---
description: Zu den Audience Manager-Tag-Management-Komponenten gehören das Clientportal, Adobe Tag Manager (nicht mehr unterstützt für Adobe Experience Platform Launch), DIL, Akamai und die Kontrolldatenbank.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Komponenten des Tag Managements
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 3%

---

# Komponenten des Tag Managements{#tag-management-components}

Zu den Audience Manager-Tag-Management-Komponenten gehören das Clientportal, Adobe Tag Manager (nicht mehr unterstützt für Adobe Experience Platform-Tags), DIL, Akamai und die Kontrolldatenbank.

<!-- 

c_comptag.xml

 -->

Audience Manager enthält die folgenden Komponenten:

* [Client Portal](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM-Container](../../reference/system-components/components-tag-management.md#dil-tim)
* [Dateninformationsbibliothek (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Kontrolldatenbank](../../reference/system-components/components-tag-management.md#control-database)

## Client Portal {#client-portal}

Das Client-Portal ist die primäre Benutzeroberfläche für die Tag- und Datenverwaltung. Kunden verwenden das Portal, um mit Tags zu arbeiten, Eigenschaften und Segmente zu erstellen, Ziele einzurichten und die Kampagnenleistung mit Berichten zu überwachen.

## DIL/TIM-Container {#dil-tim}

Die [!UICONTROL DIL] Container hilft beim Bereitstellen [!DNL Audience Manager] Datenerfassungs-Code auf Ihrer Website. [!UICONTROL TIM] ist der veraltete Tag Insertion Manager. Sie wird nicht mehr von [!DNL Audience Manager]. Stattdessen verwenden Sie die [!DNL Audience Manager] Erweiterung in [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) , um Container-Code zu konfigurieren und zu generieren, den Sie auf Seiten in Ihrem Inventar platzieren.

## Data Integration Library (DIL) {#dil}

Die [Dateninformationsbibliothek](../../dil/dil-overview.md) (DIL) ist ein eigenständiges API-Modul, das Daten von Ihrer Website erfasst. [!UICONTROL DIL] verhindert das Schreiben von speziellem Code für die Datenerfassung, -integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten. [!UICONTROL DIL] führt diese Aktionen automatisch aus. Zusätzlich [!UICONTROL DIL] ist kompakt. Es handelt sich dabei um eine eigenständige Code-Bibliothek, die dazu beiträgt, die zum Erfassen von Informationen erforderliche Codemenge zu reduzieren. Schließlich [!UICONTROL DIL] hilft Ihnen bei der Integration [!DNL Audience Manager] mit anderen Erzeugnissen in [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] uses [Akamai](https://www.akamai.com/us/en/about/) zum Hosten und Bereitstellen von Container-Code von unserer eigenen Tag-Management-Plattform namens [!UICONTROL TIM (Tag Insertion Manager)]. Codebereitstellung mit [!UICONTROL TIM] wurde zugunsten von [!DNL Adobe Experience Platform Tags].

## Kontrolldatenbank {#control-database}

Die Kontrolldatenbank:

* Verarbeitet die Client-Eingabe vom Portal (z. B. Erstellen von Eigenschaften und Zielen).
* Sendet Daten an Akamai, das Daten enthält, die zum Erstellen der Container-Vorlage und zum Veröffentlichen des iFrame verwendet werden.
* Gibt Daten für UI-Berichterstellungssysteme zurück.
