---
description: Stellen Sie Daten in die Protokolldateien des Bereitstellungsberichts in Tabellen ein, die nur IDs enthalten. Sie können Nicht-ID-Metadaten in separaten Suchtabellen einfügen, um die Dateigröße und Verarbeitungszeiten zu reduzieren.
seo-description: Stellen Sie Daten in die Protokolldateien des Bereitstellungsberichts in Tabellen ein, die nur IDs enthalten. Sie können Nicht-ID-Metadaten in separaten Suchtabellen einfügen, um die Dateigröße und Verarbeitungszeiten zu reduzieren.
seo-title: Verbessern der Protokolldateiverarbeitung mit Suchtabellen
solution: Audience Manager
title: Verbessern der Protokolldateiverarbeitung mit Suchtabellen
uuid: ffc 77618-474 b -455 e -9 c 91-15 b 32 fc 151 a 5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Improve Log File Processing Times with Lookup Tables{#improve-log-file-processing-times-with-lookup-tables}

Stellen Sie Daten in die Protokolldateien des Bereitstellungsberichts in Tabellen ein, die nur IDs enthalten. Sie können Nicht-ID-Metadaten in separaten Suchtabellen einfügen, um die Dateigröße und Verarbeitungszeiten zu reduzieren.

<!-- 

c_lookup_tables.xml

 -->

## Protokolldateimetadaten Vergrößern Dateigröße und Verarbeitungszeit

A typical log file used by the [!UICONTROL Delivery Performance] report usually contains thousands of rows and dozens of columns. Es besteht aus numerischen IDs und menschen lesbaren Informationen wie Namen für kreative Elemente, Werbetreibende, Einfügebestellungen usw.

This non-ID information is referred to as *`metadata`* (i.e., information about other information) and gets written in each row of the log file.

However, the [!UICONTROL Delivery Performance] report mainly works with the IDs in the log file. Die Metadaten sind nützlich, aber wiederholend. Dadurch werden die Dateigröße und die Datenerfassungszeiten erhöht.

## Dateigröße reduzieren und Verarbeitungszeit verkürzen mit Indextabellen

Um die Leistung zu verbessern, sollte Ihre Hauptdatendatei nur IDs enthalten. Stellen Sie Metadaten in eine separate Suchtabelle (oder Index) ein und verknüpfen Sie diese Datensätze mit der Hauptdatei mit einer gemeinsamen Variablen.

## So reduzieren Suchtabellen die Dateigröße

Nehmen wir an, Sie haben eine Datendatei, die wie unten dargestellt aussieht.

| Benutzer-ID | Anzeigen-ID | Anzeigenname | Bestell-ID | Auftragsname | Advertiser-ID | Name des Advertisers |
|---|---|---|---|---|---|---|
| 1 | 111 | Schuh A | 456 | Turnschuh | 27 | Firma A |
| 2 | 111 | Schuh A | 456 | Turnschuh | 27 | Firma A |
| 3 | 111 | Schuh A | 456 | Turnschuh | 27 | Firma A |
| 4 | 222 | Schuh B | 789 | Hiking | 14 | Firma B |
| 5 | 222 | Schuh B | 789 | Hiking | 14 | Firma B |

<br> 

Hier ist die Protokolldatei mit den entfernten Metadaten. Die Datei ist kleiner und einfacher zu verarbeiten, wenn sie nur aus IDs besteht.

| Benutzer-ID | Anzeigen-ID | Bestell-ID | Advertiser-ID |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Die nachfolgende Lookup-Datei enthält die Metadaten und kann mit der Anzeigen-ID zurück mit der Hauptdatei verknüpft werden. Notieren Sie sich auch die Größe. Anstatt jeden Advertiser mehrmals mehrfach zu wiederholen, benötigen Sie lediglich eine Referenz für jeden.

| Anzeigen-ID | Anzeigenname | Auftragsname | Name des Advertisers |
|---|---|---|---|
| 111 | Schuh A | Turnschuh | Firma A |
| 222 | Schuh B | Hiking | Firma B |

## Apis können den Bedarf an Suchtabellen löschen

Wenn Ihr Werbungssystem über eine API verfügt, müssen Sie Metadaten möglicherweise nicht in einer Lookup-Datei senden. Wir können diese Informationen eventuell über die API abrufen. In diesem Fall sollten Ihre Protokolldateien nur IDs enthalten. Wir arbeiten mit Ihnen zusammen, um festzustellen, ob Metadaten über eine API abgerufen werden können.

>[!MORE_ LIKE_ THIS]
>
>* [Bereitstellung und Leistungsbericht](../../reporting/dynamic-reports/delivery-performance-report.md)

