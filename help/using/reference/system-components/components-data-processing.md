---
description: Zu den Datenverarbeitungskomponenten gehören Hadoop, Snowflake, SOLR und Tableau.
seo-description: Zu den Datenverarbeitungskomponenten gehören Hadoop, Snowflake, SOLR und Tableau.
seo-title: Datenverarbeitungskomponenten
solution: Audience Manager
title: Datenverarbeitungskomponenten
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 3%

---


# Datenverarbeitungskomponenten{#data-processing-components}

Zu den Datenverarbeitungskomponenten gehören Hadoop, Snowflake, SOLR und Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager verwendet die folgenden Komponenten zur Datenverarbeitung:

## Hadoop {#hadoop}

In [!DNL Audience Manager]Hadoop ist die Hauptdatenbank, die alles über einen Benutzer [!DNL Audience Manager] weiß. Wenn der [Profil-Cache-Server](../../reference/system-components/components-data-collection.md) beispielsweise Protokolldateien mit Benutzerdaten erstellt, sendet er diese Daten zur Datenspeicherung an Hadoop. Weitere wichtige Hadoop-Elemente sind:

* **Hive:** Eine data warehouse für Hadoop. Hive verwaltet Ad-hoc-Abfragen an den in Hadoop gespeicherten Daten.

* **HBase:** Eine sehr große Hadoop-Datenbank. Es verarbeitet und verwaltet eingehende und ausgehende Daten, Eigenschaftsregeln, algorithmische Modellierungsinformationen und führt viele andere Funktionen zum Speichern und Verschieben von Daten auf verschiedene Systeme aus.

Kunden haben keinen direkten Zugriff auf diese Systeme. Kunden arbeiten jedoch indirekt mit ihnen, da diese Komponenten wichtige Daten über ihre Site-Besucher speichern.

## Schneeflocke {#snowflake}

[Schneeflocke](https://www.snowflake.net/) ist eine riesige Cloud-Datenbank. Es stellt Daten für viele der Dashboard-Diagramme und die zugehörigen Textfelder bereit, die die Änderung in % für jedes Element im Diagramm anzeigen. Wenn Sie die Dashboard-Berichte verwenden [!DNL Audience Manager] und sich diese ansehen, interagieren Sie mit den von [!UICONTROL Snowflake]Ihnen bereitgestellten Daten.



![](assets/dashboardreport.png)

Dies ist keineswegs eine umfassende Liste, aber einige häufige Dashboard-Berichte, für die folgende Aufgaben [!UICONTROL Snowflake] zuständig sind:

* [Täglicher Bericht zur Eigenschaftsvarianz](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Alle Überschneidungsberichte (Informationen zu den einzelnen Überschneidungsberichten finden Sie im Abschnitt [Interaktive Berichte](/help/using/reporting/dynamic-reports/dynamic-reports.md) ).
* [Bericht zu nicht verwendeten Signalen](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR ist eine Open-Source-Datenbank und ein Serversystem von Apache. Es bietet robuste und schnelle Suchfunktionen für unsere großen Datensätze. Als [!DNL Audience Manager] Kunde können Sie SOLR in Aktion sehen, wenn Sie Segmente erstellen. Er stellt Daten für den [!UICONTROL Estimated Historic Segment Size] Bericht bereit. SOLR ist aufgrund seiner Geschwindigkeit ideal für diese Rolle. SOLR kann beispielsweise die Daten der historischen Größe aktualisieren, wenn Sie Regeln erstellen und neue Eigenschaften zu einem Segment hinzufügen.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] verwendet [Tableau](https://www.tableausoftware.com/) , um Daten in den [interaktiven Berichten](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) und den [Audiencen-Optimierungsberichten](../../reporting/audience-optimization-reports/audience-optimization-reports.md)anzuzeigen. Die interaktiven Berichte zeigen Leistungs- und Überlagerungsdaten für Eigenschaften und Segmente an. Statt in Spalten und Zeilen angeordnete Zahlen zu verwenden, geben sie Daten mit unterschiedlichen Formen, Farben und Größen zurück. Darüber hinaus können Sie einzelne oder Gruppen von Datenpunkten auswählen und im Drilldown-Verfahren die Berichtsergebnisse aufschlüsseln, um weitere Details zu erhalten. Diese Visualisierungstechniken und die Berichtsinteraktivität erleichtern das Verständnis zahlreicher numerischer Daten.



![](assets/advertiser_analytics.png)

