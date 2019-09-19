---
description: Eine Übersicht über DIL und seine Funktionsweise.
seo-description: Eine Übersicht über DIL und seine Funktionsweise.
seo-title: Die Data Integration Library (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil l, '
solution: Audience Manager
title: Die Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Die Data Integration Library (DIL){#understanding-the-data-integration-library-dil}

Übersicht, erste Schritte und in der DIL-Codebibliothek von Audience Manager verfügbare Codemethoden.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Es verlässt sich auf den ID-Dienst, um ID-Synchronisierungen und URL-Ziele auszulösen. Ein Fehler tritt auf, wenn der ID-Dienst fehlt, alt ist oder nicht konfiguriert ist.
>
>Es wird empfohlen, Adobe Launch zur Implementierung und Verwaltung Ihrer DIL- und Experience Cloud ID-Dienst-Bibliotheken zu verwenden.

Sie können jedoch auch die neuesten Experience Cloud- und DIL-Versionen von unserer GitHub-Seite herunterladen. Siehe Download-Links unten:

* Herunterladen des [Experience Cloud ID-Diensts](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Download [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Zweck der DIL {#purpose-dil}

[!UICONTROL DIL] ist eine API-Bibliothek. Man kann es als Helfercode für [!DNL Adobe Audience Manager]sich vorstellen. Es ist nicht erforderlich, zu verwenden [!DNL Audience Manager], aber die Methoden und Funktionen [!UICONTROL DIL] bietet bedeutet, dass Sie keinen eigenen Code entwickeln müssen, an den Daten gesendet werden [!DNL Audience Manager]. Außerdem [!UICONTROL DIL] unterscheidet sich die API vom [Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/). Dieser Dienst wurde zur Verwaltung der Besucheridentität in verschiedenen [!DNL Experience Cloud] Lösungen entwickelt. Dagegen [!UICONTROL DIL] ist

* Führen Sie Ereignisaufrufe durch und senden Sie Daten an den [Datenerfassungsserver](../reference/system-components/components-data-collection.md).
* Daten an [Ziele](../features/destinations/destinations.md)senden

## DIL-Code abrufen und implementieren {#get-implement-dil-code}

[!UICONTROL DIL] Code steht **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)** zum Download bereit. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Es verlässt sich auf den ID-Dienst, um ID-Synchronisierungen und URL-Ziele auszulösen. Ein Fehler tritt auf, wenn der ID-Dienst fehlt, alt ist oder nicht konfiguriert ist.

Anstatt mit [!UICONTROL DIL] Adobe Launch zu arbeiten und es [!DNL Audience Manager] manuell einzurichten, sollten Sie stattdessen [Adobe Launch](https://docs.adobelaunch.com/) verwenden. [!DNL Adobe Launch] ist das empfohlene Implementierungstool, da es die Codebereitstellung, Platzierung und Versionsverwaltung vereinfacht. Lesen Sie mehr über die [Audience Manager-Erweiterung](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in Adobe Launch.

Adobe Launch ist die Nachfolgerin von [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Beispielaufruf {#sample-code}

[!UICONTROL DIL] sendet Daten an [!DNL Audience Manager] einen Ereignisaufruf. Ein Ereignisaufruf ist eine XML-HTTP-Anforderung von Ihrer Seite. Es verwendet eine `POST` Methode, um Daten im Hauptteil der Anforderung zu senden.

| Ereignisaufrufelement | Beschreibung |
|--- |--- |
| URL | DIL-Ereignisaufrufe verwenden die folgende Syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Text | Wie im Beispiel unten dargestellt, übergibt DIL Daten als Schlüssel-Wert-Paare. Spezielle Präfixzeichen kennzeichnen die Schlüssel-Wert-Paare als Audience Manager- oder Partnervariablen.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Siehe auch:
* [Voraussetzungen für das Präfix für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)
* [Unterstützte Attribute für DCS-API-Aufrufe](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Verwandte Links

* [DIL-Anwendungsfälle und Codebeispiele](/help/using/dil/dil-use-cases.md)
* [DIL-Methoden auf Klassenebene](/help/using/dil/dil-class-overview/dil-start.md)
* [DIL-Methoden auf Instanzebene](/help/using/dil/dil-instance-methods.md)
* [DIL-Module](/help/using/dil/dil-modules.md)
* [DIL-Tools](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)