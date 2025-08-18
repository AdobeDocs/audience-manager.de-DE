---
description: Zu den Datenverarbeitungskomponenten gehören Hadoop, Snowflake, SOLR und Tableau.
seo-description: Data processing components include Hadoop, Snowflake, SOLR, and Tableau.
seo-title: Data Processing Components
solution: Audience Manager
title: Komponenten für die Datenverarbeitung
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: System Components
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 1%

---

# Komponenten für die Datenverarbeitung{#data-processing-components}

Zu den Datenverarbeitungskomponenten gehören Hadoop, Snowflake, SOLR und Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager verwendet die folgenden Komponenten zur Verarbeitung von Daten:

## Hadoop {#hadoop}

[!DNL Audience Manager] ist Hadoop die Hauptdatenbank, die alles enthält, was [!DNL Audience Manager] über einen Benutzer weiß. Wenn die [Profil-Cache-Server](../../reference/system-components/components-data-collection.md) beispielsweise Protokolldateien erstellen, die Daten über Ihre Benutzerinnen und Benutzer enthalten, werden diese Daten zur Speicherung an Hadoop gesendet. Weitere wichtige Elemente von Hadoop sind:

* **Hive:** Ein Data Warehouse für Hadoop. Hive verwaltet Ad-hoc-Abfragen an die in Hadoop gespeicherten Daten.

* **HBase:** Eine sehr große Hadoop-Datenbank. Es verarbeitet und verwaltet eingehende und ausgehende Daten, Eigenschaftsregeln, algorithmische Modellierungsinformationen und führt viele andere Funktionen aus, die mit dem Speichern und Verschieben von Daten in verschiedene Systeme zusammenhängen.

Kunden haben keinen direkten Zugriff auf diese Systeme. Kunden arbeiten jedoch indirekt mit ihnen, da diese Komponenten wichtige Daten über ihre Site-Besucher speichern.

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/) ist eine riesige Cloud-Datenbank. Es stellt Daten für viele der Dashboard-Diagramme und die zugehörigen Textfelder bereit, die die prozentuale Änderung für jedes Element im Diagramm anzeigen. Wenn Sie [!DNL Audience Manager] verwenden und sich die Dashboard-Berichte ansehen, interagieren Sie mit den von [!UICONTROL Snowflake] bereitgestellten Daten.



![](assets/dashboardreport.png)

Dies ist keine umfassende Liste, aber einige gängige Dashboard-Berichte, für die [!UICONTROL Snowflake] verantwortlich ist, umfassen:

* [Täglicher Bericht zur Eigenschaftsvarianz](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Alle Überschneidungsberichte (Informationen zu den einzelnen Überschneidungsberichten finden [ im Abschnitt ](/help/using/reporting/dynamic-reports/dynamic-reports.md)Interaktive Berichte„).
* [Bericht zu nicht verwendeten Signalen](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR ist ein Open-Source-Datenbank- und Server-System von Apache. Es bietet zuverlässige und schnelle Suchfunktionen für unsere großen Datensätze. Als [!DNL Audience Manager]-Kunde können Sie SOLR beim Erstellen von Segmenten in Aktion sehen. Es stellt Daten für den [!UICONTROL Estimated Historic Segment Size] bereit. SOLR ist aufgrund seiner Geschwindigkeit ideal für diese Rolle. Beispielsweise kann SOLR die Daten zur historischen Größe aktualisieren, während Sie Regeln erstellen und einem Segment neue Eigenschaften hinzufügen.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] verwendet [Tableau](https://www.tableausoftware.com/), um Daten in den [interaktiven Berichten](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) und den [Audience Optimization-Berichten](../../reporting/audience-optimization-reports/audience-optimization-reports.md) anzuzeigen. Die interaktiven Berichte zeigen Leistungs- und Überschneidungsdaten für Eigenschaften und Segmente an. Anstatt Zahlen zu verwenden, die in Spalten und Zeilen angeordnet sind, geben sie Daten mit unterschiedlichen Formen, Farben und Größen zurück. Darüber hinaus können Sie einzelne oder Gruppen von Datenpunkten auswählen und die Berichtsergebnisse aufschlüsseln, um weitere Details zu erhalten. Diese Visualisierungstechniken und die Interaktivität von Berichten erleichtern das Verständnis großer Mengen numerischer Daten.



![](assets/advertiser_analytics.png)
