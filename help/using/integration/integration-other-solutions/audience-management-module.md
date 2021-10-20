---
description: Fügen Sie das Zielgruppen-Management-Modul zu Adobe Analytics AppMeasurement hinzu, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager-Data Integration Library-Code (DIL) ein Pixel von der Seite sendet.
keywords: Zielgruppenanalyse; Analyse; ssf; Serverseitige Weiterleitung
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Implementieren des Zielgruppen-Management-Moduls
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# Weiterleiten von Daten von [!DNL Adobe Analytics] nach [!DNL Audience Manager] {#implement-the-audience-management-module}

Führen Sie die Schritte in diesem Tutorial aus, um weiterzuleiten [!DNL Analytics] Daten an [!DNL Audience Manager] anstatt die [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) einen Pixel von der Seite senden.

>[!TIP]
>
>Es wird empfohlen, [!DNL Adobe Experience Platform Tags] Weiterleiten [!UICONTROL Analytics] Daten in [!DNL Audience Manager]. Durch Verwendung von [!UICONTROL Tags], müssen Sie den Code nicht manuell in [!DNL AppMeasurement], wie auf dieser Seite gezeigt.

## Voraussetzungen {#prereqs}

Zusätzlich zur Aktivierung der Erweiterungen oder Implementierung des in diesem Dokument beschriebenen Codes müssen Sie auch:

* Implementieren des [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* Aktivieren [Serverseitige Weiterleitung](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) für Report Suites in [!UICONTROL Adobe Analytics Admin Console].

## Implementierung {#implementation}

Es gibt zwei Methoden zur Implementierung der Datenweiterleitung von [!DNL Adobe Analytics] nach [!DNL Audience Manager]- abhängig von der von Ihnen verwendeten Tag-Management-Lösung.

### Implementierung mithilfe von [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] empfiehlt, die [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) Erweiterung des Instruments [!DNL Adobe Analytics] und [!DNL Audience Manager] in Ihren Eigenschaften. In diesem Fall müssen Sie keinen Code manuell kopieren. Stattdessen müssen Sie die Datenfreigabe im [!DNL Analytics] -Erweiterung, wie in der Abbildung unten dargestellt. Siehe auch [Adobe Analytics-Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager) Dokumentation.

>[!TIP]
>
>Wenn Sie die [!DNL Adobe Analytics] Erweiterung, *nicht* installieren Sie auch die [!DNL Audience Manager] -Erweiterung. Weiterleiten von Daten aus dem [!DNL Analytics] -Erweiterung ersetzt die [!DNL Audience Manager] Erweiterungsfunktion.

![So aktivieren Sie die Datenfreigabe von der Adobe Analytics-Erweiterung für Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Definierte Codeelemente {#code-elements-defined}

Die folgende Tabelle definiert wichtige Variablen im Codebeispiel.

| Parameter | Beschreibung |
|--- |--- |
| `partner` | Erforderlich. Dies ist ein Partnername, der von [!DNL Adobe]. Dies wird manchmal auch als [!UICONTROL partner ID] oder der Partner-Subdomäne.  Wenden Sie sich an [!DNL Adobe] Berater oder [Kundenunterstützung](https://helpx.adobe.com/de/marketing-cloud/contact-support.html) wenn Sie Ihren Partnernamen nicht kennen. |
| `containerNSID` | Erforderlich. Die meisten Kunden können einfach  `"containerNSID":0` . Wenn Ihr Unternehmen jedoch ID-Synchronisationen mit einem anderen Container anpassen muss, können Sie diese Container-ID hier angeben. |
| `uuidCookie` | Optional. Mit dieser Konfiguration können Sie eine [!DNL Adobe] -Cookie in der Erstanbieterdomäne. Diese [!DNL cookie] enthält die [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Erforderlich. Die `namespace` -Parameter erforderlich, wenn Sie die [!DNL AudienceManagement] -Modul mit [!UICONTROL AppMeasurement] Version 2.10 oder neuer. Diese [!UICONTROL AudienceManagement] -Modul erfordert, dass Sie [!UICONTROL Adobe Experience Platform Identity Service] 3.3 oder höher. <br><br>Die [!UICONTROL Experience Cloud Organization ID] ist die ID, die ein Unternehmen erhält, wenn es sich für die [!UICONTROL Experience Cloud]. Erfahren Sie mehr über die Organisations-ID Ihres Unternehmens unter [Organisationen und Kontoverknüpfung](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## Ergebnisse: Datenweiterleitung an [!DNL Audience Manager] {#results-data-forwarding}

Ihre [!DNL Analytics] -Implementierung sendet Daten an [!DNL Audience Manager] nachdem Sie über Folgendes verfügen:

* Aktiviert [!UICONTROL Server-Side Forwarding] (Wenden Sie sich an Ihren Berater über diese Funktion);
* Implementiert die [!DNL Adobe Experience Platform Identity Service];
* Befolgte die Implementierungsschritte in diesem Tutorial.

Dieser Prozess sendet Daten an [!DNL Audience Manager]:

* Bei Seitenansichtsaufrufen;
* über getrackte Links;
* Aus Video-Meilensteinen und Heartbeat-Videoansichten.

>[!NOTE]
>
>Die Variablen, die an [!DNL Audience Manager] von [!DNL Analytics] Verwenden Sie spezielle Präfixe. Sie müssen diese Präfixe beim Erstellen verstehen und berücksichtigen [!DNL Audience Manager] Eigenschaften. Weitere Informationen zu diesen Präfixen finden Sie unter [Voraussetzungen für das Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md).
