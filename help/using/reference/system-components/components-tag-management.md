---
description: Zu den Audience Manager-Tag-Management-Komponenten gehören das Client-Portal, Adobe Tag Manager (nicht mehr unterstützt für Adobe Dynamischer Tag-Manager und Adobe Experience Platform Launch), DIL, Akamai und die Steuerungsdatenbank.
seo-description: Zu den Audience Manager-Tag-Management-Komponenten gehören das Client-Portal, Adobe Tag Manager (nicht mehr unterstützt für Adobe Dynamischer Tag-Manager und Adobe Experience Platform Launch), DIL, Akamai und die Steuerungsdatenbank.
seo-title: Komponenten des Tag Managements
solution: Audience Manager
title: Komponenten des Tag Managements
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: Systemkomponenten
translation-type: tm+mt
source-git-commit: 65598677498ede26e4961cd4849c9b655dac38dc
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 5%

---


# Komponenten des Tag Managements{#tag-management-components}

Zu den Audience Manager-Tag-Management-Komponenten gehören das Client-Portal, Adobe Tag Manager (nicht mehr unterstützt für Adobe Dynamischer Tag-Manager und Adobe Experience Platform Launch), DIL, Akamai und die Steuerungsdatenbank.

<!-- 

c_comptag.xml

 -->

Audience Manager enthält die folgenden Komponenten:

* [Client-Portal](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM-Container](../../reference/system-components/components-tag-management.md#dil-tim)
* [Dateninformationsbibliothek (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Datenbank steuern](../../reference/system-components/components-tag-management.md#control-database)

## Client-Portal {#client-portal}

Das Client-Portal ist die primäre Benutzeroberfläche für Tag und Data Management. Kunden verwenden das Portal, um mit Tags zu arbeiten, Eigenschaften und Segmente zu erstellen, Ziele einzurichten und die Performance der Kampagne mit Berichten zu überwachen.

## DIL/TIM-Container {#dil-tim}

Der [!UICONTROL DIL]-Container hilft bei der Bereitstellung des [!DNL Audience Manager]-Datenerfassungscodes auf Ihrer Website. [!UICONTROL TIM] ist der nicht mehr unterstützte Tag-Einfüge-Manager. Es wird nicht mehr von [!DNL Audience Manager] verwendet. Stattdessen verwenden Sie [Dynamisches Tag-Management](https://docs.adobe.com/content/help/de-DE/dtm/using/dtm-home.html) oder die [!DNL Audience Manager]-Erweiterung in [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html), um Container-Code zu konfigurieren und zu generieren, den Sie auf den Seiten im Bestand platzieren. Der [!UICONTROL DTM]-Container funktioniert mit dem [!UICONTROL Data Information Library (DIL)], um Daten von Ihrer Site zu erfassen und an [!DNL Audience Manager] zu senden.

## Data Integration Library (DIL)- {#dil}

Die [Dateninformationsbibliothek](../../dil/dil-overview.md) (DIL) ist ein eigenständiges API-Modul, das Daten von Ihrer Website erfasst. [!UICONTROL DIL] hilft, die Notwendigkeit zu vermeiden, speziellen Code für die Datenerfassung, Integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten zu schreiben. [!UICONTROL DIL] führt diese Aktionen automatisch aus. Außerdem ist [!UICONTROL DIL] kompakt. Es handelt sich dabei um eine eigenständige Codebibliothek, die dazu beiträgt, die für die Datenerfassung erforderliche Codemenge zu reduzieren. [!UICONTROL DIL] unterstützt Sie bei der Integration von [!DNL Audience Manager] mit anderen Produkten im [!DNL Adobe]-Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] verwendet  [](https://www.akamai.com/us/en/about/) Akamaito-Host und stellt Container-Code von unserer eigenen Tag-Management-Plattform, bekannt als  [!UICONTROL TIM (Tag Insertion Manager)]. Die Codebereitstellung mit [!UICONTROL TIM] wurde jedoch zugunsten von [!DNL Adobe Dynamic Tag Management] und [!DNL Adobe Experience Platform Launch] eingestellt.

## Steuerungsdatenbank {#control-database}

Die Steuerungsdatenbank:

* Verarbeitet Client-Eingaben aus dem Portal (z. B. Erstellen von Eigenschaften und Zielen).
* Sendet Daten an Akamai, das Daten enthält, die zum Erstellen der Container-Vorlage und zum Veröffentlichen des iFrames verwendet werden.
* Gibt Daten für UI-Berichte-Systeme zurück.

