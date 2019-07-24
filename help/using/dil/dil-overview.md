---
description: Eine Übersicht über DIL und deren Funktionsweise.
seo-description: Eine Übersicht über DIL und deren Funktionsweise.
seo-title: Grundlegendes zur Data Integration Library (DIL)
solution: Audience Manager
title: Grundlegendes zur Data Integration Library (DIL)
uuid: 77 b 12 f 35-81 e 4-4639-ada 6-bf 982 f 27 b 36 e
translation-type: tm+mt
source-git-commit: 8f2cbf8a31335762f03cad278114d9ab7c520763

---


# Understanding the Data Integration Library (DIL){#understanding-the-data-integration-library-dil}

Übersicht, erste Schritte und Codemethoden, die in der DIL-Code-Bibliothek von Audience Manager verfügbar sind.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Es basiert auf dem ID-Dienst, um ID-Synchronisierungen und URL-Ziele zu auslösen. Es tritt ein Fehler auf, wenn der ID-Dienst fehlt, alt oder nicht konfiguriert ist.
>
>Wir empfehlen Ihnen, mit Adobe Launch Ihre DIL- und Experience Cloud ID-Dienstbibliotheken zu implementieren und zu verwalten.

Sie können jedoch auch die neuesten Versionen von Experience Cloud und DIL von unserer github-Seite herunterladen. Siehe Download-Links unten:

* [Experience Cloud ID-Dienst herunterladen](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* [DIL herunterladen](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Purpose of DIL {#purpose-dil}

[!UICONTROL DIL] ist eine API-Bibliothek. You can think it as a body of helper code for [!DNL Adobe Audience Manager]. It is not required to use [!DNL Audience Manager], but the methods and functions [!UICONTROL DIL] provides means you don't have to develop your own code to send data to [!DNL Audience Manager]. Also, [!UICONTROL DIL] is different than the API provided by the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/). That service is designed to manage visitor identity across different [!DNL Experience Cloud] solutions. [!UICONTROL DIL] Ist dagegen beabsichtigt:

* Make event calls and send data to the [Data Collection Server](../reference/system-components/components-data-collection.md).
* Send data to [destinations](../features/destinations/destinations.md).

## Getting and Implementing DIL Code {#get-implement-dil-code}

[!UICONTROL DIL] Code steht **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)** zur Verfügung. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Es basiert auf dem ID-Dienst, um ID-Synchronisierungen und URL-Ziele zu auslösen. Es tritt ein Fehler auf, wenn der ID-Dienst fehlt, alt oder nicht konfiguriert ist.

Rather than work with [!UICONTROL DIL] and set up [!DNL Audience Manager] manually, we recommend that you use [Adobe Launch](https://docs.adobelaunch.com/) instead. [!DNL Adobe Launch] ist das empfohlene Implementierungstool, da es die Codebereitstellung, Platzierung und Version vereinfacht. Read more about the [Audience Manager extension](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in Adobe Launch.

Adobe Launch is the successor to [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Sample Call {#sample-code}

[!UICONTROL DIL] sendet Daten [!DNL Audience Manager] an einen Ereignisaufruf. Ein Ereignisaufruf ist eine XML-HTTP-Anforderung von Ihrer Seite. It uses a `POST` method to send data in the body of the request.

| Ereignisaufruf-Element | Beschreibung |
|--- |--- |
| URL | DIL event calls use the following syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Text | Wie in Beispiel unten gezeigt, übergibt DIL Daten als Schlüssel-Wert-Paare. Special prefix characters identify the key-value pairs as Audience Manager or partner variables.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Siehe auch:
* [Präfix für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)
* [Unterstützte Attribute für DCS-API-Aufrufe](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Verwandte Links

* [DIL-Anwendungsfälle und Codebeispiele](/help/using/dil/dil-use-cases.md)
* [DIL-Methoden auf Klassenebene](/help/using/dil/dil-class-overview/dil-start.md)
* [DIL-Methoden auf Instanzebene](/help/using/dil/dil-instance-methods.md)
* [DIL-Module](/help/using/dil/dil-modules.md)
* [DIL-Werkzeuge](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)