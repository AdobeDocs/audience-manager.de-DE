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


# Implement the Audience Management Module {#implement-the-audience-management-module}

Add the [!UICONTROL Audience Management Module] to [!DNL Adobe Analytics] [!UICONTROL AppMeasurement] to forward [!DNL Analytics] data to Audience Manager instead of having the Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) code send a pixel from the page.

## Voraussetzungen {#prereqs}

Zusätzlich zur Implementierung des in diesem Dokument beschriebenen Codes müssen Sie auch:

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Enable [!UICONTROL Server-Side Forwarding] for report suites in the [!UICONTROL Adobe Analytics Admin Console].

## Implementierung {#implementation}

To implement the [!UICONTROL Audience Management Module]:

1. Download [!UICONTROL AppMeasurement] using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (requires version 1.5 or later).
1. Update your [!UICONTROL AppMeasurement] code to the version included in the downloaded zip file.
1. Copy all of the code from `AppMeasurement_Module_AudienceManagement.js` from the zip file. Paste it into the `appMeasurement.js` file just above the text, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Add the code, `s.loadModule("AudienceManagement");`, just above the `AppMeasurement_Module_AudienceManagement.js` code you just added in the previous step.
1. Update and copy the code below and add it to the `doPlugins` function in your `AppMeasurement.js` file.

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
>The `audienceManagement.setup` function shares parameters with the Audience Manager `DIL.create` function, which you can configure in this code. For more information about these parameters, see [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Code Elements Defined {#code-elements-defined}

Die folgende Tabelle definiert wichtige Variablen im Codebeispiel.

| Parameter | Beschreibung |
|--- |--- |
| `partner` | Erforderlich. Dieser Name wird Ihnen von Adobe zugewiesen. Es wird manchmal als Ihre Partner-ID oder Partner-Subdomäne bezeichnet. Contact your Adobe consultant or [Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html) if you don't know your partner name. |
| `containerNSID` | Erforderlich. Most customers can just set  `"containerNSID":0` . Wenn Ihr Unternehmen die ID jedoch mit einem anderen Behälter anpassen muss, können Sie diese Behälter-ID hier angeben. |
| `uuidCookie` | Optional. Mit dieser Konfiguration können Sie ein Adobe-Cookie in der Erstanbieterdomäne festlegen. This cookie contains the [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Erforderlich. The `namespace` parameter is required if you use the AudienceManagement module bundled with [!UICONTROL AppMeasurement] version 2.10 or newer. This [!UICONTROL AudienceManagement] module requires that you use [!UICONTROL Experience Cloud ID Service] 3.3 or newer. <br>Die [!UICONTROL Experience Cloud Organization ID] ID, mit der ein Unternehmen bei der Anmeldung für ein [!UICONTROL Experience Cloud]Unternehmen bereitgestellt wird. Find out your company's Organization ID in [Organizations and Account Linking](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Results: Data Forwarding to Audience Manager {#results-data-forwarding}

Your [!DNL Analytics] implementation sends data to Audience Manager after you have:

* Enabled [!UICONTROL Server-Side Forwarding] (talk to your consultant about this feature);
* ID-Dienst wurde implementiert;
* Installed the [!UICONTROL Audience Management Module].

This process sends data to [!DNL Audience Manager]:

* Bei Seitenansichtsaufrufen;
* Aus verfolgten Links;
* Aus Videomessung und Heartbeat-Videoansichten.

>[!NOTE]
>
>The variables sent to Audience Manager from [!DNL Analytics] use special prefixes. Sie müssen diese Präfixe verstehen und berücksichtigen, wenn Sie Audience Manager-Eigenschaften erstellen. For more information on these prefixes, see [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md).