---
description: Zu den Datenverarbeitungskomponenten gehören Hadoop, Snowflake, SOLR und Tableau.
seo-description: Data processing components include Hadoop, Snowflake, SOLR, and Tableau.
seo-title: Data Processing Components
solution: Audience Manager
title: Datenverarbeitungskomponenten
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: System Components
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 1%

---

# Datenverarbeitungskomponenten{#data-processing-components}

Zu den Datenverarbeitungskomponenten gehören Hadoop, Snowflake, SOLR und Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager verwendet die folgenden Komponenten zur Verarbeitung von Daten:

## Hadoop {#hadoop}

In [!DNL Audience Manager] ist Hadoop die Hauptdatenbank, die alles enthält, was [!DNL Audience Manager] über einen Benutzer weiß. Wenn beispielsweise die [Profil-Cache-Server](../../reference/system-components/components-data-collection.md) Protokolldateien erstellen, die Daten zu Ihren Benutzern enthalten, werden diese Daten zur Speicherung an Hadoop gesendet. Weitere wichtige Hadoop-Elemente sind:

* **Hive:** Ein Data Warehouse für Hadoop. Hive verwaltet Ad-hoc-Abfragen für die in Hadoop gespeicherten Daten.

* **HBase:** Eine sehr große Hadoop-Datenbank. Es verarbeitet und verwaltet eingehende und ausgehende Daten, Eigenschaftsregeln, algorithmische Modellierungsinformationen und führt viele andere Funktionen aus, die mit dem Speichern und Verschieben von Daten in verschiedene Systeme zusammenhängen.

Kunden haben keinen direkten Zugriff auf diese Systeme. Kunden arbeiten jedoch indirekt mit ihnen, da diese Komponenten wichtige Daten über ihre Site-Besucher speichern.

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/) ist eine massive Cloud-Datenbank. Es stellt Daten für viele Dashboard-Diagramme und deren zugehörige Textfelder bereit, die die Änderung in % für jedes Element im Diagramm anzeigen. Wenn Sie [!DNL Audience Manager] verwenden und sich die Dashboard-Berichte ansehen, interagieren Sie mit den von [!UICONTROL Snowflake] bereitgestellten Daten.



![](assets/dashboardreport.png)

Dies ist keineswegs eine umfassende Liste, aber einige häufig verwendete Dashboard-Berichte, für die [!UICONTROL Snowflake] zuständig ist, umfassen Folgendes:

* [Täglicher Bericht zur Eigenschaftsvarianz](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Alle Überschneidungsberichte (Informationen zu den einzelnen Überschneidungsberichten finden Sie im Abschnitt [Interaktive Berichte](/help/using/reporting/dynamic-reports/dynamic-reports.md) ).
* [Bericht zu nicht verwendeten Signalen](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR ist ein Open-Source-Datenbank- und Serversystem von Apache. Sie bietet robuste und schnelle Suchfunktionen für unsere großen Datensätze. Als [!DNL Audience Manager] -Kunde können Sie SOLR in Aktion sehen, wenn Sie Segmente erstellen. Sie stellt Daten für den Bericht [!UICONTROL Estimated Historic Segment Size] bereit. SOLR ist aufgrund seiner Schnelligkeit für diese Rolle ideal. Beispielsweise kann SOLR die Daten der historischen Größe aktualisieren, während Sie Regeln erstellen und einem Segment neue Eigenschaften hinzufügen.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] verwendet [Tableau](https://www.tableausoftware.com/), um Daten in den [interaktiven Berichten](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) und in den [Audience Optimization-Berichten](../../reporting/audience-optimization-reports/audience-optimization-reports.md) anzuzeigen. Die interaktiven Berichte zeigen Leistungs- und Überlagerungsdaten für Eigenschaften und Segmente an. Statt Zahlen in Spalten und Zeilen zu verwenden, geben sie Daten mit unterschiedlichen Formen, Farben und Größen zurück. Darüber hinaus können Sie einzelne Datenpunkte oder Datenpunktgruppen auswählen und im Drilldown-Verfahren in die Berichtsergebnisse navigieren, um weitere Details zu erhalten. Diese Visualisierungstechniken und die Berichtsinteraktivität erleichtern das Verständnis großer Mengen numerischer Daten.



![](assets/advertiser_analytics.png)
