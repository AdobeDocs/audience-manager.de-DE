---
description: Fügen Sie das Zielgruppen-Management-Modul zu Adobe Analytics AppMeasurement hinzu, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager Data Integration Library (DIL)-Code ein Pixel von der Seite sendet.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Fügen Sie das Zielgruppen-Management-Modul zu Adobe Analytics AppMeasurement hinzu, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager Data Integration Library (DIL)-Code ein Pixel von der Seite sendet.
seo-title: Implementieren des Zielgruppen-Management-Moduls
solution: Audience Manager
title: Implementieren des Zielgruppen-Management-Moduls
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: d6bfffa97813eeafd7e478f0520b2a62eb63cb94

---


# Implementieren des Zielgruppen-Management-Moduls {#implement-the-audience-management-module}

Fügen Sie die [!UICONTROL Audience Management Module] zu [!DNL Adobe Analytics] hinzu, um [!UICONTROL AppMeasurement] Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager [!DNL Analytics] ([!UICONTROL Data Integration Library][!UICONTROL DIL] )-Code ein Pixel von der Seite sendet.

>[!NOTE]
>
>Die Anweisungen auf dieser Seite beziehen sich auf Implementierungen mit [Adobe Digital Tag Manager (DTM)](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) oder einer anderen Tag-Management-Lösung, *außer* [Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html). Es wird empfohlen, Adobe Launch zu verwenden. Bei Verwendung von Launch müssen Sie keinen Code manuell kopieren, wie auf dieser Seite gezeigt.

## Voraussetzungen {#prereqs}

Zusätzlich zur Implementierung des in diesem Dokument beschriebenen Codes müssen Sie auch:

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Aktivieren Sie [!UICONTROL Server-Side Forwarding] für Report Suites im [!UICONTROL Adobe Analytics Admin Console].

## Implementierung {#implementation}

So implementieren Sie [!UICONTROL Audience Management Module]:

1. Herunterladen [!UICONTROL AppMeasurement] mit dem [Analytics-Code-Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (Version 1.5 oder höher erforderlich).
1. Aktualisieren Sie Ihren [!UICONTROL AppMeasurement] Code auf die in der heruntergeladenen ZIP-Datei enthaltene Version.
1. Kopieren Sie den gesamten Code aus `AppMeasurement_Module_AudienceManagement.js` der ZIP-Datei. Fügen Sie sie in die `appMeasurement.js` Datei direkt über dem Text ein, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Fügen Sie den Code `s.loadModule("AudienceManagement");`direkt über dem `AppMeasurement_Module_AudienceManagement.js` Code hinzu, den Sie im vorherigen Schritt hinzugefügt haben.
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
>Die `audienceManagement.setup` Funktion verwendet Parameter mit der `DIL.create` Funktion Audience Manager, die Sie in diesem Code konfigurieren können. Weitere Informationen zu diesen Parametern finden Sie unter [DIL-Erstellung](../../dil/dil-class-overview/dil-create.md#dil-create).

## Code-Elemente definiert {#code-elements-defined}

Die folgende Tabelle definiert wichtige Variablen im Codebeispiel.

| Parameter | Beschreibung |
|--- |--- |
| `partner` | Erforderlich. Dies ist ein von Adobe zugewiesener Name des Partners. Manchmal wird sie als "Partner-ID"oder "Partner-Subdomäne"bezeichnet.  Wenden Sie sich an Ihren Adobe-Berater oder [Kundendienst](https://helpx.adobe.com/marketing-cloud/contact-support.html) , wenn Sie Ihren Partnernamen nicht kennen. |
| `containerNSID` | Erforderlich. Die meisten Kunden können einfach einstellen `"containerNSID":0` . Wenn Ihr Unternehmen jedoch ID-Synchronisierungen mit einem anderen Behälter anpassen muss, können Sie diese Behälter-ID hier angeben. |
| `uuidCookie` | Optional. Mit dieser Konfiguration können Sie ein Adobe-Cookie in der Erstanbieterdomäne einrichten. Dieses Cookie enthält die [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Erforderlich. Der `namespace` Parameter ist erforderlich, wenn Sie das AudienceManagement-Modul mit [!UICONTROL AppMeasurement] Version 2.10 oder neuer verwenden. Für dieses [!UICONTROL AudienceManagement] Modul müssen Sie [!UICONTROL Experience Cloud ID Service] 3.3 oder höher verwenden. <br> Die ID [!UICONTROL Experience Cloud Organization ID] ist die ID, die ein Unternehmen bei der Anmeldung für die [!UICONTROL Experience Cloud]ID erhält. Erfahren Sie mehr über die Organisations-ID Ihres Unternehmens in [Organisationen und Kontoverknüpfung](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Ergebnisse: Datenweiterleitung an Audience Manager {#results-data-forwarding}

Ihre [!DNL Analytics] Implementierung sendet Daten an Audience Manager, nachdem Sie Folgendes haben:

* Aktiviert [!UICONTROL Server-Side Forwarding] (sprechen Sie mit Ihrem Berater über diese Funktion)
* Implementierung des ID-Diensts;
* Installation [!UICONTROL Audience Management Module].

Dieser Prozess sendet Daten an [!DNL Audience Manager]:

* Aufrufe bei Seitenansichten;
* von verfolgten Links;
* Von Video-Meilenstein- und Heartbeat-Videoansichten.

>[!NOTE]
>
>Die Variablen, die an Audience Manager gesendet werden, [!DNL Analytics] verwenden spezielle Präfixe. Sie müssen diese Präfixe beim Erstellen von Audience Manager-Eigenschaften verstehen und berücksichtigen. Weitere Informationen zu diesen Präfixen finden Sie unter [Voraussetzungen für das Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md).