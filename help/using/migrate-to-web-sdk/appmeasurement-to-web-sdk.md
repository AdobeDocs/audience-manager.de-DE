---
title: Aktualisieren Sie Ihre Datenerfassungsbibliothek für Audience Manager von der AppMeasurement JavaScript-Bibliothek in die Web SDK JavaScript-Bibliothek.
description: Machen Sie sich mit den Schritten zur Aktualisierung Ihrer Datenerfassungsbibliothek für den Audience Manager von der AppMeasurement JavaScript-Bibliothek zur Web SDK JavaScript-Bibliothek vertraut.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---

# Aktualisieren Sie Ihre Datenerfassungsbibliothek für den Audience Manager von der AppMeasurement JavaScript-Bibliothek in die Web SDK JavaScript-Bibliothek.

## Vorgesehene Zielgruppe {#intended-audience}

Diese Seite ist für Audience Manager gedacht, die AppMeasurement verwenden, um Webkollektionsdaten in Audience Manager zu importieren. Kunden, die die Tag-Erweiterung [Audience Manager ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) verwenden, lesen das Handbuch, in dem beschrieben wird, wie Sie Ihre Datenerfassungsbibliothek für Audience Manager [ von der Audience Manager-Tag-Erweiterung zur Web SDK-Tag-Erweiterung ](dil-extension-to-web-sdk.md) aktualisieren.

## Vorteile und Nachteile dieses Implementierungspfads

Die Verwendung dieses Migrationsansatzes hat sowohl Vor- als auch Nachteile. Legen Sie bei jeder Option sorgfältig ab, welcher Ansatz für Ihr Unternehmen am besten geeignet ist.

| Vorteile | Nachteile |
| --- | --- |
| <ul><li>**Verwendet Ihre vorhandene Implementierung**: Dieser Ansatz erfordert zwar einige Implementierungsänderungen, erfordert jedoch keine völlig neue Implementierung. Sie können Ihre vorhandene Datenschicht und Ihren Code mit minimalen Änderungen an der Implementierungslogik verwenden.</li><li>**Kein Schema erforderlich**: Für diese Phase der Migration zum Web SDK benötigen Sie kein XDM-Schema. Stattdessen können Sie das `data` -Objekt ausfüllen, das Daten direkt an Audience Manager sendet. Nachdem die Migration zum Web SDK abgeschlossen ist, können Sie ein Schema für Ihre Organisation erstellen und die Datastraam-Zuordnung verwenden, um die entsprechenden XDM-Felder auszufüllen. Wenn in dieser Phase des Migrationsprozesses ein Schema erforderlich ist, muss Ihr Unternehmen ein Audience Manager-XDM-Schema verwenden. Die Verwendung dieses Schemas erschwert es Ihrem Unternehmen, in Zukunft Ihr eigenes Schema zu verwenden.</li></ul> | <ul><li>**Technische Schulden bei der Implementierung**: Da dieser Ansatz eine modifizierte Form Ihrer bestehenden Implementierung verwendet, kann es schwieriger sein, die Implementierungslogik zu verfolgen und bei Bedarf zukünftige Änderungen vorzunehmen.</li><li>**Erfordert Zuordnung zum Senden von Daten an Platform**: Wenn Ihr Unternehmen für die Verwendung von Real-Time CDP bereit ist, müssen Sie Daten an einen Datensatz in Adobe Experience Platform senden. Diese Aktion erfordert, dass jedes Feld im `data` -Objekt ein Eintrag im Tool für die Datenasterzuordnung ist, der ihn einem XDM-Schemafeld zuordnet. Die Zuordnung muss nur einmal für diesen Workflow durchgeführt werden. Es müssen keine Implementierungsänderungen vorgenommen werden. Es handelt sich jedoch um einen zusätzlichen Schritt, der beim Senden von Daten in ein XDM-Objekt nicht erforderlich ist.</li></ul> |

Adobe empfiehlt, diesem Implementierungspfad in den folgenden Szenarien zu folgen:

* Sie verfügen über eine vorhandene Implementierung mithilfe der Adobe Analytics AppMeasurement JavaScript-Bibliothek. Wenn Sie über eine Implementierung mit der Audience Manager-Tag-Erweiterung verfügen, folgen Sie stattdessen dem Befehl &quot;[Migrieren von der Audience Manager-Tag-Erweiterung zur Web SDK-Tag-Erweiterung](dil-extension-to-web-sdk.md)&quot;.
* Sie beabsichtigen, Real-Time CDP in Zukunft zu verwenden, möchten Ihre Audience Manager-Implementierung jedoch nicht von Grund auf durch eine Web SDK-Implementierung ersetzen. Die Ersetzung Ihrer Implementierung durch das Web SDK erfordert den größten Aufwand, bietet aber auch die praktikabelste langfristige Implementierungsarchitektur. Wenn Ihr Unternehmen bereit ist, die Implementierung eines sauberen Web SDK durchzuführen, finden Sie weitere Informationen in der [Web SDK-Dokumentation](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) .

## Schritte für die Migration zum Web SDK

Die folgenden Schritte enthalten konkrete Ziele, auf die wir hinarbeiten müssen. Klicken Sie auf jeden Schritt, um detaillierte Anweisungen dazu zu erhalten.

+++**1. Erstellen und Konfigurieren eines Datastreams**

Erstellen Sie einen Datenspeicher in der Adobe Experience Platform-Datenerfassung. Wenn Sie Daten an diesen Datastream senden, leitet er Daten an Audience Manager weiter. Künftig leitet derselbe Datenspeicher Daten an Real-Time CDP weiter.

1. Navigieren Sie zu [experience.adobe.com](https://experience.adobe.com) und melden Sie sich mit Ihren Anmeldedaten an.
1. Verwenden Sie die Startseite oder die Produktselektor oben rechts, um zu **[!UICONTROL Data Collection]** zu navigieren.
1. Wählen Sie im linken Navigationsbereich **[!UICONTROL Datastreams]** aus.
1. Wählen Sie **[!UICONTROL New Datastream]** aus.
1. Geben Sie den gewünschten Namen ein und wählen Sie dann **[!UICONTROL Save]** aus.
1. Nachdem der Datastream erstellt wurde, wählen Sie **[!UICONTROL Add Service]** aus.
1. Wählen Sie im Dropdown-Menü Dienst die Option **[!UICONTROL Audience Manager]** aus.

   ![Audience Manager-Dienst hinzufügen](assets/add-service.png) {style="border:1px solid lightslategray"}

Ihr Datastream kann jetzt Daten empfangen und an Audience Manager weitergeben. Notieren Sie die Datastream-ID, da diese ID für die Konfiguration des Web SDK im Code erforderlich ist.

+++

+++**2. Installieren der Web SDK JavaScript-Bibliothek**

Weitere Informationen und zu verwendende Codeblöcke finden Sie unter [Installieren des Web SDK mit der JavaScript-Bibliothek](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) . Referenzieren Sie die neueste Version von `alloy.js` , damit die zugehörigen Methodenaufrufe verwendet werden können.

+++

+++**3. Web SDK** konfigurieren

Richten Sie Ihre Implementierung so ein, dass sie auf den in Schritt 1 erstellten Datastream verweist, indem Sie den Web SDK-Befehl [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) verwenden. Der Befehl `configure` muss auf jeder Seite festgelegt sein, damit Sie ihn neben den Bibliotheksinstallationscode einfügen können.

Verwenden Sie die Eigenschaften [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) und [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) im Web SDK `configure` -Befehl:

* Stellen Sie `edgeConfigId` auf die aus dem vorherigen Schritt abgerufene Datastream-ID ein.
* Stellen Sie die `orgId` auf die IMS-Organisations-ID Ihres Unternehmens ein.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Sie können optional andere Eigenschaften im Befehl [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) entsprechend den Implementierungsanforderungen Ihres Unternehmens festlegen.

+++

+++**4. Aktualisieren der Code-Logik zur Verwendung einer JSON-Payload**

Ändern Sie die Implementierung Ihres Audience Managers so, dass sie nicht auf `AppMeasurement.js` oder das `s` -Objekt angewiesen ist. Legen Sie stattdessen Variablen in ein korrekt formatiertes JavaScript-Objekt fest, das beim Senden an Adobe in ein JSON-Objekt konvertiert wird. Die Festlegung einer [Datenschicht](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer) auf Ihrer Site ist bei der Festlegung von Werten äußerst hilfreich, da Sie weiterhin auf dieselben Werte verweisen können.

Um Daten an Audience Manager zu senden, muss die Web SDK-Payload `data.__adobe.audiencemanager` verwenden, wobei alle Analysevariablen in diesem Objekt festgelegt sind. Variablen in diesem Objekt verwenden identische Namen und Formate wie ihre AppMeasurement-Variablen-Entsprechungen. Wenn Sie beispielsweise die Variable `products` festlegen, teilen Sie sie nicht wie bei XDM in einzelne Objekte. Fügen Sie ihn stattdessen als Zeichenfolge ein, die genau ist, wenn Sie die Variable `s.products` festlegen:

```json
{
  "data": {
    "__adobe": {
      "audiencemanager": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

Letztlich enthält diese Payload alle gewünschten Werte und alle Verweise auf das `s` -Objekt in Ihrer Implementierung werden entfernt. Sie können alle von JavaScript bereitgestellten Ressourcen verwenden, um dieses Payload-Objekt festzulegen, einschließlich der Punktnotation zum Festlegen einzelner Werte.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {audiencemanager: {}}}};
dataObj.data.__adobe.audiencemanager.pageName = window.document.title;
dataObj.data.__adobe.audiencemanager.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{audiencemanager:{...a}}}};
```

+++

+++**5. Methodenaufrufe für die Verwendung des Web SDK aktualisieren**

Aktualisieren Sie alle Instanzen, in denen Sie [`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) und [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method) aufrufen, und ersetzen Sie sie durch den Befehl [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) . Es gibt drei Szenarien, die zu berücksichtigen sind:

* **Seitenansichts-Tracking**: Ersetzen Sie den Seitenansichts-Tracking-Aufruf durch den Web SDK `sendEvent` -Befehl:

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Automatische Linktracking**: Die Konfigurationseigenschaft [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) ist standardmäßig aktiviert. Es werden automatisch die richtigen Linktracking-Variablen festgelegt, um Daten an den Audience Manager zu senden. Wenn Sie das automatische Linktracking deaktivieren möchten, legen Sie diese Eigenschaft im Befehl [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) auf `false` fest.

* **Manuelles Linktracking**: Das Web SDK verfügt nicht über separate Befehle zwischen Seitenansichts- und Nicht-Seitenansichtsaufrufen. Geben Sie diese Unterscheidung im Payload-Objekt an.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.audiencemanager.linkName = "Example custom link";
  dataObj.data.__adobe.audiencemanager.linkType = "o";
  dataObj.data.__adobe.audiencemanager.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. Validieren und Veröffentlichen von Änderungen**

Nachdem Sie alle Verweise auf AppMeasurement und das Objekt `s` entfernt haben, veröffentlichen Sie Ihre Änderungen in Ihrer Entwicklungsumgebung, um zu überprüfen, ob die neue Implementierung funktioniert. Nachdem Sie überprüft haben, ob alles ordnungsgemäß funktioniert, können Sie Ihre Aktualisierungen in der Produktion veröffentlichen.

Bei richtiger Migration ist `AppMeasurement.js` nicht mehr auf Ihrer Site erforderlich und alle Verweise auf dieses Skript können entfernt werden.

+++

An dieser Stelle ist Ihre Audience Manager-Implementierung vollständig auf das Web SDK migriert und bereit, in Zukunft zu Real-Time CDP zu wechseln.
