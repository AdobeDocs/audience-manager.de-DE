---
description: Zu den Datenverarbeitungskomponenten gehören Hadoop, Snowflake, SOLR und Tableau.
seo-description: Zu den Datenverarbeitungskomponenten gehören Hadoop, Snowflake, SOLR und Tableau.
seo-title: Datenverarbeitungskomponenten
solution: Audience Manager
title: Datenverarbeitungskomponenten
uuid: d 458 d 869-7 a 23-4016-871 d -0 b 994 cf 4 af 06
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Processing Components{#data-processing-components}

Zu den Datenverarbeitungskomponenten gehören Hadoop, Snowflake, SOLR und Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager verwendet die folgenden Komponenten zum Verarbeiten von Daten:

## Hadoop {#hadoop}

In [!DNL Audience Manager], Hadoop is the master database that contains everything [!DNL Audience Manager] knows about a user. For example, when the [Profile Cache Servers](../../reference/system-components/components-data-collection.md) create log files that contain data about your users, it sends that data to Hadoop for storage. Weitere wichtige Hadoop-Elemente:

* **Hive:** Ein Data Warehouse für Hadoop. Hive verwaltet Ad-hoc-Abfragen auf die in Hadoop gespeicherten Daten.

* **Hbase:** Eine sehr große Hadoop-Datenbank. Sie verarbeitet und verwaltet eingehende und ausgehende Daten, Eigenschaftsregeln, algorithmische Modellinformationen und führt viele weitere Funktionen durch, mit denen Daten auf verschiedene Systeme gespeichert und verschoben werden.

Kunden haben keinen direkten Zugriff auf diese Systeme. Kunden arbeiten jedoch indirekt daran, da diese Komponenten wichtige Daten über ihre Site-Besucher speichern.

## Snowflake {#snowflake}

[Snowflake](https://www.snowflake.net/) ist eine umfangreiche Cloud-Datenbank. Es stellt Daten für viele Dashboard-Diagramme und zugehörige Textfelder bereit, die die % Änderung für jedes Element im Diagramm anzeigen. If you use [!DNL Audience Manager] and look at the dashboard reports, you're interacting with data provided by [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

This is by no means a comprehensive list, but some common dashboard reports that [!UICONTROL Snowflake] is responsible for include:

* [Bericht zu täglichen Eigenschaften](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* [Bereitstellung und Leistungsbericht](/help/using/reporting/dynamic-reports/delivery-performance-report.md)
* All the overlap reports (see the [Interactive Reports](/help/using/reporting/dynamic-reports/dynamic-reports.md) section for information about each overlap report).
* [Bericht zu nicht verwendeten Signalen](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR ist eine Open Source-Datenbank und ein Serversystem aus Apache. Es bietet robuste und schnelle Suchfunktionen über unsere großen Datensätze. As an [!DNL Audience Manager] customer, you can see SOLR in action when you build segments. It provides data to the [!UICONTROL Estimated Historic Segment Size] report. SOLR ist aufgrund seiner Geschwindigkeit ideal für diese Rolle. Beispielsweise kann SOLR die historischen Größendaten beim Erstellen von Regeln aktualisieren und einem Segment neue Eigenschaften hinzufügen.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] verwendet [Tableau](https://www.tableausoftware.com/) , um Daten in den [interaktiven Berichten](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) und den [Zielgruppenoptimierungsberichten anzuzeigen](../../reporting/audience-optimization-reports/audience-optimization-reports.md). Die interaktiven Berichte zeigen Leistungs- und Überlappungsdaten für Eigenschaften und Segmente an. Statt Zahlen in Spalten und Zeilen zu verwenden, werden Daten mit unterschiedlichen Formen, Farben und Größen zurückgegeben. Darüber hinaus können Sie für weitere Details einzelne Datenpunkte oder Datengruppen im Drilldown-Verfahren auswählen. Diese Visualisierungstechniken und Interaktivitätsinteraktivität erleichtern die Verständlichkeit von numerischen Daten.



![](assets/advertiser_analytics.png)

