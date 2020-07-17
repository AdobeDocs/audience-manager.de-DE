---
description: Hinzufügen Sie das Audience Management Module an Adobe Analytics AppMeasurement, um Analytics-Daten an den Audience Manager weiterzuleiten, anstatt dass der DIL-Code (Audience Manager Data Integration Library) ein Pixel von der Seite sendet.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Hinzufügen Sie das Audience Management Module an Adobe Analytics AppMeasurement, um Analytics-Daten an den Audience Manager weiterzuleiten, anstatt dass der DIL-Code (Audience Manager Data Integration Library) ein Pixel von der Seite sendet.
seo-title: Implementieren des Audience Management-Moduls
solution: Audience Manager
title: Implementieren des Audience Management-Moduls
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Integration with Analytics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 5%

---


# How to forward data from [!DNL Adobe Analytics] to [!DNL Audience Manager] {#implement-the-audience-management-module}

Führen Sie die Schritte in diesem Lernprogramm aus, um [!DNL Analytics] Daten an die Seite weiterzuleiten, [!DNL Audience Manager] anstatt dass der [!DNL Audience Manager] ( [!UICONTROL Data Integration Library][!DNL DIL]) Code ein Pixel von der Seite sendet.

>[!TIP]
>
>Es wird empfohlen, [!DNL Adobe Experience Platform Launch] die [!UICONTROL Analytics] Daten zu übermitteln [!DNL Audience Manager]. Durch die Verwendung [!UICONTROL Launch]müssen Sie keinen Code manuell in kopieren, wie auf dieser Seite gezeigt [!DNL AppMeasurement].

## Voraussetzungen {#prereqs}

Zusätzlich zur Aktivierung der Erweiterungen oder Implementierung des in diesem Dokument beschriebenen Codes müssen Sie auch:

* Implement the [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html).
* Aktivieren Sie die [serverseitige Weiterleitung](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) für Report Suites im [!UICONTROL Adobe Analytics Admin Console].

## Implementierung {#implementation}

Es gibt zwei Methoden, um die Datenweiterleitung von [!DNL Adobe Analytics] zu [!DNL Audience Manager]implementieren, je nach der von Ihnen verwendeten Tag-Management-Lösung.

### Implementierung mit [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] empfiehlt die Verwendung der Erweiterung [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) zum Instrumentieren [!DNL Adobe Analytics] und [!DNL Audience Manager] auf Ihren Eigenschaften. In diesem Fall müssen Sie keinen Code manuell kopieren. Stattdessen müssen Sie die Datenfreigabe in der [!DNL Analytics Launch] Erweiterung aktivieren, wie in der Abbildung unten dargestellt. Weitere Informationen finden Sie in der Dokumentation zur [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Wenn Sie die [!DNL Adobe Analytics] Erweiterung installieren, *installieren Sie nicht* auch die [!DNL Audience Manager] Erweiterung. Die Weiterleitung von Daten aus der [!DNL Analytics] Erweiterung ersetzt die [!DNL Audience Manager] Erweiterungsfunktion.

![So aktivieren Sie die Datenfreigabe von der Adobe Analytics Extension in Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementierung mit [!DNL Adobe Digital Tag Management (DTM)] einer anderen Tag-Management-Lösung

>[!WARNING]
>
>[!DNL Adobe] hat Pläne für einen Sonnenuntergang [!DNL DTM] bis Ende 2020 veröffentlicht. Weitere Informationen und eine Planung finden Sie unter [!DNL DTM] Pläne für einen Sunset in den [Adobe-Community-Foren](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset).

So implementieren Sie die [!UICONTROL Audience Management Module] Anwendung mit [Adobe DTM](https://docs.adobe.com/content/help/de-DE/dtm/using/dtm-home.html) oder einer anderen Tag-Management-Lösung:

1. Herunterladen [!UICONTROL AppMeasurement] mit dem [Analytics Code-Manager](https://docs.adobe.com/content/help/de-DE/analytics/admin/admin-tools/code-manager-admin.html) (erfordert Version 1.5 oder höher).
1. Aktualisieren Sie Ihren [!UICONTROL AppMeasurement] Code auf die Version, die in der heruntergeladenen ZIP-Datei enthalten ist.
1. Kopieren Sie den gesamten Code aus `AppMeasurement_Module_AudienceManagement.js` der ZIP-Datei. Fügen Sie sie in die `appMeasurement.js` Datei direkt über dem Text ein, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Hinzufügen den Code, `s.loadModule("AudienceManagement");`direkt über dem `AppMeasurement_Module_AudienceManagement.js` Code, den Sie gerade im vorherigen Schritt hinzugefügt haben.
1. Aktualisieren und kopieren Sie den unten stehenden Code und fügen Sie ihn der `doPlugins` Funktion in Ihrer `AppMeasurement.js` Datei hinzu.

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>Die `audienceManagement.setup` Funktion verwendet Parameter mit der [!DNL Audience Manager] `DIL.create` Funktion, die Sie in diesem Code konfigurieren können. Weitere Informationen zu diesen Parametern finden Sie unter [DIL-Erstellung](../../dil/dil-class-overview/dil-create.md#dil-create).

## Code-Elemente definiert {#code-elements-defined}

Die folgende Tabelle definiert wichtige Variablen im Codebeispiel.

| Parameter | Beschreibung |
|--- |--- |
| `partner` | Erforderlich. Dies ist ein Partnername, der Ihnen zugewiesen wird von [!DNL Adobe]. Es wird manchmal auch als Ihre [!UICONTROL partner ID] Partner-Subdomäne bezeichnet.  Wenden Sie sich an Ihren [!DNL Adobe] Berater oder [Kundendienst](https://helpx.adobe.com/de/marketing-cloud/contact-support.html) , wenn Sie Ihren Partnernamen nicht kennen. |
| `containerNSID` | Erforderlich. Die meisten Kunden können einfach einstellen `"containerNSID":0` . Wenn Ihre Firma jedoch ID-Synchronisierungen mit einem anderen Container anpassen muss, können Sie diese Container-ID hier angeben. |
| `uuidCookie` | Optional. Mit dieser Konfiguration können Sie ein [!DNL Adobe] Cookie in der Erstanbieterdomäne einrichten. Dies [!DNL cookie] enthält die [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Erforderlich. Der `namespace` Parameter ist erforderlich, wenn Sie das [!DNL AudienceManagement] mit [!UICONTROL AppMeasurement] Version 2.10 oder neuer gebündelte Modul verwenden. Für dieses [!UICONTROL AudienceManagement] Modul müssen Sie [!UICONTROL Adobe Experience Platform Identity Service] 3.3 oder höher verwenden. <br><br>Die ID [!UICONTROL Experience Cloud Organization ID] ist die ID, die eine Firma bei der Anmeldung für die [!UICONTROL Experience Cloud]ID bereitstellt. Erfahren Sie mehr über die Organisations-ID Ihrer Firma in [Organisationen und Kontoverknüpfung](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Ergebnisse: Datenweiterleitung an [!DNL Audience Manager] {#results-data-forwarding}

Ihre [!DNL Analytics] Implementierung sendet Daten an [!DNL Audience Manager] , nachdem Sie:

* Aktiviert [!UICONTROL Server-Side Forwarding] (sprechen Sie mit Ihrem Berater über diese Funktion)
* Umsetzung der [!DNL Adobe Experience Platform Identity Service];
* Folgen Sie den Implementierungsschritten in diesem Lernprogramm.

Dieser Prozess sendet Daten an [!DNL Audience Manager]:

* Bei Seitenaufrufen zur Ansicht;
* von verfolgten Links;
* Von Video-Meilenstein- und Heartbeat-Video-Ansichten.

>[!NOTE]
>
>Die Variablen, die an [!DNL Audience Manager] von [!DNL Analytics] verwendet werden, verwenden spezielle Präfixe. Sie müssen diese Präfixe beim Erstellen von [!DNL Audience Manager] Eigenschaften verstehen und berücksichtigen. Weitere Informationen zu diesen Präfixen finden Sie unter [Voraussetzungen für das Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md).
