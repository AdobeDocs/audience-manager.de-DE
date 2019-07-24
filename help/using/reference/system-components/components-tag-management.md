---
description: Zu den Audience Manager-Tag-Management-Komponenten gehören das Client Portal, Adobe Tag Manager (nicht mehr unterstützt zugunsten von Adobe Dynamischer Tag-Manager und Adobe Launch), DIL, Akamai und die Control-Datenbank.
seo-description: Zu den Audience Manager-Tag-Management-Komponenten gehören das Client Portal, Adobe Tag Manager (nicht mehr unterstützt zugunsten von Adobe Dynamischer Tag-Manager und Adobe Launch), DIL, Akamai und die Control-Datenbank.
seo-title: Tag-Management-Komponenten
solution: Audience Manager
title: Tag-Management-Komponenten
uuid: e 5059478-6 ba 7-4 e 1 a-afec-e 41 ad 7 a 27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Tag Management Components{#tag-management-components}

Zu den Audience Manager-Tag-Management-Komponenten gehören das Client Portal, Adobe Tag Manager (nicht mehr unterstützt zugunsten von Adobe Dynamischer Tag-Manager und Adobe Launch), DIL, Akamai und die Control-Datenbank.

<!-- 

c_comptag.xml

 -->

Audience Manager enthält die folgenden Komponenten:

* [Client Portal](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM-Container](../../reference/system-components/components-tag-management.md#dil-tim)
* [Dateninformationsbibliothek (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Control-Datenbank](../../reference/system-components/components-tag-management.md#control-database)

## Client Portal {#client-portal}

Das Client-Portal ist die primäre Benutzeroberfläche für Tag- und Datenverwaltung. Kunden verwenden das Portal, um mit Tags zu arbeiten, Eigenschaften und Segmente zu erstellen, Ziele einzurichten und die Kampagnenleistung mit Berichten zu überwachen.

## DIL/TIM Container {#dil-tim}

The [!UICONTROL DIL] container helps deploy [!DNL Audience Manager] data collection code to your website. [!UICONTROL TIM] ist der veraltete Tag-Insertion Manager. It is no longer used by [!DNL Audience Manager]. Instead, you use [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/) or the [!DNL Audience Manager] extension in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) to configure and generate container code that you place on pages in your inventory. The [!UICONTROL DTM] container works with the [!UICONTROL Data Information Library (DIL)] to collect data from your site and send it to [!DNL Audience Manager].

## Data Integration Library (DIL){#dil} 

The [Data Information Library](../../dil/dil-overview.md) (DIL) is a self-contained API module that collects data from your website. [!UICONTROL DIL] verhindert, dass der spezielle Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und die Wiederherstellung von Seitendaten nicht geschrieben werden müssen. [!UICONTROL DIL] führt diese Aktionen automatisch durch. [!UICONTROL DIL] Außerdem ist das kompakte Element. Es handelt sich um eine eigenständige Codebibliothek, mit der die für die Datenerfassung erforderliche Codemenge reduziert wird. Finally, [!UICONTROL DIL] helps you integrate [!DNL Audience Manager] with other products in the [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] verwendet [Akamai](https://www.akamai.com/html/about/index.html) zum Hosten und Bereitstellen von Containercode aus unserer eigenen Tag-Management-Plattform, bekannt als [!UICONTROL TIM (Tag Insertion Manager)]. However, code deployment with [!UICONTROL TIM] has been phased out in favor of [!UICONTROL Adobe Dynamic Tag Management] and [!UICONTROL Adobe Launch].

## Control Database {#control-database}

Die Control-Datenbank:

* Verarbeitet Client-Eingaben aus dem Portal (z. B. Eigenschaften und Ziele erstellen).
* Sendet Daten an Akamai, einschließlich Daten zum Erstellen der Container-Vorlage und des iframe für die Zielveröffentlichung.
* Gibt Daten für UI-Berichtssysteme zurück.

