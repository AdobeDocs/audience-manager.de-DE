---
description: Ein Überblick über DIL und seine Funktionsweise.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: Grundlegendes zur Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 1%

---

# Die [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>Ab Juli 2023 hat Adobe die Entwicklung der Erweiterung [!DNL Data Integration Library (DIL)] und der Erweiterung [!DNL DIL] eingestellt.
>
>Bestehende Kunden können weiterhin ihre [!DNL DIL] -Implementierung verwenden. Adobe wird jedoch nicht mehr [!DNL DIL] als bisher entwickeln. Kunden wird empfohlen, das [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) für ihre langfristige Datenerfassungsstrategie zu bewerten.
>
>Kunden, die nach Juli 2023 neue Datenerfassungs-Integrationen implementieren möchten, sollten stattdessen das [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) verwenden.

Überblick, erste Schritte und Codemethoden, die in der [!DNL Audience Manager DIL] -Codebibliothek verfügbar sind.

>[!IMPORTANT]
>
>Ab Version 8.0 (veröffentlicht im August 2018) weist [!UICONTROL DIL] eine starke Abhängigkeit vom [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), Version 3.3 oder höher auf. Die Auslösung von ID-Synchronisierungen und URL-Zielen erfolgt über den [!DNL ID Service]. Ein Fehler tritt auf, wenn [!DNL ID Service] fehlt, alt ist oder nicht konfiguriert ist.
>
>Es wird empfohlen, [!DNL Adobe Experience Platform Tags] zu verwenden, um Ihre [!DNL DIL] - und [!DNL Adobe Experience Platform Identity Service] -Bibliotheken zu implementieren und zu verwalten.

Sie können jedoch auch die neuesten Experience Cloud- und [!DNL DIL]-Versionen von unserer GitHub-Seite herunterladen. Siehe Downloadlinks unten:

* Laden Sie den [Adobe Experience Platform Identity-Dienst](https://github.com/Adobe-Marketing-Cloud/id-service/releases) herunter
* Herunterladen von [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Zweck des DIL {#purpose-dil}

[!UICONTROL DIL] ist eine API-Bibliothek. Sie können es als Hilfecode für [!DNL Adobe Audience Manager] betrachten. Es ist nicht erforderlich, [!DNL Audience Manager] zu verwenden, aber die Methoden und Funktionen, die [!UICONTROL DIL] bereitstellt, bedeuten, dass Sie keinen eigenen Code entwickeln müssen, um Daten an [!DNL Audience Manager] zu senden. Außerdem unterscheidet sich [!UICONTROL DIL] von der API, die vom [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) bereitgestellt wird. Dieser Dienst dient der Verwaltung der Besucheridentität über verschiedene [!DNL Experience Cloud] -Lösungen hinweg. Im Gegensatz dazu wird [!UICONTROL DIL] folgendermaßen entwickelt:

* Führen Sie Ereignisaufrufe aus und senden Sie Daten an den [Datenerfassungsserver](../reference/system-components/components-data-collection.md).
* Senden Sie Daten an [Ziele](../features/destinations/destinations.md).

## Abrufen und Implementieren von DIL-Code {#get-implement-dil-code}

[!UICONTROL DIL] -Code kann **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)** heruntergeladen werden. Beachten Sie, dass ab Version 8.0 (veröffentlicht im August 2018) [!UICONTROL DIL] eine starke Abhängigkeit vom [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), Version 3.3 oder höher aufweist. Es verlässt sich darauf, dass die [!DNL ID Service] ID-Synchronisationen und [!DNL URL destinations] auslöst. Ein Fehler tritt auf, wenn [!DNL ID Service] fehlt, alt ist oder nicht konfiguriert ist.

Statt mit [!UICONTROL DIL] zu arbeiten und [!DNL Audience Manager] manuell einzurichten, empfehlen wir, stattdessen [Adobe Experience Platform-Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) zu verwenden. [!DNL Adobe Experience Platform Tags] ist das empfohlene Implementierungstool, da es die Codebereitstellung, -platzierung und -versionsverwaltung vereinfacht. Weitere Informationen zur [Audience Manager-Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) finden Sie in [!DNL Adobe Experience Platform Tags].

## Beispielaufruf {#sample-code}

[!UICONTROL DIL] sendet Daten bei einem Ereignisaufruf an [!DNL Audience Manager]. Ein Ereignisaufruf ist eine XML-HTTP-Anforderung von Ihrer Seite. Es wird eine `POST` -Methode verwendet, um Daten im Hauptteil der Anfrage zu senden.

| Ereignisaufrufelement | Beschreibung |
|--- |--- |
| URL | DIL-Ereignisaufrufe verwenden die folgende Syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| body | Wie im folgenden Beispiel gezeigt, übergibt DIL Daten als Schlüssel-Wert-Paare. Durch spezielle Präfixzeichen werden die Schlüssel-Wert-Paare als Audience Manager- oder Partnervariablen gekennzeichnet.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
