---
title: Migration von der Audience Manager-Tag-Erweiterung zur Web SDK-Tag-Erweiterung
description: Machen Sie sich mit den Schritten zum Aktualisieren Ihrer Datenerfassungsbibliothek für Audience Manager von der Audience Manager-Tag-Erweiterung zur Web SDK-Tag-Erweiterung vertraut.
exl-id: 7f0486db-4511-4311-90df-290580fdcd78
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---

# Aktualisieren Sie Ihre Datenerfassungsbibliothek für den Audience Manager von der Audience Manager-Tag-Erweiterung auf die Web SDK-Tag-Erweiterung

## Vorgesehene Zielgruppe

Diese Seite ist für Audience Manager gedacht, die die Tag-Erweiterung [Audience Manager](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) verwenden, um Webkollektionsdaten in Audience Manager zu importieren. Kunden, die die AppMeasurement JavaScript-Bibliothek verwenden, lesen bitte das Handbuch zum Aktualisieren Ihrer Datenerfassungsbibliothek für Audience Manager [ von der AppMeasurement JavaScript-Bibliothek zur Web SDK-JavaScript-Bibliothek](appmeasurement-to-web-sdk.md).

## Vorteile und Nachteile dieses Implementierungspfads

Die Verwendung dieses Migrationsansatzes hat sowohl Vor- als auch Nachteile. Legen Sie bei jeder Option sorgfältig ab, welcher Ansatz für Ihr Unternehmen am besten geeignet ist.

| Vorteile | Nachteile |
| --- | --- |
| <ul><li>**Keine Codeänderungen auf Ihrer Site**: Da Ihre Implementierung bereits Tags installiert hat, können alle Migrationsaktualisierungen auf der Tag-Oberfläche vorgenommen werden.</li><li>**Verwendet Ihre vorhandene Implementierung**: Für diesen Ansatz ist keine neue Implementierung erforderlich. Sie benötigen zwar neue Regelaktionen, können aber Ihre vorhandenen Datenelemente und Regelbedingungen mit minimalen Änderungen wiederverwenden.</li><li>**Kein Schema erforderlich**: Für diese Phase der Migration zum Web SDK benötigen Sie kein XDM-Schema. Stattdessen können Sie das Objekt `data` ausfüllen, das Daten direkt an Adobe Audience Manager sendet. Nachdem die Migration zum Web SDK abgeschlossen ist, können Sie ein Schema für Ihre Organisation erstellen und die Datastraam-Zuordnung verwenden, um die entsprechenden XDM-Felder auszufüllen. Wenn in dieser Phase des Migrationsprozesses ein Schema erforderlich ist, muss Ihr Unternehmen ein Adobe Audience Manager-XDM-Schema verwenden. Die Verwendung dieses Schemas erschwert es Ihrem Unternehmen, in Zukunft Ihr eigenes Schema zu verwenden.</li></ul> | <ul><li>**Technische Schulden bei der Implementierung**: Da dieser Ansatz eine modifizierte Form Ihrer vorhandenen Implementierung verwendet, kann es schwieriger sein, die Implementierungslogik zu verfolgen und bei Bedarf Änderungen vorzunehmen. Das Debuggen von benutzerspezifischem Code kann besonders schwierig sein.</li><li>**Erfordert Zuordnung zum Senden von Daten an Platform**: Wenn Ihr Unternehmen für die Verwendung von Real-Time CDP bereit ist, müssen Sie Daten an einen Datensatz in Adobe Experience Platform senden. Diese Aktion erfordert, dass jedes Feld im `data` -Objekt ein Eintrag im Tool für die Datenasterzuordnung ist, der ihn einem XDM-Schemafeld zuordnet. Die Zuordnung muss nur einmal für diesen Workflow durchgeführt werden. Es müssen keine Implementierungsänderungen vorgenommen werden. Es handelt sich jedoch um einen zusätzlichen Schritt, der beim Senden von Daten in ein XDM-Objekt nicht erforderlich ist.</li></ul> |

Adobe empfiehlt, diesem Implementierungspfad zu folgen, wenn Sie über eine vorhandene Implementierung mit der Adobe Audience Manager-Tag-Erweiterung verfügen.

## Schritte für die Migration zum Web SDK

Die folgenden Schritte enthalten konkrete Ziele, auf die wir hinarbeiten müssen. Wählen Sie jeden Schritt aus, um detaillierte Anweisungen dazu zu erhalten.

+++**1. Erstellen und Konfigurieren eines Datastreams**

Befolgen Sie die unten stehenden Anweisungen, um einen Datastream in der Adobe Experience Platform-Datenerfassung zu erstellen. Wenn Sie Daten an diesen Datastream senden, leitet er Daten an Audience Manager weiter. Künftig leitet derselbe Datenspeicher Daten an Real-Time CDP weiter.

1. Navigieren Sie zu [experience.adobe.com](https://experience.adobe.com) und melden Sie sich mit Ihren Anmeldedaten an.
1. Verwenden Sie die Startseite oder die Produktselektor oben rechts, um zu **[!UICONTROL Data Collection]** zu navigieren.
1. Wählen Sie im linken Navigationsbereich **[!UICONTROL Datastreams]** aus.
1. Wählen Sie **[!UICONTROL New Datastream]** aus.
1. Geben Sie den gewünschten Namen ein und wählen Sie dann **[!UICONTROL Save]** aus.
1. Nachdem der Datastream erstellt wurde, wählen Sie **[!UICONTROL Add Service]** aus.
1. Wählen Sie im Dropdown-Menü Dienst die Option **[!UICONTROL Adobe Audience Manager]** aus.
1. Stellen Sie sicher, dass die Option **[!UICONTROL Enable XDM Flattened Fields]** deaktiviert ist.

   ![Audience Manager-Dienst hinzufügen](assets/add-service.png) {style="border:1px solid lightslategray"}

Ihr Datastream kann jetzt Daten empfangen und an Audience Manager weitergeben.

+++

+++**2. Fügen Sie Ihrer Tag-Eigenschaft die Web SDK-Erweiterung hinzu**

In diesem Abschnitt wird Ihr -Tag für den Großteil der Migrationsschritte vorbereitet, die im nächsten Schritt unternommen werden.

1. Wählen Sie links oben in der Adobe Experience Platform-Benutzeroberfläche das Hamburger-Symbol und dann **[!UICONTROL Tags]** aus.
1. Wählen Sie die gewünschte Tag-Eigenschaft aus.
1. Wählen Sie im linken Navigationsbereich der Tag-Eigenschaft **[!UICONTROL Extensions]** aus.
1. Wählen Sie oben **[!UICONTROL Catalog]** aus, um eine Liste aller verfügbaren Erweiterungen anzuzeigen.
1. Suchen Sie nach der Erweiterung &quot;**[!UICONTROL Adobe Experience Platform Web SDK]**&quot;, wählen Sie sie aus und klicken Sie auf der rechten Seite auf &quot;**[!UICONTROL Install]**&quot;.

   ![Katalog](assets/catalog.png) {style="border:1px solid lightslategray"}

1. Die Erweiterungskonfigurationseinstellungen werden angezeigt. Suchen Sie den Abschnitt &quot;**[!UICONTROL Datastreams]**&quot;und wählen Sie die Sandbox, die Sie verwenden, sowie den Datastream aus, den Sie im vorherigen Schritt erstellt haben.

   ![Auswahl des Datenspeichers](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Wählen Sie **[!UICONTROL Save]** aus.

Für Ihre Tag-Eigenschaft ist jetzt das Web SDK installiert.

+++

+++**3. Datenobjektdatenelement** erstellen

Das Datenobjekt-Datenelement bietet ein intuitives Framework zum Konfigurieren einer Payload, die das Web SDK zum Senden an einen Datastream verwendet. Die meisten Regeln, die Sie im folgenden Schritt aktualisieren, interagieren mit diesem Datenelement.

1. Wählen Sie im linken Navigationsbereich der Tags-Oberfläche die Option **[!UICONTROL Data Elements]** aus.
1. Wählen Sie **[!UICONTROL Add Data Element]**
1. Legen Sie für das Datenelement die folgenden Einstellungen fest:
   * **[!UICONTROL Name]**: Alles, was Sie möchten, wie &quot;Datenschicht&quot;oder &quot;Datenobjekt&quot;
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]**: [!UICONTROL Variable]
   * Kontrollkästchen können unverändert bleiben.
1. Wählen Sie rechts die folgenden Einstellungen aus:
   * Optionsfeld &quot;Eigenschaft&quot;: **[!UICONTROL Data]**
   * **[!UICONTROL Solution]**: [!UICONTROL Adobe Audience Manager]
1. Wählen Sie **[!UICONTROL Save]** aus.

   ![Datenelement erstellen](assets/create-data-element.png) {style="border:1px solid lightslategray"}

Ihre Tag-Eigenschaft verfügt jetzt über alles, was zum Aktualisieren der einzelnen Regeln erforderlich ist.

+++

+++**4. Aktualisieren Sie Regeln, um die Web SDK-Erweiterung anstelle der Audience Manager-Erweiterung zu verwenden**

Dieser Schritt enthält den Großteil des für die Migration zum Web SDK erforderlichen Aufwands und erfordert Kenntnisse darüber, wie Ihre Implementierung funktioniert. Unten finden Sie ein Beispiel zum Bearbeiten einer typischen Tag-Regel. Aktualisieren Sie alle Tag-Regeln in Ihrer Implementierung, um alle Verweise auf die Audience Manager-Erweiterung durch die Web SDK-Erweiterung zu ersetzen.

1. Wählen Sie im linken Navigationsbereich der Tags-Oberfläche die Option **[!UICONTROL Rules]** aus.
1. Wählen Sie eine zu bearbeitende Regel aus.
1. Wählen Sie die Aktion **[!UICONTROL Audience Manager - Set Variables]** aus.
1. Beachten Sie alle in dieser Regel festgelegten Audience Manager-Variablen. Schließen Sie beide in den Dropdown-Menüs festgelegten Variablen und die in benutzerdefiniertem Code festgelegten Variablen ein.
1. Ändern Sie &quot;[!UICONTROL Action Configuration]&quot;in die folgenden Einstellungen:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: Variable aktualisieren
1. Stellen Sie sicher, dass das in Schritt 3 erstellte Datenobjekt in der Dropdown-Liste rechts im Feld **[!UICONTROL Data element]** ausgewählt ist.
1. Setzen Sie die Schlüssel-Wert-Paare des Audience Managers auf die gleichen Werte wie in der Audience Manager-Erweiterung konfiguriert.
1. Nachdem alle Regellogik mit der Web SDK-Erweiterung repliziert wurde, wählen Sie **[!UICONTROL Keep Changes]** aus.
1. Wiederholen Sie diese Schritte für jede Aktionskonfiguration, in der die Audience Manager-Tag-Erweiterung zum Festlegen von Werten verwendet wird.

Die obigen Schritte gelten nur für Regeln, die Werte festlegen. Die folgenden Schritte ersetzen alle Aktionen, die den [!UICONTROL Action Configuration] [!UICONTROL Send Event] verwenden.

1. Wählen Sie eine Regel aus, die ein Web SDK-Ereignis sendet.
1. Wählen Sie den Aktionstyp **[!UICONTROL Send Event]** aus.
1. Ändern Sie &quot;[!UICONTROL Action Configuration]&quot;in die folgenden Einstellungen:
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: [!UICONTROL Send event]
1. Ändern Sie rechts die Aktionseinstellungen in Folgendes:
   * **[!UICONTROL Type]**: Verwenden Sie **[!UICONTROL Web Webpagedetails Page Views]**.
   * **[!UICONTROL Data]**: Wählen Sie das Datenobjekt aus, das Sie in Schritt 3 erstellt haben.
1. Wählen Sie **[!UICONTROL Keep Changes]** aus.
1. Wiederholen Sie diese Schritte für jede Aktionskonfiguration, die Audience Manager zum Senden eines Ereignisses verwendet.

+++

+++**5. Publish - aktualisierte Regeln**

Das Veröffentlichen aktualisierter Regeln folgt demselben Workflow wie jede andere Änderung an der Tag-Konfiguration.

1. Wählen Sie im linken Navigationsbereich der Tags-Oberfläche die Option **[!UICONTROL Publishing Flow]** aus.
1. Wählen Sie **[!UICONTROL Add Library]** aus.
1. Geben Sie diesem Tag einen Namen, z. B. &quot;Aktualisierung auf Web SDK&quot;.
1. Wählen Sie **[!UICONTROL Add All Changed Resources]** aus.
1. Wählen Sie **[!UICONTROL Save]** aus.
1. Der Veröffentlichungs-Workflow zeigt einen orangefarbenen Punkt an, der angibt, dass er erstellt wird. Sobald der Punkt grün wird, sind Ihre Änderungen in Ihrer Entwicklungsumgebung verfügbar.
1. Testen Sie Ihre Änderungen in Ihrer Entwicklungsumgebung, um sicherzustellen, dass alle Regeln ordnungsgemäß ausgelöst werden und dass das Datenobjekt mit den erwarteten Werten gefüllt wird.
1. Wenn die Bibliothek fertig ist, senden Sie sie zur Genehmigung, erstellen Sie sie zum Staging, genehmigen Sie sie schließlich und veröffentlichen Sie sie in der Produktion.

   ![Veröffentlichungsfluss](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Audience Manager-Erweiterung deaktivieren**

Sobald Ihre Tag-Implementierung vollständig in das Web SDK migriert ist, können Sie die Audience Manager-Erweiterung deaktivieren.

1. Wählen Sie im linken Navigationsbereich der Tags-Oberfläche die Option **[!UICONTROL Extensions]** aus.
1. Suchen und wählen Sie die Erweiterung [!UICONTROL Audience Manager] aus. Wählen Sie rechts **[!UICONTROL Disable]** aus.
1. Führen Sie denselben obigen Veröffentlichungsarbeitsablauf aus, um das Entfernen der Erweiterung [!UICONTROL Audience Manager] zu veröffentlichen.
1. Nachdem die Erweiterung in der Produktion deaktiviert wurde, können Sie sie vollständig deinstallieren. Wählen Sie die Erweiterung aus, wählen Sie das Menü mit den drei Punkten auf der rechten Seite aus und klicken Sie dann auf **[!UICONTROL Uninstall]**.
1. Führen Sie denselben obigen Veröffentlichungsarbeitsablauf aus, um diese Änderungen in der Produktion zu veröffentlichen.

+++

An dieser Stelle ist Ihre Audience Manager-Implementierung vollständig auf das Web SDK migriert und bereit, in Zukunft zu Real-Time CDP zu wechseln.
