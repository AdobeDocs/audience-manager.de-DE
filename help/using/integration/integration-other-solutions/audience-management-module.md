---
description: Fügen Sie das Zielgruppen-Management-Modul zu Adobe Analytics appmeasurement hinzu, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt den DIL-Code (Data Integration Library) von Audience Manager ein Pixel von der Seite senden zu lassen.
keywords: audience analytics; analytics; ssf; serverseitige Weiterleitung
seo-description: Fügen Sie das Zielgruppen-Management-Modul zu Adobe Analytics appmeasurement hinzu, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt den DIL-Code (Data Integration Library) von Audience Manager ein Pixel von der Seite senden zu lassen.
seo-title: Implementieren des Zielgruppen-Management-Moduls
solution: Audience Manager
title: Implementieren des Zielgruppen-Management-Moduls
uuid: 08846427-def 3-4 a 15-88 e 5-08882 d 8 d 57 ce
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Implementieren des Zielgruppen-Management-Moduls {#implement-the-audience-management-module}

Fügen Sie die Daten [!UICONTROL Audience Management Module][!DNL Adobe Analytics][!UICONTROL AppMeasurement] zum Weiterleiten [!DNL Analytics] an Audience Manager hinzu, anstatt den Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL])-Code ein Pixel von der Seite senden zu lassen.

## Voraussetzungen {#prereqs}

Zusätzlich zur Implementierung des in diesem Dokument beschriebenen Codes müssen Sie auch:

* Implementieren Sie den [Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Aktivieren [!UICONTROL Server-Side Forwarding] Sie Report Suites in [!UICONTROL Adobe Analytics Admin Console].

## Implementierung {#implementation}

So implementieren [!UICONTROL Audience Management Module]Sie Folgendes:

1. Herunterladen [!UICONTROL AppMeasurement] mit dem [Analytics Code-Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (Version 1.5 oder höher erforderlich)
1. Aktualisieren Sie Ihren [!UICONTROL AppMeasurement] Code auf die Version, die in der heruntergeladenen ZIP-Datei enthalten ist.
1. Kopieren Sie den gesamten Code aus `AppMeasurement_Module_AudienceManagement.js` der ZIP-Datei. Fügen Sie es in die `appMeasurement.js` Datei direkt über dem Text ein. `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Fügen Sie den Code direkt `s.loadModule("AudienceManagement");`oberhalb des `AppMeasurement_Module_AudienceManagement.js` Codes hinzu, den Sie gerade im vorherigen Schritt hinzugefügt haben.
1. Aktualisieren und kopieren Sie den unten stehenden Code und fügen Sie ihn der `doPlugins` Funktion in Ihrer `AppMeasurement.js` Datei hinzu.

```js
s.AudienceManagement.setup({ 
     "partner":"partner name", 
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
>Die `audienceManagement.setup` Funktion gibt Parameter mit der Funktion Audience Manager `DIL.create` frei, die Sie in diesem Code konfigurieren können. Weitere Informationen zu diesen Parametern finden Sie unter [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Definierte Codeelemente {#code-elements-defined}

Die folgende Tabelle definiert wichtige Variablen im Codebeispiel.

| Parameter | Beschreibung |
|--- |--- |
| `partner` | Erforderlich. Dieser Name wird Ihnen von Adobe zugewiesen. Es wird manchmal als Ihre Partner-ID oder Partner-Subdomäne bezeichnet. Wenden Sie sich an Ihren Adobe-Berater oder [an den Kundendienst,](https://helpx.adobe.com/marketing-cloud/contact-support.html) wenn Sie Ihren Partnernamen nicht kennen. |
| `containerNSID` | Erforderlich. Die meisten Kunden `"containerNSID":0` können einfach festlegen. Wenn Ihr Unternehmen die ID jedoch mit einem anderen Behälter anpassen muss, können Sie diese Behälter-ID hier angeben. |
| `uuidCookie` | Optional. Mit dieser Konfiguration können Sie ein Adobe-Cookie in der Erstanbieterdomäne festlegen. Dieses Cookie enthält die [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Erforderlich. Der `namespace` Parameter ist erforderlich, wenn Sie das audiencemanagement-Modul verwenden, das mit [!UICONTROL AppMeasurement] Version 2.10 oder neuer gebündelt ist. Für dieses [!UICONTROL AudienceManagement] Modul ist es erforderlich, dass Sie [!UICONTROL Experience Cloud ID Service] 3.3 oder neuer verwenden. <br>Die [!UICONTROL Experience Cloud Organization ID] ID, mit der ein Unternehmen bei der Anmeldung für ein [!UICONTROL Experience Cloud]Unternehmen bereitgestellt wird. Ermitteln Sie die Organisations-ID Ihres Unternehmens in [Organisationen und Kontoverknüpfung](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Ergebnisse: Datenweiterleitung an Audience Manager {#results-data-forwarding}

Ihre [!DNL Analytics] Implementierung sendet Daten an Audience Manager, nachdem Sie über folgende Möglichkeiten verfügen:

* Aktiviert [!UICONTROL Server-Side Forwarding] (mit Ihrem Berater über diese Funktion sprechen);
* ID-Dienst wurde implementiert;
* Installed the [!UICONTROL Audience Management Module].

Dieser Prozess sendet Daten [!DNL Audience Manager]an:

* Bei Seitenansichtsaufrufen;
* Aus verfolgten Links;
* Aus Videomessung und Heartbeat-Videoansichten.

>[!NOTE]
>
>Die an Audience Manager gesendeten Variablen verwenden [!DNL Analytics] spezielle Präfixe. Sie müssen diese Präfixe verstehen und berücksichtigen, wenn Sie Audience Manager-Eigenschaften erstellen. Weitere Informationen zu diesen Präfixen finden Sie unter [Voraussetzungen für die Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md).