---
description: Zu den Audience Manager-Tag-Management-Komponenten gehören das Clientportal, Adobe Tag Manager (nicht mehr unterstützt für Adobe Experience Platform Launch), DIL, Akamai und die Kontrolldatenbank.
seo-description: Zu den Audience Manager-Tag-Management-Komponenten gehören das Clientportal, Adobe Tag Manager (nicht mehr unterstützt für Adobe Experience Platform Launch), DIL, Akamai und die Kontrolldatenbank.
seo-title: Komponenten des Tag Managements
solution: Audience Manager
title: Komponenten des Tag Managements
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: 'Systemkomponenten '
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 4%

---

# Komponenten des Tag Managements{#tag-management-components}

Zu den Audience Manager-Tag-Management-Komponenten gehören das Clientportal, Adobe Tag Manager (nicht mehr unterstützt für Adobe Experience Platform Launch), DIL, Akamai und die Kontrolldatenbank.

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

## DIL/TIM Container {#dil-tim}

Der [!UICONTROL DIL]-Container hilft bei der Bereitstellung von [!DNL Audience Manager] Datenerfassungscode für Ihre Website. [!UICONTROL TIM] ist der veraltete Tag Insertion Manager. Sie wird nicht mehr von [!DNL Audience Manager] verwendet. Stattdessen verwenden Sie die Erweiterung [!DNL Audience Manager] in [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html), um den Container-Code zu konfigurieren und zu generieren, den Sie auf Seiten in Ihrem Inventar platzieren.

## Data Integration Library (DIL) {#dil}

Die [Data Information Library](../../dil/dil-overview.md) (DIL) ist ein eigenständiges API-Modul, das Daten von Ihrer Website erfasst. [!UICONTROL DIL] verhindert das Schreiben von speziellem Code für die Datenerfassung, -integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten. [!UICONTROL DIL] führt diese Aktionen automatisch aus. Außerdem ist [!UICONTROL DIL] kompakt. Es handelt sich dabei um eine eigenständige Code-Bibliothek, die dazu beiträgt, die zum Erfassen von Informationen erforderliche Codemenge zu reduzieren. Schließlich hilft Ihnen [!UICONTROL DIL] bei der Integration von [!DNL Audience Manager] mit anderen Produkten im [!DNL Adobe]-Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] verwendet  [](https://www.akamai.com/us/en/about/) Akamaito-Host und stellt Container-Code von unserer eigenen Tag-Management-Plattform bereit, die als  [!UICONTROL TIM (Tag Insertion Manager)]bezeichnet wird. Die Codebereitstellung mit [!UICONTROL TIM] wurde jedoch zugunsten von [!DNL Adobe Experience Platform Launch] eingestellt.

## Kontrolldatenbank {#control-database}

Die Kontrolldatenbank:

* Verarbeitet die Client-Eingabe vom Portal (z. B. Erstellen von Eigenschaften und Zielen).
* Sendet Daten an Akamai, das Daten enthält, die zum Erstellen der Container-Vorlage und zum Veröffentlichen des iFrame verwendet werden.
* Gibt Daten für UI-Berichterstellungssysteme zurück.
