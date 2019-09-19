---
description: Zu den Komponenten des Zielgruppen-Manager-Tag-Managements gehören das Client-Portal, Adobe Tag-Manager (nicht mehr unterstützt für Adobe Dynamic Tag Manager und Adobe Launch), DIL, Akamai und die Steuerungsdatenbank.
seo-description: Zu den Komponenten des Zielgruppen-Manager-Tag-Managements gehören das Client-Portal, Adobe Tag-Manager (nicht mehr unterstützt für Adobe Dynamic Tag Manager und Adobe Launch), DIL, Akamai und die Steuerungsdatenbank.
seo-title: Komponenten des Tag-Managements
solution: Audience Manager
title: Komponenten des Tag-Managements
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Komponenten des Tag-Managements{#tag-management-components}

Zu den Komponenten des Zielgruppen-Manager-Tag-Managements gehören das Client-Portal, Adobe Tag-Manager (nicht mehr unterstützt für Adobe Dynamic Tag Manager und Adobe Launch), DIL, Akamai und die Steuerungsdatenbank.

<!-- 

c_comptag.xml

 -->

Audience Manager enthält die folgenden Komponenten:

* [Client-Portal](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM-Container](../../reference/system-components/components-tag-management.md#dil-tim)
* [Data Information Library (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Datenbank steuern](../../reference/system-components/components-tag-management.md#control-database)

## Client-Portal {#client-portal}

Das Client-Portal ist die primäre Benutzeroberfläche für Tag- und Datenverwaltung. Kunden verwenden das Portal, um mit Tags zu arbeiten, Eigenschaften und Segmente zu erstellen, Ziele einzurichten und die Kampagnenleistung mit Berichten zu überwachen.

## DIL/TIM-Container {#dil-tim}

Der [!UICONTROL DIL] Container hilft bei der Bereitstellung des [!DNL Audience Manager] Datenerfassungscodes auf Ihrer Website. [!UICONTROL TIM] ist der nicht mehr unterstützte Tag-Einfüge-Manager. Es wird nicht mehr von verwendet [!DNL Audience Manager]. Stattdessen verwenden Sie das [dynamische Tag-Management](https://marketing.adobe.com/resources/help/en_US/dtm/) oder die [!DNL Audience Manager] Erweiterung in [Adobe Launch](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) , um den Containercode zu konfigurieren und zu generieren, den Sie auf Seiten in Ihrem Bestand platzieren. Der [!UICONTROL DTM] Container funktioniert mit dem [!UICONTROL Data Information Library (DIL)] , um Daten von Ihrer Site zu erfassen und an zu senden [!DNL Audience Manager].

## Data Integration Library (DIL){#dil} 

Die [Dateninformationsbibliothek](../../dil/dil-overview.md) (DIL) ist ein eigenständiges API-Modul, das Daten von Ihrer Website erfasst. [!UICONTROL DIL] hilft, die Notwendigkeit zu vermeiden, speziellen Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten zu schreiben. [!UICONTROL DIL] führt diese Aktionen automatisch aus. Außerdem [!UICONTROL DIL] ist kompakt. Es handelt sich dabei um eine eigenständige Codebibliothek, die dazu beiträgt, die für die Datenerfassung erforderliche Codemenge zu reduzieren. Schließlich [!UICONTROL DIL] hilft Ihnen die Integration [!DNL Audience Manager] mit anderen Produkten in der [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] verwendet [Akamai](https://www.akamai.com/html/about/index.html) , um Containercode von unserer eigenen Tag-Management-Plattform namens [!UICONTROL TIM (Tag Insertion Manager)]. Die Codebereitstellung mit [!UICONTROL TIM] wurde jedoch zugunsten [!UICONTROL Adobe Dynamic Tag Management] und [!UICONTROL Adobe Launch]schrittweise eingestellt.

## Datenbank steuern {#control-database}

Die Steuerungsdatenbank:

* Verarbeitet Client-Eingaben aus dem Portal (z. B. Erstellen von Eigenschaften und Zielen).
* Sendet Daten an Akamai, das Daten enthält, die zum Erstellen der Containervorlage und zum Veröffentlichen des iFrame verwendet werden.
* Gibt Daten für UI-Berichterstellungssysteme zurück.

