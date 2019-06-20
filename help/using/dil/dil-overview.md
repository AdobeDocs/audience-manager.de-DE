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


# Grundlegendes zur Data Integration Library (DIL){#understanding-the-data-integration-library-dil}

Übersicht, erste Schritte und Codemethoden, die in der DIL-Code-Bibliothek von Audience Manager verfügbar sind.

>[!IMPORTANT]
>
>Ab Version 8.0 (August 2018 veröffentlicht) hat die [!UICONTROL DIL] Abhängigkeit von [der Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/), Version 3.3 oder höher eine starke Abhängigkeit. Es basiert auf dem ID-Dienst, um ID-Synchronisierungen und URL-Ziele zu auslösen. Es tritt ein Fehler auf, wenn der ID-Dienst fehlt, alt oder nicht konfiguriert ist.
>
>Wir empfehlen Ihnen, mit Adobe Launch Ihre DIL- und Experience Cloud ID-Dienstbibliotheken zu implementieren und zu verwalten.

Sie können jedoch auch die neuesten Versionen von Experience Cloud und DIL von unserer github-Seite herunterladen. Siehe Download-Links unten:

* [Experience Cloud ID-Dienst herunterladen](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* [DIL herunterladen](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Zweck von DIL {#purpose-dil}

[!UICONTROL DIL] ist eine API-Bibliothek. Sie können ihn als Hilfslinie für [!DNL Adobe Audience Manager]den Hilfecode vorstellen. Es ist nicht erforderlich [!DNL Audience Manager], aber die Methoden und Funktionen [!UICONTROL DIL] bieten eine Möglichkeit, dass Sie keinen eigenen Code entwickeln müssen, um Daten zu senden [!DNL Audience Manager]. Außerdem [!UICONTROL DIL] unterscheidet sich die API von der vom [Experience Cloud ID-Dienst bereitgestellten API](https://marketing.adobe.com/resources/help/en_US/mcvid/). Dieser Dienst dient zur Verwaltung der Besucheridentität über verschiedene [!DNL Experience Cloud] Lösungen hinweg. [!UICONTROL DIL] Ist dagegen beabsichtigt:

* Treffen Sie Ereignisaufrufe und senden Sie Daten an den [Datenerfassungsserver](../reference/system-components/components-data-collection.md).
* Senden Sie Daten an [Ziele](../features/destinations/destinations.md).

## Abrufen und Implementieren von DIL-Code {#get-implement-dil-code}

[!UICONTROL DIL] Code steht **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)** zur Verfügung. Beachten Sie, dass ab Version 8.0 (August 2018 veröffentlicht) eine starke [!UICONTROL DIL] Abhängigkeit vom [Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/), Version 3.3 oder höher, besteht. Es basiert auf dem ID-Dienst, um ID-Synchronisierungen und URL-Ziele zu auslösen. Es tritt ein Fehler auf, wenn der ID-Dienst fehlt, alt oder nicht konfiguriert ist.

Anstatt mit manuell zu arbeiten [!UICONTROL DIL] und [!DNL Audience Manager] manuell einzurichten, empfehlen wir stattdessen [, Adobe Launch](https://docs.adobelaunch.com/) zu verwenden. [!DNL Adobe Launch] ist das empfohlene Implementierungstool, da es die Codebereitstellung, Platzierung und Version vereinfacht. Weitere Informationen zur [Audience Manager Extension](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in Adobe Launch.

Adobe Launch ist der Nachfolger von [Adobe Dynamischer Tag-Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Beispielaufruf {#sample-code}

[!UICONTROL DIL] sendet Daten [!DNL Audience Manager] an einen Ereignisaufruf. Ein Ereignisaufruf ist eine XML-HTTP-Anforderung von Ihrer Seite. Sie verwendet eine `POST` Methode zum Senden von Daten im Textkörper der Anforderung.

| Ereignisaufruf-Element | Beschreibung |
|--- |--- |
| URL | DIL-Ereignisaufrufe verwenden die folgende Syntax: `https://adobe.demdex.net/event?_ts =`*`UNIX UTC timestamp`* |
| Text | Wie in Beispiel unten gezeigt, übergibt DIL Daten als Schlüssel-Wert-Paare. Spezielle Präfixzeichen identifizieren die Schlüssel-Wert-Paare als Audience Manager oder Partnervariablen.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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