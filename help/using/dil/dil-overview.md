---
description: Ein Überblick über DIL und seine Funktionsweise.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: DIL
solution: Audience Manager
title: Grundlegendes zur Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 1%

---

# Grundlegendes zum [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>Ab Juli 2023 hat Adobe die Entwicklung des [!DNL Data Integration Library (DIL)] und der [!DNL DIL] eingestellt.
>
>Bestehende Kundinnen und Kunden können ihre [!DNL DIL] Implementierung weiterhin nutzen. Adobe wird jedoch keine [!DNL DIL] über diesen Punkt hinaus entwickeln. Kundinnen und Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de) auf ihre langfristige Datenerfassungsstrategie hin zu überprüfen.
>
>Kunden, die nach Juli 2023 neue Datenerfassungsintegrationen implementieren möchten, sollten stattdessen [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de) verwenden.

Übersicht, Erste Schritte und Codemethoden, die in der [!DNL Audience Manager DIL]-Code-Bibliothek verfügbar sind.

>[!IMPORTANT]
>
>Ab Version 8.0 (veröffentlicht im August 2018) ist [!UICONTROL DIL] stark von [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=de), Version 3.3 oder höher abhängig. Sie beruht auf dem [!DNL ID Service], ID-Synchronisierungen und URL-Ziele auszulösen. Ein Fehler tritt auf, wenn der [!DNL ID Service] fehlt, alt oder nicht konfiguriert ist.
>
>Es wird empfohlen, [!DNL Adobe Experience Platform Tags] zur Implementierung und Verwaltung Ihrer [!DNL DIL]- und [!DNL Adobe Experience Platform Identity Service]-Bibliotheken zu verwenden.

Sie können jedoch auch die neuesten Experience Cloud- und [!DNL DIL]-Versionen von unserer GitHub-Seite herunterladen. Siehe Downloadlinks unten:

* [Adobe Experience Platform Identity Service herunterladen](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* [DIL herunterladen](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Zweck von DIL {#purpose-dil}

[!UICONTROL DIL] ist eine API-Bibliothek. Man kann es sich als eine Art Hilfscode für [!DNL Adobe Audience Manager] vorstellen. Es ist nicht erforderlich, [!DNL Audience Manager] zu verwenden, aber die Methoden und Funktionen, die [!UICONTROL DIL] bietet, bedeuten, dass Sie keinen eigenen Code entwickeln müssen, um Daten an [!DNL Audience Manager] zu senden. Außerdem unterscheidet sich [!UICONTROL DIL] von der vom [Adobe Experience Platform Identity Service&rbrace; bereitgestellten &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=de). Dieser Service ist für die Verwaltung der Besucheridentität in verschiedenen [!DNL Experience Cloud] konzipiert. Im Gegensatz dazu ist [!UICONTROL DIL] für Folgendes konzipiert:

* Führen Sie Ereignisaufrufe durch und senden Sie Daten an den [Datenerfassungsserver](../reference/system-components/components-data-collection.md).
* Senden von Daten an [Ziele](../features/destinations/destinations.md).

## Abrufen und Implementieren von DIL-Code {#get-implement-dil-code}

[!UICONTROL DIL] Code kann hier heruntergeladen **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Beachten Sie, dass ab Version 8.0 (veröffentlicht im August 2018) [!UICONTROL DIL] eine feste Abhängigkeit vom [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=de), Version 3.3 oder höher aufweist. Es beruht auf dem [!DNL ID Service], ID-Synchronisationen und -[!DNL URL destinations] auszulösen. Ein Fehler tritt auf, wenn der [!DNL ID Service] fehlt, alt oder nicht konfiguriert ist.

Anstatt mit [!UICONTROL DIL] zu arbeiten und [!DNL Audience Manager] manuell einzurichten, empfehlen wir, stattdessen [Adobe Experience Platform-Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=de) zu verwenden. [!DNL Adobe Experience Platform Tags] ist das empfohlene Implementierungs-Tool, da es die Bereitstellung, Platzierung und Versionsverwaltung von Code vereinfacht. Weitere Informationen zur [Audience Manager-Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=de) finden Sie in [!DNL Adobe Experience Platform Tags].

## Beispielaufruf {#sample-code}

[!UICONTROL DIL] sendet in einem Ereignisaufruf Daten an [!DNL Audience Manager]. Ein Ereignisaufruf ist eine XML-HTTP-Anfrage von Ihrer Seite. Sie verwendet eine `POST` Methode zum Senden von Daten im Hauptteil der Anfrage.

| Ereignisaufrufelement | Beschreibung |
|--- |--- |
| URL | DIL-Ereignisaufrufe verwenden die folgende Syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Textkörper | Wie im folgenden Beispiel gezeigt, übergibt DIL Daten als Schlüssel-Wert-Paare. Spezielle Präfixzeichen identifizieren die Schlüssel-Wert-Paare als Audience Manager- oder Partnervariablen.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Siehe auch:

* [Voraussetzungen für Präfixe für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)
* [Unterstützte Attribute für DCS-API-Aufrufe](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Verwandte Links

* [DIL-Anwendungsfälle und Code-Beispiele](/help/using/dil/dil-use-cases.md)
* [DIL-Methoden auf Klassenebene](/help/using/dil/dil-class-overview/dil-start.md)
* [DIL-Methoden auf Instanzebene](/help/using/dil/dil-instance-methods.md)
* [DIL-Module](/help/using/dil/dil-modules.md)
* [DIL-Tools](/help/using/dil/dil-tools.md)
* [Flash-DIL](/help/using/dil/dil-flash.md)
