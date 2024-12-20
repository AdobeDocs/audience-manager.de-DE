---
title: Migrieren von der Audience Manager-Tag-Erweiterung zur Web SDK-Tag-Erweiterung
description: Machen Sie sich mit den Schritten zur Aktualisierung Ihrer Datenerfassungsbibliothek für Audience Manager von der Audience Manager-Tag-Erweiterung zur Web SDK-Tag-Erweiterung vertraut
exl-id: 7f0486db-4511-4311-90df-290580fdcd78
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---

# Aktualisieren Sie Ihre Datenerfassungsbibliothek für den Audience Manager von der Audience Manager-Tag-Erweiterung zur Web SDK-Tag-Erweiterung.

## Vorgesehene Zielgruppe

Diese Seite richtet sich an Audience Manager-Kunden, die die [Audience Manager-Tag-Erweiterung](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) verwenden, um Web-Sammlungsdaten in den Audience Manager zu bringen. Kunden, die die AppMeasurement JavaScript-Bibliothek verwenden, lesen bitte das Handbuch zum Aktualisieren Ihrer Datenerfassungsbibliothek für den Audience Manager [von der AppMeasurement JavaScript-Bibliothek zur Web SDK JavaScript-Bibliothek](appmeasurement-to-web-sdk.md).

## Vor- und Nachteile dieses Implementierungspfads

Die Verwendung dieses Migrationsansatzes hat sowohl Vor- als auch Nachteile. Wägen Sie jede Option sorgfältig ab, um zu entscheiden, welcher Ansatz für Ihr Unternehmen am besten geeignet ist.

| Vorteile | Nachteile |
| --- | --- |
| <ul><li>**Keine Code-Änderungen auf Ihrer Site**: Da in Ihrer Implementierung bereits Tags installiert sind, können alle Migrationsaktualisierungen in der Tags-Oberfläche vorgenommen werden.</li><li>**Verwendet Ihre vorhandene Implementierung**: Für diesen Ansatz ist keine neue Implementierung erforderlich. Neue Regelaktionen sind zwar erforderlich, aber Sie können Ihre vorhandenen Datenelemente und Regelbedingungen mit minimalen Änderungen wiederverwenden.</li><li>**Erfordert kein Schema**: Für diesen Schritt der Migration zur Web-SDK benötigen Sie kein XDM-Schema. Stattdessen können Sie das `data`-Objekt füllen, das Daten direkt an Adobe Audience Manager sendet. Sobald die Migration auf die Web-SDK abgeschlossen ist, können Sie ein Schema für Ihr Unternehmen erstellen und die Datenstromzuordnung verwenden, um die entsprechenden XDM-Felder auszufüllen. Wenn in dieser Phase des Migrationsprozesses ein Schema erforderlich wäre, würde Ihr Unternehmen gezwungen sein, ein Adobe Audience Manager-XDM-Schema zu verwenden. Die Verwendung dieses Schemas erschwert es Ihrem Unternehmen, in Zukunft Ihr eigenes Schema zu verwenden.</li></ul> | <ul><li>**Technischer Aufwand bei der Implementierung**: Da dieser Ansatz eine geänderte Form Ihrer vorhandenen Implementierung verwendet, kann es schwieriger sein, die Implementierungslogik zu verfolgen und bei Bedarf Änderungen durchzuführen. Benutzerdefinierter Code kann besonders schwer zu debuggen sein.</li><li>**Zuordnung erforderlich, um Daten an Platform zu senden**: Wenn Ihr Unternehmen für die Verwendung von Real-Time CDP bereit ist, müssen Sie Daten an einen Datensatz in Adobe Experience Platform senden. Für diese Aktion muss jedes Feld im `data`-Objekt ein Eintrag im Datenstrom-Zuordnungs-Tool sein, der es einem XDM-Schemafeld zuweist. Die Zuordnung muss für diesen Workflow nur einmal durchgeführt werden und erfordert keine Änderungen an der Implementierung. Es ist jedoch ein zusätzlicher Schritt, der beim Senden von Daten in einem XDM-Objekt nicht erforderlich ist.</li></ul> |

Adobe empfiehlt, diesen Implementierungspfad einzuhalten, wenn Sie über eine vorhandene Implementierung mit der Tag-Erweiterung &quot;Adobe Audience Manager&quot; verfügen.

## Zur Migration auf die Web-SDK erforderliche Schritte

Die folgenden Schritte enthalten konkrete Ziele, auf die Sie hinarbeiten müssen. Wählen Sie jeden Schritt aus, um detaillierte Anweisungen zur Durchführung zu erhalten.

+++**1. Erstellen und Konfigurieren eines Datenstroms**

Gehen Sie wie folgt vor, um einen Datenstrom in der Datenerfassung von Adobe Experience Platform zu erstellen. Wenn Sie Daten an diesen Datenstrom senden, leitet er Daten an den -Audience Manager weiter. In Zukunft leitet derselbe Datenstrom Daten an Real-Time CDP weiter.

1. Navigieren Sie zu [experience.adobe.com](https://experience.adobe.com) und melden Sie sich mit Ihren Anmeldedaten an.
1. Navigieren Sie mithilfe der Startseite oder des Produktselektors oben rechts zu **[!UICONTROL Data Collection]**.
1. Wählen Sie in der linken Navigation **[!UICONTROL Datastreams]** aus.
1. Wählen Sie **[!UICONTROL New Datastream]** aus.
1. Geben Sie den gewünschten Namen ein und wählen Sie dann **[!UICONTROL Save]** aus.
1. Wählen Sie nach der Erstellung des Datenstroms **[!UICONTROL Add Service]** aus.
1. Wählen Sie im Dropdown-Menü Service die Option **[!UICONTROL Adobe Audience Manager]** aus.
1. Stellen Sie sicher, dass die Option **[!UICONTROL Enable XDM Flattened Fields]** deaktiviert ist.

   ![Audience Manager-Service hinzufügen](assets/add-service.png) {style="border:1px solid lightslategray"}

Ihr Datenstrom ist jetzt bereit, Daten zu empfangen und an den Audience Manager weiterzuleiten.

+++

+++**2. Fügen Sie die Web SDK-Erweiterung zu Ihrer Tag-Eigenschaft hinzu**

In diesem Abschnitt wird Ihr Tag auf den Großteil des Migrationsaufwands vorbereitet, der im nächsten Schritt stattfindet.

1. Wählen Sie oben links in der Adobe Experience Platform-Benutzeroberfläche das Hamburger-Symbol und dann **[!UICONTROL Tags]** aus.
1. Wählen Sie die gewünschte Tag-Eigenschaft aus.
1. Wählen Sie im linken Navigationsbereich der Tag-Eigenschaft **[!UICONTROL Extensions]** aus.
1. Wählen Sie oben **[!UICONTROL Catalog]** aus, um eine Liste aller verfügbaren Erweiterungen anzuzeigen.
1. Suchen Sie nach der **[!UICONTROL Adobe Experience Platform Web SDK]**-Erweiterung, wählen Sie sie aus und klicken Sie dann auf der rechten Seite auf **[!UICONTROL Install]** .

   ![Katalog](assets/catalog.png) {style="border:1px solid lightslategray"}

1. Die Konfigurationseinstellungen der Erweiterung werden angezeigt. Suchen Sie den Abschnitt **[!UICONTROL Datastreams]** und wählen Sie die verwendete Sandbox und den im vorherigen Schritt erstellten Datenstrom aus.

   ![Datenstromauswahl](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Wählen Sie **[!UICONTROL Save]** aus.

In Ihrer Tag-Eigenschaft ist jetzt Web SDK installiert.

+++

+++**3. Erstellen Sie ein Datenelement für ein Datenobjekt**

Das Datenelement „Datenobjekt“ bietet ein intuitives Framework zum Konfigurieren einer Payload, die von Web SDK zum Senden an einen Datenstrom verwendet wird. Die meisten Regeln, die Sie im folgenden Schritt aktualisieren, interagieren mit diesem Datenelement.

1. Wählen Sie in der linken Navigation der Tags-Benutzeroberfläche **[!UICONTROL Data Elements]** aus.
1. **[!UICONTROL Add Data Element]** auswählen
1. Geben Sie dem Datenelement die folgenden Einstellungen:
   * **[!UICONTROL Name]**: Alles, was Sie möchten, z. B. „Datenschicht“ oder „Datenobjekt“
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]**: [!UICONTROL Variable]
   * Kontrollkästchen können unverändert bleiben.
1. Wählen Sie rechts die folgenden Einstellungen aus:
   * Optionsfeld „Eigenschaft“: **[!UICONTROL Data]**
   * **[!UICONTROL Solution]**: [!UICONTROL Adobe Audience Manager]
1. Wählen Sie **[!UICONTROL Save]** aus.

   ![Datenelement erstellen](assets/create-data-element.png) {style="border:1px solid lightslategray"}

Ihre Tag-Eigenschaft verfügt jetzt über alles, was zum Aktualisieren jeder Regel erforderlich ist.

+++

+++**4. Aktualisieren Sie Regeln, um die Web SDK-Erweiterung anstelle der Audience Manager-Erweiterung zu verwenden**

Dieser Schritt enthält den Großteil des für die Migration auf die Web-SDK erforderlichen Arbeitsaufwands und setzt Kenntnisse der Funktionsweise Ihrer Implementierung voraus. Nachfolgend finden Sie ein Beispiel für die Bearbeitung einer typischen Tag-Regel. Aktualisieren Sie alle Tag-Regeln in Ihrer Implementierung, um alle Verweise auf die Audience Manager-Erweiterung durch die Web SDK-Erweiterung zu ersetzen.

1. Wählen Sie in der linken Navigation der Tags-Benutzeroberfläche **[!UICONTROL Rules]** aus.
1. Regel zum Bearbeiten auswählen.
1. **[!UICONTROL Audience Manager - Set Variables]** auswählen
1. Notieren Sie alle Audience Manager-Variablen, die in dieser Regel festgelegt sind. Schließen Sie sowohl in den Dropdown-Menüs festgelegte Variablen als auch Variablen ein, die in benutzerdefiniertem Code festgelegt sind.
1. Ändern Sie die [!UICONTROL Action Configuration] in die folgenden Einstellungen:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: Variable aktualisieren
1. Stellen Sie sicher, dass das in Schritt 3 erstellte Datenobjekt in der Dropdown-Liste auf der rechten Seite im Feld **[!UICONTROL Data element]** ausgewählt ist.
1. Legen Sie die Schlüssel-Wert-Paare des Audience Managers auf dieselben entsprechenden Werte fest, wie sie in der Audience Manager-Erweiterung konfiguriert wurden.
1. Nachdem die gesamte Regellogik mithilfe der Web-SDK-Erweiterung repliziert wurde, wählen Sie **[!UICONTROL Keep Changes]** aus.
1. Wiederholen Sie diese Schritte für jede Aktionskonfiguration, die die Audience Manager-Tag-Erweiterung zum Festlegen von Werten verwendet.

Die obigen Schritte gelten nur für Regeln, die Werte festlegen. Die folgenden Schritte ersetzen alle Aktionen, die die [!UICONTROL Action Configuration]-[!UICONTROL Send Event] verwenden.

1. Wählen Sie eine Regel aus, die ein Web SDK-Ereignis sendet.
1. Wählen Sie die **[!UICONTROL Send Event]** Aktionstyp aus.
1. Ändern Sie die [!UICONTROL Action Configuration] in die folgenden Einstellungen:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: [!UICONTROL Send event]
1. Ändern Sie auf der rechten Seite die Aktionseinstellungen wie folgt:
   * **[!UICONTROL Type]**: Verwenden Sie **[!UICONTROL Web Webpagedetails Page Views]**.
   * **[!UICONTROL Data]**: Wählen Sie das Datenobjekt aus, das Sie in Schritt 3 erstellt haben.
1. Wählen Sie **[!UICONTROL Keep Changes]** aus.
1. Wiederholen Sie diese Schritte für jede Aktionskonfiguration, die Audience Manager zum Senden eines Ereignisses verwendet.

+++

+++**5. Aktualisierte Publish-Regeln**

Das Veröffentlichen aktualisierter Regeln folgt demselben Workflow wie alle anderen Änderungen an Ihrer Tags-Konfiguration.

1. Wählen Sie in der linken Navigation der Tags-Benutzeroberfläche **[!UICONTROL Publishing Flow]** aus.
1. Wählen Sie **[!UICONTROL Add Library]** aus.
1. Geben Sie diesem Tag-Commit einen Namen, z. B. „Upgrade auf Web SDK&quot;.
1. Wählen Sie **[!UICONTROL Add All Changed Resources]** aus.
1. Wählen Sie **[!UICONTROL Save]** aus.
1. Der Veröffentlichungs-Workflow zeigt einen orangefarbenen Punkt an, der angibt, dass er gerade erstellt wird. Sobald der Punkt grün wird, sind Ihre Änderungen in Ihrer Entwicklungsumgebung verfügbar.
1. Testen Sie die Änderungen in Ihrer Entwicklungsumgebung, um sicherzustellen, dass alle Regeln ordnungsgemäß ausgelöst werden und das Datenobjekt mit erwarteten Werten gefüllt wird.
1. Wenn Sie bereit sind, senden Sie die Bibliothek zur Genehmigung, erstellen Sie sie für das Staging, genehmigen Sie sie dann letztendlich und veröffentlichen Sie sie in der Produktion.

   ![Publishing-Ablauf](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Deaktivieren Sie die Audience Manager-Erweiterung**

Nachdem Ihre Tag-Implementierung vollständig in die Web-SDK migriert wurde, können Sie die Audience Manager-Erweiterung deaktivieren.

1. Wählen Sie in der linken Navigation der Tags-Benutzeroberfläche **[!UICONTROL Extensions]** aus.
1. Suchen Sie die [!UICONTROL Audience Manager]-Erweiterung und wählen Sie sie aus. Wählen Sie rechts **[!UICONTROL Disable]** aus.
1. Befolgen Sie denselben Veröffentlichungs-Workflow wie oben, um die Entfernung der [!UICONTROL Audience Manager]-Erweiterung zu veröffentlichen.
1. Sobald die Erweiterung in der Produktion deaktiviert ist, können Sie sie vollständig deinstallieren. Klicken Sie auf die Erweiterung, dann auf das Dreipunkt-Menü auf der rechten Seite und schließlich auf **[!UICONTROL Uninstall]**.
1. Folgen Sie demselben Veröffentlichungs-Workflow wie oben, um diese Änderungen in der Produktion zu veröffentlichen.

+++

Zu diesem Zeitpunkt wird Ihre Audience Manager-Implementierung vollständig in die Web-SDK migriert und ist bereit, in Zukunft zu Real-Time CDP zu wechseln.
