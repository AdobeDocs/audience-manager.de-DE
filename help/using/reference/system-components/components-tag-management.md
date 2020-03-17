---
description: Zu den Tag-Management-Komponenten von Audience Manager gehören das Client-Portal, Adobe Tag Manager (nicht mehr unterstützt für Adobe Dynamic Tag Manager und Adobe Experience Platform Launch), DIL, Akamai und die Steuerungsdatenbank.
seo-description: Zu den Tag-Management-Komponenten von Audience Manager gehören das Client-Portal, Adobe Tag Manager (nicht mehr unterstützt für Adobe Dynamic Tag Manager und Adobe Experience Platform Launch), DIL, Akamai und die Steuerungsdatenbank.
seo-title: Komponenten des Tag-Managements
solution: Audience Manager
title: Komponenten des Tag-Managements
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Komponenten des Tag-Managements{#tag-management-components}

Zu den Tag-Management-Komponenten von Audience Manager gehören das Client-Portal, Adobe Tag Manager (nicht mehr unterstützt für Adobe Dynamic Tag Manager und Adobe Experience Platform Launch), DIL, Akamai und die Steuerungsdatenbank.

<!-- 

c_comptag.xml

 -->

Audience Manager umfasst die folgenden Komponenten:

* [Client-Portal](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM-Container](../../reference/system-components/components-tag-management.md#dil-tim)
* [Data Information Library (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Datenbank steuern](../../reference/system-components/components-tag-management.md#control-database)

## Client-Portal {#client-portal}

Das Client-Portal ist die primäre Benutzeroberfläche für Tag und Data Management. Kunden verwenden das Portal, um mit Tags zu arbeiten, Eigenschaften und Segmente zu erstellen, Ziele einzurichten und die Performance von Campaignen mit Berichten zu überwachen.

## DIL/TIM-Container {#dil-tim}

Der [!UICONTROL DIL] Container hilft bei der Bereitstellung des [!DNL Audience Manager] Datenerfassungscodes auf Ihrer Website. [!UICONTROL TIM] ist der nicht mehr unterstützte Tag-Einfüge-Manager. Es wird nicht mehr von verwendet [!DNL Audience Manager]. Stattdessen verwenden Sie das [dynamische Tag-Management](https://marketing.adobe.com/resources/help/en_US/dtm/) oder die [!DNL Audience Manager] Erweiterung in [Adobe Experience Platform Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) , um Container-Code zu konfigurieren und zu generieren, den Sie auf Seiten in Ihrem Bestand platzieren. Der [!UICONTROL DTM] Container arbeitet mit der [!UICONTROL Data Information Library (DIL)] , um Daten von Ihrer Site zu erfassen und an [!DNL Audience Manager]zu senden.

## Data Integration Library (DIL){#dil} 

Die [Dateninformationsbibliothek](../../dil/dil-overview.md) (DIL) ist ein eigenständiges API-Modul, das Daten von Ihrer Website erfasst. [!UICONTROL DIL] hilft, die Notwendigkeit zu vermeiden, speziellen Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten zu schreiben. [!UICONTROL DIL] führt diese Aktionen automatisch aus. Außerdem [!UICONTROL DIL] ist kompakt. Es handelt sich dabei um eine eigenständige Codebibliothek, die dazu beiträgt, die für die Datenerfassung erforderliche Codemenge zu reduzieren. Schließlich [!UICONTROL DIL] hilft Ihnen die Integration [!DNL Audience Manager] mit anderen Produkten in der [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] verwendet [Akamai](https://www.akamai.com/html/about/index.html) , um Container-Code von unserer eigenen Tag-Management-Plattform, bekannt als [!UICONTROL TIM (Tag Insertion Manager)]. Die Codebereitstellung mit [!UICONTROL TIM] wurde jedoch zugunsten [!DNL Adobe Dynamic Tag Management] und [!DNL Adobe Experience Platform Launch]schrittweise eingestellt.

## Datenbank steuern {#control-database}

Die Steuerungsdatenbank:

* Verarbeitet Client-Eingaben aus dem Portal (z. B. Erstellen von Eigenschaften und Zielen).
* Sendet Daten an Akamai, das Daten enthält, die zum Erstellen der Container-Vorlage und zum Veröffentlichen des iFrames verwendet werden.
* Gibt Daten für UI-Berichte-Systeme zurück.

