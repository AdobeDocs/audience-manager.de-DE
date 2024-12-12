---
title: Aktualisieren Sie Ihre Datenerfassungsbibliothek für Audience Manager von der AppMeasurement JavaScript-Bibliothek in die Web SDK JavaScript-Bibliothek.
description: Machen Sie sich mit den Schritten zur Aktualisierung Ihrer Datenerfassungsbibliothek für den Audience Manager von der AppMeasurement JavaScript-Bibliothek zur Web SDK JavaScript-Bibliothek vertraut.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: f8d8eb722e7b5cc4371f400a76fbd548a1318668
workflow-type: tm+mt
source-wordcount: '2589'
ht-degree: 0%

---


# Aktualisieren Sie Ihre Datenerfassungsbibliothek für den Audience Manager von der AppMeasurement JavaScript-Bibliothek in die Web SDK JavaScript-Bibliothek.

## Vorgesehene Zielgruppe {#intended-audience}

Diese Seite richtet sich an Audience Manager und Adobe Analytics-Kunden, die die JavaScript-Bibliothek [!DNL AppMeasurement] verwenden, um Webdaten an Audience Manager zu senden.

In der folgenden Tabelle finden Sie Anleitungen zu den Migrationsschritten zum Web SDK, je nach aktueller Datenerfassungsmethode.

| Ihre vorhandene Datenerfassungsmethode | Migrationsanweisungen für Web SDK |
|---------|----------|
| [!DNL AppMeasurement] JavaScript-Bibliothek | Befolgen Sie die Anweisungen in diesem Handbuch. |
| [!DNL Audience Manager] [Tag-Erweiterung](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | Befolgen Sie die Anweisungen unter [Aktualisieren Ihrer Datenerfassungsbibliothek von der Audience Manager-Tag-Erweiterung auf die Web SDK-Tag-Erweiterung](dil-extension-to-web-sdk.md). |
| [!DNL AppMeasurement] JavaScript-Bibliothek + [!DNL Audience Manager] [DIL-Bibliothek](../dil/dil-overview.md) | Befolgen Sie die Anweisungen unter [Aktualisieren Ihrer Datenerfassungsbibliothek von der Audience Manager-Tag-Erweiterung auf die Web SDK-Tag-Erweiterung](dil-extension-to-web-sdk.md). |

## Migrationsübersicht {#overview}

Die Migration von [!DNL AppMeasurement] zum [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) ist in erster Linie eine Adobe Analytics-Migration. Für Audience Manager umfasst diese Migration auch Audience Manager. Beide müssen gemeinsam migriert werden. Wenn Sie hauptsächlich mit Audience Manager arbeiten, stellen Sie sicher, dass Sie das Analytics-Team an dieser Migration beteiligen.

Wenn Sie [!DNL AppMeasurement] für die Audience Manager-Datenerfassung verwenden, verwenden Sie derzeit den [!DNL Server-side Forwarding (SSF)]-Ansatz, um Analytics-Daten an Audience Manager zu senden. Bei dieser Konfiguration wird die Analytics-Datenerfassungsanforderung an Audience Manager weitergeleitet, der auch die Seitenantwort des Audience Managers verarbeitet.

Dies ist seit vielen Jahren der Standardansatz und wahrscheinlich Ihr aktuelles Setup. Wenn Ihre [!DNL AppMeasurement] -Bibliothek das `AudienceManagement` -Modul enthält und Ihre Datenerfassungsaufrufe den `/10/` -Pfad in die Anfrage (`/b/ss/examplereportsuite/10/`) einschließen, ist dieses Handbuch für Sie bestimmt.

## Serverseitige Weiterleitung (Server-Side Forwarding, SSF) im Vergleich zu Web SDK-Datenflüssen {#data-flows}

Für die folgenden Anweisungen ist es entscheidend, die Datenflussunterschiede zwischen Analytics und Audience Manager beim Wechsel zum Web SDK (und dem Edge Network) zu verstehen.

Bei der serverseitigen Weiterleitung erfasst der regionale Datenerfassungsknoten von Analytics die Daten, wandelt sie in ein vom Audience Manager akzeptiertes Signal um, sendet sie an den Audience Manager und gibt die Antwort des Audience Managers auf die Seite zurück. Das Modul [!DNL AudienceManagement] in der Bibliothek [!DNL AppMeasurement] verarbeitet dann die Antwort (z. B. Ablegen von Cookies, Senden von URL-Zielen). Dieser Vorgang wird als serverseitige Weiterleitung bezeichnet, da Analytics die Daten mithilfe von Adobe-Servern an den Audience Manager weiterleitet.

Mit Web SDK sendet das Edge Network Daten in separaten Aktionen an Analytics und Audience Manager. Das Web SDK ist eine einzelne Bibliothek, die Daten an alle Lösungen sendet und das Edge Network wandelt lösungsunabhängige Datenpunkte in lösungsspezifische Formate um.

In diesem neuen Datenfluss werden alle Daten an ein Edge Network [datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview) gesendet, das Sie [konfigurieren](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) können, um Daten nach Bedarf an Adobe-Lösungen zu senden. Zum Audience Manager wandelt die Aktivierung des Audience Manager-Dienstes im Datastream [!DNL XDM] und Analytics-Daten in von Audience Manager akzeptierte Signale um. Das Edge Network gibt auch die Antwort des Audience Managers an die Seite zurück, auf der das Web SDK die Antwort verarbeitet, ähnlich wie dies [!DNL AppMeasurement] und das [!DNL AudienceManagement]-Modul getan haben.

## Migration von Tags und Nicht-Tags {#tags-vs-non-tags}

Unabhängig davon, ob Sie Tags mit der Erweiterung [!DNL AppMeasurement], der Bibliothek [!DNL AppMeasurement] in einem anderen Tag-Management-System verwenden oder [!DNL AppMeasurement] direkt auf der Seite platzieren, sind die Schritte für die Migration von Audience Manager zum Web SDK identisch. Da die Migration von Audience Managern von der Analytics-Migration abhängig ist, werden die Schritte für die Migration von [!DNL AppMeasurement] zum Web SDK während der Analytics-Migration festgelegt.

Diese Informationen werden in der Analytics-Dokumentation für [Tags](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) - oder [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) -basierte Implementierungen behandelt.

## XDM und die `data.__adobe.` -Knoten {#xdm-data-nodes}

Eine der Hauptfunktionen des [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) besteht darin, Daten an [Real-time Customer Data Platform (RTCDP)](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home) zu senden. Um dies zu erreichen und dennoch Daten für andere Experience Cloud-Lösungen ohne vollständige Neuimplementierung zu erfassen, werden lösungsspezifische Daten innerhalb des Datenerfassungsserver-Aufrufs aufgeteilt. Dieser Aufruf verwendet ein standardisiertes JSON-Schema namens [Experience-Datenmodell (XDM)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home)

Lösungsunabhängige Elemente wie Informationen über den Browser und das Gerät werden in einer vorab festgelegten XDM-Struktur an das Edge Network gesendet. Das Edge Network wandelt diese Daten in lösungsspezifische Formate um. Daten, die spezifisch für Target, Analytics und Audience Manager sind, werden jedoch in einem dedizierten `data.__adobe` -Knoten innerhalb der XDM-Payload gespeichert.

Beispiel:

* Die Analytics-Variable `s.eVar1` wird in der XDM-Payload als `data.__adobe.analytics.evar1` dargestellt.
* Ein Target-Parameter, der sich auf den Status der Kundenloyalität bezieht, wird als `data.__adobe.target.loyaltyStatus` gespeichert.

Daten im Knoten `__adobe` werden an die entsprechenden Lösungen (wie Analytics und Audience Manager) gesendet, ohne an Experience Platform gesendet zu werden, selbst wenn der Experience Platform-Dienst im Datastream aktiviert ist. Dies bedeutet, dass Sie Ihre aktuellen Konfigurationen für Analytics und Audience Manager beibehalten können, während Sie die Flexibilität haben, alle erforderlichen Datenelemente XDM-Schemaelementen für Echtzeit-Anwendungsfälle beim Experience Platform mithilfe von [Datenvorbereitung für die Datenerfassung](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep) zuzuordnen.

Beispielsweise kann die Analytics-Zeichenfolge &quot;`s.products`&quot;, mit der der Warenkorbinhalt während des Checkout gemeldet wird, weiterhin im Originalformat an Analytics und Audience Manager gesendet werden. Gleichzeitig können Sie die Elemente dieser Zeichenfolge verwenden, um intuitivere XDM-Warenkorbschemata für Experience Platform-Anwendungsfälle zu erstellen.

Da die meisten Audience Manager-Implementierungen auf Analytics-Daten basieren, die an Audience Manager weitergeleitet werden, basieren viele Ihrer Audience Manager-Eigenschaftsausdrücke wahrscheinlich auf Analytics-Variablen (`c_evar#`, `c_prop#` und `c_events`). Um zu vermeiden, dass während der Migration Eigenschaftenausdrücke mithilfe von XDM-Formaten neu erstellt werden, ist das Edge Network standardmäßig so konfiguriert, dass alle im Knoten `data.__adobe.analytics` gefundenen Analytics-Variablen in Audience Manager-Signale umgewandelt werden. Dieser Vorgang ähnelt dem serverseitigen Weiterleitungs-Workflow.

Das Edge Network kann diese Transformation durchführen, da ein einzelner Datenerfassungsaufruf von der Seite an einen einzelnen Datastream gesendet wird, der mehrere Adobe-Lösungen speist. Daher verwenden die meisten Migrationen von [!DNL AppMeasurement] zum Web SDK für sowohl Analytics als auch Audience Manager in erster Linie den Knoten `data.__adobe.analytics` .

Das Edge Network wandelt Geräte- und Browserdaten aus der XDM-Payload und den Paketkopfzeilen in Audience Manager-Signale um. Auf diese Weise können Sie die Plattformschlüssel `h_` und `d_` in Audience Manager-Eigenschaftsausdrücken weiterhin verwenden.

## Der Knoten `data.__adobe.audiencemanager` {#data-note}

Der Knoten `data.__adobe.audiencemanager` wird für Audience Manager-Implementierungen verwendet, die nicht auf Analytics angewiesen sind. Es speichert benutzerdefinierte Audience Manager-Schlüssel-Wert-Paare, die zuvor über die [DIL-Bibliothek](../dil/dil-overview.md)-Bibliothek gesendet wurden, wie im [Migrationshandbuch für Tag-Erweiterungen](dil-extension-to-web-sdk.md) beschrieben.

Der Knoten `data.__adobe.audiencemanager` ist zwar für die in diesem Handbuch beschriebene Migration nicht erforderlich, doch ermöglicht der hier erläuterte neue Datenfluss das Senden von Daten an Audience Manager, ohne in Analytics aufgezeichnet zu werden.

Wenn Sie ein benutzerdefiniertes Schlüssel/Wert-Paar an Audience Manager senden müssen, ohne es in Analytics einschließen zu müssen, können Sie den Knoten `data.__adobe.audiencemanager` verwenden. Jeder Datensatz in diesem Knoten wird an die vom Audience Manager transformierten Analytics-Daten im Datenerfassungsserver-Aufruf angehängt.

## Vorteile und Nachteile dieses Implementierungspfads

Die Verwendung dieses Migrationsansatzes hat sowohl Vor- als auch Nachteile. Legen Sie bei jeder Option sorgfältig ab, welcher Ansatz für Ihr Unternehmen am besten geeignet ist.

| Vorteile | Nachteile |
| --- | --- |
| <ul><li>**Verwendet Ihre vorhandene Implementierung**: Dieser Ansatz erfordert zwar einige Implementierungsänderungen, erfordert jedoch keine völlig neue Implementierung. Sie können Ihre vorhandene Datenschicht und Ihren Code mit minimalen Änderungen an der Implementierungslogik verwenden.</li><li>**Kein Schema erforderlich**: Für diese Phase der Migration zum Web SDK benötigen Sie kein XDM-Schema. Stattdessen können Sie das `data` -Objekt ausfüllen, das Daten direkt an Audience Manager sendet. Nachdem die Migration zum Web SDK abgeschlossen ist, können Sie ein Schema für Ihre Organisation erstellen und die Datastraam-Zuordnung verwenden, um die entsprechenden XDM-Felder auszufüllen. Wenn in dieser Phase des Migrationsprozesses ein Schema erforderlich ist, muss Ihr Unternehmen ein Audience Manager-XDM-Schema verwenden. Die Verwendung dieses Schemas erschwert es Ihrem Unternehmen, in Zukunft Ihr eigenes Schema zu verwenden.</li></ul> | <ul><li>**Technische Schulden bei der Implementierung**: Da dieser Ansatz eine modifizierte Form Ihrer bestehenden Implementierung verwendet, kann es schwieriger sein, die Implementierungslogik zu verfolgen und bei Bedarf zukünftige Änderungen vorzunehmen.</li><li>**Erfordert Zuordnung zum Senden von Daten an Platform**: Wenn Ihr Unternehmen für die Verwendung von Real-Time CDP bereit ist, müssen Sie Daten an einen Datensatz in Adobe Experience Platform senden. Diese Aktion erfordert, dass jedes Feld im `data` -Objekt ein Eintrag im Tool für die Datenasterzuordnung ist, der ihn einem XDM-Schemafeld zuordnet. Die Zuordnung muss nur einmal für diesen Workflow durchgeführt werden. Es müssen keine Implementierungsänderungen vorgenommen werden. Es handelt sich jedoch um einen zusätzlichen Schritt, der beim Senden von Daten in ein XDM-Objekt nicht erforderlich ist.</li></ul> |

Adobe empfiehlt, diesem Implementierungspfad in den folgenden Szenarien zu folgen:

* Sie verfügen über eine vorhandene Implementierung mithilfe der Adobe Analytics AppMeasurement JavaScript-Bibliothek. Wenn Sie über eine Implementierung mit der Audience Manager-Tag-Erweiterung verfügen, folgen Sie stattdessen dem Befehl &quot;[Migrieren von der Audience Manager-Tag-Erweiterung zur Web SDK-Tag-Erweiterung](dil-extension-to-web-sdk.md)&quot;.
* Sie beabsichtigen, Real-Time CDP in Zukunft zu verwenden, möchten Ihre Audience Manager-Implementierung jedoch nicht von Grund auf durch eine Web SDK-Implementierung ersetzen. Die Ersetzung Ihrer Implementierung durch das Web SDK erfordert den größten Aufwand, bietet aber auch die praktikabelste langfristige Implementierungsarchitektur. Wenn Ihr Unternehmen bereit ist, die Implementierung eines sauberen Web SDK durchzuführen, finden Sie weitere Informationen in der [Web SDK-Dokumentation](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) .

## Schritte für die Migration zum Web SDK

Gehen Sie wie folgt vor, um Ihre Datenerfassungsintegration in das Web SDK zu migrieren.

+++**1. Migrieren Sie Ihre Analytics-Implementierung**.

Wenden Sie sich an Ihr Analytics-Team, um die Schritte für die Analytics-Migration in den auf [Tags](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) oder [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) basierenden Implementierungen durchzuführen. Nachdem Sie Ihre Analytics-Implementierung migriert haben, fahren Sie mit dem folgenden Schritt fort.

+++

+++**2. Fügen Sie den Audience Manager-Dienst zum Datastream** hinzu.

Fügen Sie den Audience Manager-Dienst zum Datenspeicher hinzu, den Sie in Schritt 1 erstellt haben.

1. Navigieren Sie zu [experience.adobe.com](https://experience.adobe.com) und melden Sie sich mit Ihren Anmeldedaten an.
1. Verwenden Sie die Startseite oder die Produktselektor oben rechts, um zu **[!UICONTROL Data Collection]** zu navigieren.
1. Wählen Sie im linken Navigationsbereich **[!UICONTROL Datastreams]** aus.
1. Wählen Sie den Datenspeicher aus, den Sie im Rahmen der Analytics-Migration in Schritt 1 erstellt haben.
1. Wählen Sie **[!UICONTROL Add Service]** aus.
1. Wählen Sie im Dropdown-Menü Dienst die Option **[!UICONTROL Audience Manager]** aus.
1. Aktivieren Sie die Optionen **[!UICONTROL Cookie Destinations Enabled]** und **[!UICONTROL URL Destinations Enabled]**. Diese Optionen ermöglichen es dem Edge Network, diese Audience Manager-Zieltypen zur Seite zurückzugeben.
1. Stellen Sie sicher, dass **[!UICONTROL Enable XDM Flattened Fields]** deaktiviert ist. Diese Option deaktiviert die automatische Transformation von Analytics-Variablen in Audience Manager-Signale. Diese Option soll die Abwärtskompatibilität für Benutzer gewährleisten, die zu Web SDK migriert wurden, bevor das Edge Network die Analytics-Daten automatisch in Audience Manager-Signale umwandelte.

   >[!NOTE]
   >
   >Für die Migration zum Web SDK mit aktivierter Option **[!UICONTROL Enabled XDM Flattened Fields]** müssen alle Daten, die in Audience Manager benötigt werden, als XDM formatiert sind, sowie alle Audience Manager-Eigenschaften, die Props, eVars oder Ereignisse verwenden, aktualisiert werden, um stattdessen nach XDM-formatierten Daten zu suchen. Adobe empfiehlt, diese Option deaktiviert zu lassen.


   ![Audience Manager-Dienst hinzufügen](assets/add-service.png) {style="border:1px solid lightslategray"}

1. Wählen Sie **[!UICONTROL Save]** aus, um die Konfiguration des Datastreams zu speichern.

Ihr Datastream kann jetzt Daten empfangen und an Audience Manager weitergeben. Notieren Sie die Datastream-ID, da diese ID für die Konfiguration des Web SDK im Code erforderlich ist.

+++

+++**3. Aktivieren Sie ID-Synchronisierungen von Drittanbietern und legen Sie die Audience Manager-Container-ID** fest.

1. Navigieren Sie zu [experience.adobe.com](https://experience.adobe.com) und melden Sie sich mit Ihren Anmeldedaten an.
1. Verwenden Sie die Startseite oder die Produktselektor oben rechts, um zu **[!UICONTROL Data Collection]** zu navigieren.
1. Wählen Sie im linken Navigationsbereich **[!UICONTROL Datastreams]** aus.
1. Wählen Sie den Datenspeicher aus, den Sie im Rahmen der Analytics-Migration in Schritt 1 erstellt haben.
1. Wählen Sie in der oberen rechten Ecke der Konfigurationsseite des Datastreams **[!UICONTROL Edit]** aus.
1. Erweitern Sie das Dropdown-Menü **[!UICONTROL Advanced Options]** und aktivieren Sie die Funktion **[!UICONTROL Third Party ID Sync]** , falls sie noch nicht aktiviert ist. Diese Option weist das Edge Network an, Partner-ID-Synchronisationen für Audience Manager- und Experience Platform-Datenpartner zurückzugeben.

   ![Aktivieren Sie die Synchronisierung der Drittanbieter-ID.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. In den meisten Fällen können Sie das Feld **[!UICONTROL Third Party ID Sync Container ID]** leer lassen. Der Standardwert lautet `0`. Wenn Sie jedoch sicherstellen möchten, dass die richtige Container-ID verwendet wird, führen Sie die folgenden Schritte aus:
   * Öffnen Sie ein Browserfenster im Inkognito- oder privaten Modus und navigieren Sie zu einer Seite, die Teil der Migration ist.
   * Verwenden Sie die Entwicklertools des Browsers, um nach dem Netzwerkaufruf zu `dpm.demdex.net/id` zu filtern. Dieser Aufruf wird nur auf der ersten Seite eines ersten Besuchs ausgelöst. Daher ist eine Inkognito oder ein privater Browser erforderlich.
   * Anzeigen der Payload der Anfrage. Wenn der Parameter `d_nsid` sich von null unterscheidet, kopieren Sie ihn in das Feld **[!UICONTROL Third Party ID Sync Container ID]** .

1. Wählen Sie **[!UICONTROL Save]** aus.

Ihr Datastream ist jetzt bereit, sowohl Daten an Audience Manager zu senden als auch die Audience Manager-Antworten an das Web SDK zu übergeben.

+++

+++**4. Hinzufügen von Kunden-IDs zur Identitätszuordnung**

Die meisten Audience Manager-Implementierungen verwenden [Profilzusammenführungsregeln](../features/profile-merge-rules/merge-rules-overview.md) in geräteübergreifenden Personalisierungsszenarien und helfen zu steuern, für welche Segmente sich Besucher je nach Authentifizierungsstatus qualifizieren können (angemeldet oder abgemeldet). Profilzusammenführungsrichtlinien erfordern, dass bei jedem Datenerfassungsaufruf nach der Authentifizierung eine kundeneigene Kennung (CRM-ID, Kundennummer usw.) an den Audience Manager gesendet wird. Zuvor wurde die Funktion `setCustomerIDs` des Besucher-ID-Diensts ([!DNL visitor.js]) verwendet, um Kunden-IDs an jeden Analytics-Datenerfassungsaufruf anzuhängen, der dann an Audience Manager weitergeleitet wurde.

Mit der Web SDK müssen diese Identitäten jetzt mit einem speziellen XDM-Konstrukt namens [IdentityMap](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap) an das Edge Network gesendet werden.

Die korrekte Übergabe von Identitäten in einer Identitätszuordnung erfordert das Verständnis von [Identitäts-Namespaces](https://experienceleague.adobe.com/de/docs/experience-platform/identity/features/namespaces) und die sorgfältige Prüfung der zu übergebenden Identitäten, insbesondere beim Senden von Daten an eine Experience Platform-Sandbox. [In diesem Artikel](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-21305) werden diese Überlegungen und Anweisungen erläutert.

Nachdem Sie bestimmt haben, welche Identitäten weitergegeben werden sollen und wann, befolgen Sie die Anleitungen zur Verwendung des [!UICONTROL Identity map] **[!UICONTROL Identity map]** [Datenelements](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/data-element-types#identity-map) in Tags oder legen Sie es manuell fest, wie in der [Übersicht über Identitätsdaten](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/identity/overview) beschrieben, um es an Ihre Web SDK-Bereitstellungsstrategie anzupassen.

+++

## Konfigurieren der serverseitigen Weiterleitung und Audience Analytics in der Benutzeroberfläche von Analytics Report Suite Manager {#configure-ssf-analytics}

Wenn Sie mit der Analytics [serverseitigen Weiterleitung](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf) vertraut sind, fragen Sie sich vielleicht: &quot;*Sollte ich die Einstellung für die serverseitige Weiterleitung in der Benutzeroberfläche von Analytics Report Suite Manager deaktivieren, um zu verhindern, dass Analytics-Daten zweimal an den Audience Manager gesendet werden?*&quot;.

Die Antwort lautet &quot;Nein&quot;. Sie sollten diese Einstellung nicht deaktivieren. Dies ist der Grund:

Wenn diese Einstellung aktiviert ist und das Modul [!DNL AudienceManagement] der Bibliothek [!DNL AppMeasurement] auf Ihrer Seite hinzugefügt wird, fließen alle an diese Report Suite gesendeten Daten ebenfalls an den Audience Manager.

Zur Einhaltung der DSGVO-Datenschutzbestimmungen gibt es Szenarien, in denen Daten in Analytics gesammelt werden können, jedoch nicht in Audience Manager. Darüber hinaus gibt es Fälle, in denen globale Report Suites und regionsspezifische Anwendungsfälle verwendet werden, in denen einige Datenerfassungsaufrufe nicht an Audience Manager gesendet werden sollten. Um dieses Problem zu beheben, führte Adobe eine serverseitige Weiterleitung mit der Bezeichnung &quot;Aus&quot; ein.

Wie auf der Seite [Analytics- und DSGVO-Compliance mit Schwerpunkt auf der serverseitigen Weiterleitung](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr) erläutert, verhindert das Hinzufügen der Kontextvariablen `cm.ssf=1` zu einem Analytics-Datenerfassungsserver, dass dieser Datenerfassungsaufruf an Audience Manager weitergeleitet wird.

Es gibt zwei Gründe, warum Sie diese Einstellung nicht deaktivieren sollten.

1. Wenn der Audience Manager-Dienst für einen Datastream aktiviert ist, hängt das Edge Network die Variable &quot;`cm.ssf`&quot;an alle an Analytics gesendeten Datenerfassungsanforderungen an. Dadurch wird verhindert, dass die Analytics-Daten auch an Audience Manager gesendet werden. In allen Assurance-Protokollen, die zur Validierung der Analytics-Migration verwendet werden, wird die Variable &quot;`cm.ssf=1`&quot;angezeigt, wenn der Audience Manager-Dienst im Datastream aktiviert ist.
1. Diese Einstellung ermöglicht auch den Datenfluss für die [!DNL Audience Analytics] -Integration. Wie in der [Audience Analytics-Übersicht](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/mc-audiences-aam) beschrieben, ist für diese Integration eine serverseitige Weiterleitung erforderlich, da die Audience Manager-Antwort auf den Analytics-Datenerfassungsserver dem Analytics-Treffer vor der Verarbeitung hinzugefügt wird. Ein ähnlicher Vorgang erfolgt innerhalb des Edge Networks. Wenn die serverseitige Weiterleitung aktiviert ist, fügt das Edge Network die erforderlichen Segmente aus der Audience Manager-Antwort zu den an Analytics gesendeten Daten hinzu.

Zusammenfassend ist es wichtig, dass diese Einstellung aktiviert bleibt, damit Audience Analytics weiterhin mit einer Web SDK-Implementierung funktioniert und keine Daten in Audience Manager doppelt gezählt werden.
