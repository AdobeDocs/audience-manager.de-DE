---
description: Ein Überblick über DIL und seine Funktionsweise.
seo-description: Ein Überblick über DIL und seine Funktionsweise.
seo-title: Grundlegendes zur Data Integration Library (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, '
solution: Audience Manager
title: Grundlegendes zur Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL-Implementierung
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 17%

---

# Verstehen des [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Überblick, erste Schritte und Codemethoden, die in der [!DNL Audience Manager DIL] -Codebibliothek verfügbar sind.

>[!IMPORTANT]
>
>Ab Version 8.0 (veröffentlicht im August 2018) ist [!UICONTROL DIL] stark von [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html), Version 3.3 oder höher abhängig. Sie verlässt sich darauf, dass [!DNL ID Service] ID-Synchronisierungen und URL-Ziele auslöst. Ein Fehler tritt auf, wenn [!DNL ID Service] fehlt, alt ist oder nicht konfiguriert ist.
>
>Es wird empfohlen, [!DNL Adobe Experience Platform Launch] zu verwenden, um Ihre [!DNL DIL]- und [!DNL Adobe Experience Platform Identity Service]-Bibliotheken zu implementieren und zu verwalten.

Sie können jedoch auch die neuesten Experience Cloud- und [!DNL DIL]-Versionen von unserer GitHub-Seite herunterladen. Siehe Downloadlinks unten:

* Laden Sie den [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases) herunter.
* [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases) herunterladen

## Zweck der DIL {#purpose-dil}

[!UICONTROL DIL] ist eine API-Bibliothek. Sie können sich dies als Hilfecode für [!DNL Adobe Audience Manager] vorstellen. Es ist nicht erforderlich [!DNL Audience Manager] zu verwenden, aber die Methoden und Funktionen [!UICONTROL DIL] bedeuten, dass Sie keinen eigenen Code entwickeln müssen, um Daten an [!DNL Audience Manager] zu senden. Außerdem unterscheidet sich [!UICONTROL DIL] von der API, die vom [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html) bereitgestellt wird. Dieser Dienst wurde entwickelt, um die Besucheridentität über verschiedene [!DNL Experience Cloud] -Lösungen hinweg zu verwalten. [!UICONTROL DIL] hingegen wurde für Folgendes entwickelt:

* Führen Sie Ereignisaufrufe durch und senden Sie Daten an den [Datenerfassungsserver](../reference/system-components/components-data-collection.md).
* Senden Sie Daten an [Ziele](../features/destinations/destinations.md).

## Abrufen und Implementieren von DIL-Code {#get-implement-dil-code}

[!UICONTROL DIL] Der Code kann  **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)** heruntergeladen werden. Beachten Sie, dass [!UICONTROL DIL] ab Version 8.0 (veröffentlicht im August 2018) eine starke Abhängigkeit vom [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), Version 3.3 oder höher aufweist. Sie verlässt sich darauf, dass [!DNL ID Service] ID-Synchronisationen und [!DNL URL destinations] auslöst. Ein Fehler tritt auf, wenn [!DNL ID Service] fehlt, alt ist oder nicht konfiguriert ist.

Statt mit [!UICONTROL DIL] zu arbeiten und [!DNL Audience Manager] manuell einzurichten, empfehlen wir stattdessen die Verwendung von [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html). [!DNL Adobe Experience Platform Launch] ist das empfohlene Implementierungstool, da es die Codebereitstellung, -platzierung und -versionsverwaltung vereinfacht. Weitere Informationen zur [Audience Manager-Erweiterung](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) in [!DNL Adobe Experience Platform Launch].

## Beispielaufruf {#sample-code}

[!UICONTROL DIL] sendet Daten  [!DNL Audience Manager] in einem Ereignisaufruf an . Ein Ereignisaufruf ist eine XML-HTTP-Anforderung von Ihrer Seite. Es wird eine `POST`-Methode verwendet, um Daten im Hauptteil der Anfrage zu senden.

| Ereignisaufrufelement | Beschreibung |
|--- |--- |
| URL | DIL-Ereignisaufrufe verwenden die folgende Syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Text | Wie im folgenden Beispiel gezeigt, übergibt DIL Daten als Schlüssel-Wert-Paare. Die Schlüsselwertpaare werden durch spezielle Präfixzeichen als Audience Manager- oder Partnervariablen gekennzeichnet.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
