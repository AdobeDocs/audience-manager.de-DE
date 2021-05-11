---
description: Eine Übersicht über DIL und Funktionsweise.
seo-description: Eine Übersicht über DIL und Funktionsweise.
seo-title: Grundlegendes zur Data Integration Library (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil l, '
solution: Audience Manager
title: Grundlegendes zur Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL-Implementierung
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 17%

---

# Die [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Übersicht, erste Schritte und Codemethoden, die in der [!DNL Audience Manager DIL]-Codebibliothek verfügbar sind.

>[!IMPORTANT]
>
>Ab Version 8.0 (veröffentlicht im August 2018) ist [!UICONTROL DIL] stark von dem [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html), Version 3.3 oder höher abhängig. Es verlässt sich auf das [!DNL ID Service], um ID-Synchronisierungen und URL-Ziele auszulösen. Ein Fehler tritt auf, wenn [!DNL ID Service] fehlt, alt ist oder nicht konfiguriert ist.
>
>Es wird empfohlen, [!DNL Adobe Experience Platform Launch] zu verwenden, um Ihre [!DNL DIL]- und [!DNL Adobe Experience Platform Identity Service]-Bibliotheken zu implementieren und zu verwalten.

Sie können jedoch auch die neuesten Experience Clouden und [!DNL DIL] Versionen von unserer GitHub-Seite herunterladen. Siehe Download-Links unten:

* [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases) herunterladen
* [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Zweck der DIL {#purpose-dil}

[!UICONTROL DIL] ist eine API-Bibliothek. Sie können es als Helfercode für [!DNL Adobe Audience Manager] betrachten. Es ist nicht erforderlich, [!DNL Audience Manager] zu verwenden, aber die Methoden und Funktionen [!UICONTROL DIL] bedeutet, dass Sie keinen eigenen Code entwickeln müssen, um Daten an [!DNL Audience Manager] zu senden. Außerdem unterscheidet sich [!UICONTROL DIL] von der API, die vom [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) bereitgestellt wird. Dieser Dienst wurde entwickelt, um die Identität des Besuchers in verschiedenen [!DNL Experience Cloud]-Lösungen zu verwalten. [!UICONTROL DIL] hingegen wurde für Folgendes entwickelt:

* Führen Sie Ereignis-Aufrufe durch und senden Sie Daten an den [Datenerfassungsserver](../reference/system-components/components-data-collection.md).
* Senden Sie Daten an [Ziele](../features/destinations/destinations.md).

## Abrufen und Implementieren von DIL-Code {#get-implement-dil-code}

[!UICONTROL DIL] Code steht  **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)** zum Download bereit. Bitte beachten Sie, dass [!UICONTROL DIL] ab Version 8.0 (August 2018 veröffentlicht) eine feste Abhängigkeit vom [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), Version 3.3 oder höher aufweist. Es verlässt sich auf die [!DNL ID Service], um ID-Synchronisierungen und [!DNL URL destinations] auszulösen. Ein Fehler tritt auf, wenn [!DNL ID Service] fehlt, alt ist oder nicht konfiguriert ist.

Anstatt mit [!UICONTROL DIL] zu arbeiten und [!DNL Audience Manager] manuell einzurichten, sollten Sie stattdessen [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html) verwenden. [!DNL Adobe Experience Platform Launch] ist das empfohlene Implementierungstool, da es die Codebereitstellung, Platzierung und Versionsverwaltung vereinfacht. Lesen Sie mehr über die [Audience Manager-Erweiterung](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) in [!DNL Adobe Experience Platform Launch].

## Beispielaufruf {#sample-code}

[!UICONTROL DIL] sendet Daten  [!DNL Audience Manager] in einem Ereignis-Aufruf. Ein Ereignis-Aufruf ist eine XML-HTTP-Anforderung von Ihrer Seite. Es wird eine `POST`-Methode verwendet, um Daten im Hauptteil der Anforderung zu senden.

| Ereignis-Aufrufelement | Beschreibung |
|--- |--- |
| URL | DIL-Ereignis-Aufrufe verwenden die folgende Syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Text | Wie im Beispiel unten dargestellt, übergibt DIL Daten als Schlüssel-Wert-Paare. Spezielle Präfixzeichen kennzeichnen die Schlüsselwertpaare als Audience Manager- oder Partnervariablen.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
