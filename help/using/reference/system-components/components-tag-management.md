---
description: Zu den Tag-Management-Komponenten von Audience Manager gehören das Client-Portal, Adobe Tag Manager (veraltet zugunsten von Adobe Experience Platform Launch), DIL, Akamai und die Kontrolldatenbank.
seo-description: Audience Manager tag management components include the client portal, Adobe Tag Manager (deprecated in favor of Adobe Experience Platform Launch), DIL, Akamai, and the control database.
seo-title: Tag Management Components
solution: Audience Manager
title: Tag Management-Komponenten
uuid: e5059478-6ba7-4e1a-afec-e41ad7a27750
feature: System Components
exl-id: 064e3653-7658-422c-9dd5-2252806e8f09
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 1%

---

# Tag Management-Komponenten{#tag-management-components}

Zu den Tag-Management-Komponenten von Audience Manager gehören das Client-Portal, Adobe Tag Manager (veraltet zugunsten von Adobe Experience Platform Tags), DIL, Akamai und die Kontrolldatenbank.

<!-- 

c_comptag.xml

 -->

Audience Manager umfasst die folgenden Komponenten:

* [Client-Portal](../../reference/system-components/components-tag-management.md#client-portal)
* [DIL/TIM-Container](../../reference/system-components/components-tag-management.md#dil-tim)
* [Data Information Library (DIL)](../../reference/system-components/components-tag-management.md#dil)
* [Akamai](../../reference/system-components/components-tag-management.md#akamai)
* [Datenbank kontrollieren](../../reference/system-components/components-tag-management.md#control-database)

## Client-Portal {#client-portal}

Das Client-Portal ist die primäre Benutzeroberfläche für das Tag- und Daten-Management. Kundinnen und Kunden verwenden das Portal, um mit Tags zu arbeiten, Eigenschaften und Segmente zu erstellen, Ziele einzurichten und die Kampagnenleistung mit Berichten zu überwachen.

## DIL/TIM-Container {#dil-tim}

Der [!UICONTROL DIL]-Container hilft beim Bereitstellen [!DNL Audience Manager] Datenerfassungs-Codes auf Ihrer Website. [!UICONTROL TIM] ist der veraltete Tag Insertion Manager. Es wird nicht mehr von [!DNL Audience Manager] verwendet. Stattdessen verwenden Sie die [!DNL Audience Manager]-Erweiterung in [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=de) um Container-Code zu konfigurieren und zu generieren, den Sie auf Seiten in Ihrem Inventar platzieren.

## Data Integration Library (DIL) {#dil}

Die [Data Information Library](../../dil/dil-overview.md) (DIL) ist ein eigenständiges API-Modul, das Daten von Ihrer Website erfasst. [!UICONTROL DIL] ist es nicht mehr erforderlich, speziellen Code für die Datenerfassung, -integration, das Lesen von Cookie-Werten und das Wiederherstellen von Seitendaten zu schreiben. [!UICONTROL DIL] führt diese Aktionen automatisch aus. Darüber hinaus ist [!UICONTROL DIL] kompakt. Es handelt sich dabei um eine eigenständige Code-Bibliothek, die dazu beiträgt, den für das Erfassen von Informationen erforderlichen Code zu reduzieren. Schließlich hilft Ihnen [!UICONTROL DIL] bei der Integration von [!DNL Audience Manager] mit anderen Produkten in der [!DNL Adobe] Experience Cloud.

## Akamai {#akamai}

[!DNL Audience Manager] verwendet [Akamai](https://www.akamai.com/us/en/about/) um Container-Code von unserer eigenen Tag-Management-Plattform namens [!UICONTROL TIM (Tag Insertion Manager)] zu hosten und bereitzustellen. Die Code-Bereitstellung mit [!UICONTROL TIM] wurde jedoch zugunsten von [!DNL Adobe Experience Platform Tags] schrittweise eingestellt.

## Datenbank kontrollieren {#control-database}

Die Kontrolldatenbank:

* Verarbeitet Client-Eingaben über das Portal (z. B. Erstellen von Eigenschaften und Zielen).
* Übermittelt Daten an Akamai, einschließlich der Daten zum Erstellen der Container-Vorlage und des Destination Publishing iFrame.
* Gibt Daten für Berichterstellungssysteme der Benutzeroberfläche zurück.
