---
description: Eine Übersicht über DIL und seine Funktionsweise.
seo-description: Eine Übersicht über DIL und seine Funktionsweise.
seo-title: Die Data Integration Library (DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: Die Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 2%

---


# Erläuterungen zum [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Übersicht, erste Schritte und in der [!DNL Audience Manager DIL] Codebibliothek verfügbare Codemethoden.

>[!IMPORTANT]
>
>Ab Version 8.0 (veröffentlicht August 2018), [!UICONTROL DIL] hat eine feste Abhängigkeit von der [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), Version 3.3 oder höher. Es verlässt sich darauf, ID-Synchronisierungen und URL-Ziele [!DNL ID Service] auszulösen. Es tritt ein Fehler auf, wenn die Variable [!DNL ID Service] fehlt, alt ist oder nicht konfiguriert ist.
>
>Wir empfehlen Ihnen, Ihre Bibliotheken [!DNL Adobe Experience Platform Launch] zu implementieren und zu verwalten [!DNL DIL] und [!DNL Adobe Experience Platform Identity Service] zu verwenden.

Sie können aber auch die neuesten Experience Clouden und [!DNL DIL] Versionen von unserer GitHub-Seite herunterladen. Siehe Download-Links unten:

* Herunterladen des Identitätsdienstes für [Adobe Experience Platformen](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Download [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Zweck der DIL {#purpose-dil}

[!UICONTROL DIL] ist eine API-Bibliothek. Man kann es als Helfercode für [!DNL Adobe Audience Manager]sich vorstellen. Es ist nicht erforderlich, zu verwenden [!DNL Audience Manager], aber die Methoden und Funktionen [!UICONTROL DIL] bietet bedeutet, dass Sie keinen eigenen Code entwickeln müssen, an den Daten gesendet werden [!DNL Audience Manager]. Außerdem [!UICONTROL DIL] unterscheidet sich die vom Identitätsdienst für die [Adobe Experience Platform bereitgestellte API](https://docs.adobe.com/content/help/en/id-service/using/home.html). Dieser Dienst wurde zur lösungsübergreifenden Verwaltung der Besucher-Identität konzipiert. [!DNL Experience Cloud] Dagegen [!UICONTROL DIL] ist

* Führen Sie Ereignis-Aufrufe durch und senden Sie Daten an den [Datenerfassungsserver](../reference/system-components/components-data-collection.md).
* Senden von Daten an [Ziele](../features/destinations/destinations.md).

## DIL-Code abrufen und implementieren {#get-implement-dil-code}

[!UICONTROL DIL] Code steht **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)**zum Download bereit. Bitte beachten Sie, dass ab Version 8.0 (August 2018 veröffentlicht)[!UICONTROL DIL]eine feste Abhängigkeit von der[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), Version 3.3 oder höher, besteht. Es verlässt sich darauf, ID-Synchronisierungen[!DNL ID Service]und[!DNL URL destinations]auszulösen. Es tritt ein Fehler auf, wenn die Variable[!DNL ID Service]fehlt, alt ist oder nicht konfiguriert ist.

Anstatt mit [!UICONTROL DIL] und [!DNL Audience Manager] manuell einzurichten, sollten Sie stattdessen [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) verwenden. [!DNL Adobe Experience Platform Launch] ist das empfohlene Implementierungstool, da es die Codebereitstellung, Platzierung und Versionsverwaltung vereinfacht. Lesen Sie mehr über die [Audience Manager-Erweiterung](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in [!DNL Adobe Experience Platform Launch].

[!DNL Adobe Experience Platform Launch] ist der Nachfolger von [Adobe Dynamic Tag Manager](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) ([!DNL DTM]).

## Beispielaufruf {#sample-code}

[!UICONTROL DIL] sendet Daten an [!DNL Audience Manager] einen Ereignis-Aufruf. Ein Ereignis-Aufruf ist eine XML-HTTP-Anforderung von Ihrer Seite. Es verwendet eine `POST` Methode, um Daten im Hauptteil der Anforderung zu senden.

| Ereignis-Aufrufelement | Beschreibung |
|--- |--- |
| URL | DIL-Ereignis-Aufrufe verwenden die folgende Syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
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