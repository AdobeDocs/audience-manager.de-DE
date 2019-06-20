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


# Tag-Management-Komponenten{#tag-management-components}

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

## DIL/TIM-Container {#dil-tim}

Der [!UICONTROL DIL] Behälter hilft Ihnen, [!DNL Audience Manager] Datenerfassungscode auf Ihrer Website bereitzustellen. [!UICONTROL TIM] ist der veraltete Tag-Insertion Manager. Sie wird nicht mehr verwendet [!DNL Audience Manager]. Stattdessen verwenden [Sie das Dynamische Tag-Management](https://marketing.adobe.com/resources/help/en_US/dtm/) oder die [!DNL Audience Manager] Erweiterung in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) , um Behälter zu konfigurieren und zu generieren, die Sie auf Seiten in Ihrem Bestand platzieren. Der [!UICONTROL DTM] Container arbeitet mit der [!UICONTROL Data Information Library (DIL)] zur Datenerfassung von Ihrer Site und sendet ihn an [!DNL Audience Manager].

## Data Integration Library (DIL){#dil} 

Die [Data Information Library](../../dil/dil-overview.md) (DIL) ist ein eigenständiges API-Modul, das Daten von Ihrer Website sammelt. [!UICONTROL DIL] verhindert, dass der spezielle Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und die Wiederherstellung von Seitendaten nicht geschrieben werden müssen. [!UICONTROL DIL] führt diese Aktionen automatisch durch. [!UICONTROL DIL] Außerdem ist das kompakte Element. Es handelt sich um eine eigenständige Codebibliothek, mit der die für die Datenerfassung erforderliche Codemenge reduziert wird. Schließlich [!UICONTROL DIL] können Sie die Integration [!DNL Audience Manager] mit anderen Produkten in der [!DNL Adobe] Experience Cloud erleichtern.

## Akamai {#akamai}

[!DNL Audience Manager] verwendet [Akamai](https://www.akamai.com/html/about/index.html) zum Hosten und Bereitstellen von Containercode aus unserer eigenen Tag-Management-Plattform, bekannt als [!UICONTROL TIM (Tag Insertion Manager)]. Die Code-Bereitstellung wurde [!UICONTROL TIM] jedoch zugunsten [!UICONTROL Adobe Dynamic Tag Management] von und [!UICONTROL Adobe Launch].

## Control-Datenbank {#control-database}

Die Control-Datenbank:

* Verarbeitet Client-Eingaben aus dem Portal (z. B. Eigenschaften und Ziele erstellen).
* Sendet Daten an Akamai, einschließlich Daten zum Erstellen der Container-Vorlage und des iframe für die Zielveröffentlichung.
* Gibt Daten für UI-Berichtssysteme zurück.

