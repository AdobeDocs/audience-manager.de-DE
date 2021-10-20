---
description: Ein Überblick über DIL und seine Funktionsweise.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, '
solution: Audience Manager
title: Grundlegendes zur Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 11%

---

# Grundlagen zum [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Überblick, erste Schritte und verfügbare Codemethoden in der [!DNL Audience Manager DIL] Code-Bibliothek.

>[!IMPORTANT]
>
>Ab Version 8.0 (veröffentlicht im August 2018), [!UICONTROL DIL] hat eine starke Abhängigkeit von der [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), Version 3.3 oder höher. Sie beruht auf der [!DNL ID Service] , um ID-Synchronisierungen und URL-Ziele auszulösen. Wenn die Variable [!DNL ID Service] fehlt, alt oder nicht konfiguriert ist.
>
>Es wird empfohlen, [!DNL Adobe Experience Platform Tags] implementieren und verwalten Sie [!DNL DIL] und [!DNL Adobe Experience Platform Identity Service] -Bibliotheken.

Sie können jedoch auch das neueste Experience Cloud herunterladen und [!DNL DIL] von unserer GitHub-Seite veröffentlicht. Siehe Downloadlinks unten:

* Laden Sie die [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Download [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Zweck des DIL {#purpose-dil}

[!UICONTROL DIL] ist eine API-Bibliothek. Sie können ihn als Hilfecode für [!DNL Adobe Audience Manager]. Es ist nicht erforderlich, [!DNL Audience Manager], aber die Methoden und Funktionen [!UICONTROL DIL] bietet bedeutet, dass Sie keinen eigenen Code entwickeln müssen, um Daten an [!DNL Audience Manager]. Außerdem [!UICONTROL DIL] unterscheidet sich von der von der [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html). Dieser Dienst dient der Verwaltung der Besucheridentität über verschiedene [!DNL Experience Cloud] Lösungen. Im Gegensatz dazu [!UICONTROL DIL] ist so konzipiert, dass

* Ereignisaufrufe durchführen und Daten an die [Datenerfassungsserver](../reference/system-components/components-data-collection.md).
* Senden von Daten an [Ziele](../features/destinations/destinations.md).

## Abrufen und Implementieren von DIL-Code {#get-implement-dil-code}

[!UICONTROL DIL] -Code kann heruntergeladen werden **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Beachten Sie, dass ab Version 8.0 (veröffentlicht im August 2018) [!UICONTROL DIL] hat eine starke Abhängigkeit von der [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), Version 3.3 oder höher. Sie beruht auf der [!DNL ID Service] ID-Synchronisierungen auslösen und [!DNL URL destinations]. Wenn die Variable [!DNL ID Service] fehlt, alt oder nicht konfiguriert ist.

Anstatt mit [!UICONTROL DIL] und [!DNL Audience Manager] verwenden, empfehlen wir, [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) anstatt. [!DNL Adobe Experience Platform Tags] ist das empfohlene Implementierungstool, da es die Codebereitstellung, -platzierung und -versionsverwaltung vereinfacht. Mehr über [Audience Manager-Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) in [!DNL Adobe Experience Platform Tags].

## Beispielaufruf {#sample-code}

[!UICONTROL DIL] sendet Daten an [!DNL Audience Manager] in einem Ereignisaufruf. Ein Ereignisaufruf ist eine XML-HTTP-Anforderung von Ihrer Seite. Es verwendet eine `POST` -Methode zum Senden von Daten im Hauptteil der Anfrage.

| Ereignisaufrufelement | Beschreibung |
|--- |--- |
| URL | DIL-Ereignisaufrufe verwenden die folgende Syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Text | Wie im folgenden Beispiel gezeigt, übergibt DIL Daten als Schlüssel-Wert-Paare. Durch Sonderpräfixzeichen werden die Schlüssel-Wert-Paare als Audience Manager- oder Partnervariablen identifiziert.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Siehe auch:
* [Anforderungen an Präfixe für Schlüsselvariablen](../features/traits/trait-variable-prefixes.md)
* [Unterstützte Attribute für DCS-API-Aufrufe](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Verwandte Links

* [DIL-Anwendungsfälle und Code-Beispiele](/help/using/dil/dil-use-cases.md)
* [DIL-Methoden auf Klassenebene ](/help/using/dil/dil-class-overview/dil-start.md)
* [DIL-Methoden auf Instanzebene](/help/using/dil/dil-instance-methods.md)
* [DIL-Module](/help/using/dil/dil-modules.md)
* [DIL-Tools](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)
