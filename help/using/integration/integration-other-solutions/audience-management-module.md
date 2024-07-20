---
description: Fügen Sie das Zielgruppen-Management-Modul zum Adobe Analytics-AppMeasurement hinzu, um Analytics-Daten an Audience Manager weiterzuleiten, anstatt dass der Audience Manager-Data Integration Library-Code (DIL) ein Pixel von der Seite sendet.
keywords: Zielgruppenanalyse; Analyse; ssf; serverseitige Weiterleitung
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Implementieren des Zielgruppen-Management-Moduls
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---

# Weiterleiten von Daten von [!DNL Adobe Analytics] an [!DNL Audience Manager] {#implement-the-audience-management-module}

Führen Sie die Schritte in diesem Tutorial aus, um [!DNL Analytics] -Daten an [!DNL Audience Manager] weiterzuleiten, anstatt dass der Code [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) ein Pixel von der Seite sendet.

>[!TIP]
>
>Es wird empfohlen, [!DNL Adobe Experience Platform Tags] zu verwenden, um [!UICONTROL Analytics] -Daten an [!DNL Audience Manager] weiterzuleiten. Durch die Verwendung von [!UICONTROL Tags] müssen Sie keinen Code manuell in [!DNL AppMeasurement] kopieren, wie auf dieser Seite dargestellt.

## Voraussetzungen {#prereqs}

Zusätzlich zur Aktivierung der Erweiterungen oder Implementierung des in diesem Dokument beschriebenen Codes müssen Sie auch:

* Implementieren Sie den [Adobe Experience Platform Identity-Dienst](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* Aktivieren Sie die [serverseitige Weiterleitung](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) für Report Suites in der [!UICONTROL Adobe Analytics Admin Console].

## Implementierung {#implementation}

Je nach der von Ihnen verwendeten Tag-Management-Lösung gibt es zwei Methoden zur Implementierung der Datenweiterleitung von [!DNL Adobe Analytics] zu [!DNL Audience Manager].

### Implementierung mit [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] empfiehlt, die Erweiterung [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) zu verwenden, um [!DNL Adobe Analytics] und [!DNL Audience Manager] in Ihren Eigenschaften zu instrumentieren. In diesem Fall müssen Sie keinen Code manuell kopieren. Stattdessen müssen Sie die Datenfreigabe in der Erweiterung [!DNL Analytics] aktivieren, wie in der Abbildung unten dargestellt. Weitere Informationen finden Sie in der Dokumentation zur [Adobe Analytics-Erweiterung](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Wenn Sie die Erweiterung [!DNL Adobe Analytics] installieren, installieren *nicht* auch die Erweiterung [!DNL Audience Manager]. Die Weiterleitung von Daten aus der Erweiterung [!DNL Analytics] ersetzt die Funktion der Erweiterung [!DNL Audience Manager] .

![So aktivieren Sie die Datenfreigabe von der Adobe Analytics-Erweiterung für Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Definierte Codeelemente {#code-elements-defined}

Die folgende Tabelle definiert wichtige Variablen im Codebeispiel.

| Parameter | Beschreibung |
|--- |--- |
| `partner` | Erforderlich. Dies ist ein Partnername, der Ihnen von [!DNL Adobe] zugewiesen wird. Sie wird manchmal auch als Ihre [!UICONTROL partner ID] - oder Partner-Subdomäne bezeichnet.  Wenden Sie sich an Ihren [!DNL Adobe] -Berater oder an die [Kundenunterstützung](https://helpx.adobe.com/de/marketing-cloud/contact-support.html), wenn Sie Ihren Partnernamen nicht kennen. |
| `containerNSID` | Erforderlich. Die meisten Kunden können einfach `"containerNSID":0` festlegen. Wenn Ihr Unternehmen jedoch die ID-Synchronisierungen mit einem anderen Container anpassen muss, können Sie diese Container-ID hier angeben. |
| `uuidCookie` | Optional. Mit dieser Konfiguration können Sie ein [!DNL Adobe] -Cookie in der Erstanbieterdomäne setzen. Diese [!DNL cookie] enthält die [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Erforderlich. Der Parameter `namespace` ist erforderlich, wenn Sie das mit [!UICONTROL AppMeasurement] Version 2.10 oder höher gebündelte Modul [!DNL AudienceManagement] verwenden. Für dieses [!UICONTROL AudienceManagement]-Modul müssen Sie [!UICONTROL Adobe Experience Platform Identity Service] 3.3 oder höher verwenden. <br><br>Die [!UICONTROL Experience Cloud Organization ID] ist die ID, die ein Unternehmen erhält, wenn es sich für die [!UICONTROL Experience Cloud] anmeldet. Erfahren Sie mehr über die Organisations-ID Ihres Unternehmens in [Organisationen und Kontoverknüpfung](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## Ergebnisse: Datenweiterleitung an [!DNL Audience Manager] {#results-data-forwarding}

Ihre [!DNL Analytics] -Implementierung sendet Daten an [!DNL Audience Manager], nachdem Sie Folgendes erreicht haben:

* Aktiviert [!UICONTROL Server-Side Forwarding] (sprechen Sie mit Ihrem Berater über diese Funktion);
* Implementiert den [!DNL Adobe Experience Platform Identity Service];
* Befolgte die Implementierungsschritte in diesem Tutorial.

Dieser Prozess sendet Daten an [!DNL Audience Manager]:

* Bei Seitenansichtsaufrufen;
* über getrackte Links;
* Aus Video-Meilensteinen und Heartbeat-Videoansichten.

>[!NOTE]
>
>Die von [!DNL Analytics] an [!DNL Audience Manager] gesendeten Variablen verwenden spezielle Präfixe. Sie müssen diese Präfixe beim Erstellen von [!DNL Audience Manager] -Eigenschaften verstehen und berücksichtigen. Weitere Informationen zu diesen Präfixen finden Sie unter [Voraussetzungen für das Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md).
