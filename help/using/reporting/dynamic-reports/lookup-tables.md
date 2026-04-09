---
description: Fügen Sie Daten in die Protokolldateien des Versandleistungsberichts in Tabellen ein, die nur IDs enthalten. Fügen Sie Nicht-ID-Metadaten in separate Suchtabellen ein, um die Dateigröße und die Verarbeitungszeiten zu reduzieren.
seo-description: Put data in Delivery Performance report log files into tables that contain IDs only. Put non-ID metadata in separate lookup tables to help reduce file size and processing times.
seo-title: Improve Log File Processing Times with Lookup Tables
solution: Audience Manager
title: Verkürzen der Verarbeitungszeiten von Protokolldateien mit Lookup-Tabellen
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Reporting Reference
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
TQID: https://experienceleague.adobe.com/9eLSmpl5-daNV5NgXrPfLThoIlMibaOtbgrsuqfkeCI
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a99472c1-6aae-4c7a-8aa0-f60636369620id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6cid: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 464
ht-degree: 14%

---

# Verkürzen der Verarbeitungszeiten von Protokolldateien mit Lookup-Tabellen{#improve-log-file-processing-times-with-lookup-tables}

Fügen Sie Daten in die Protokolldateien des Versandleistungsberichts in Tabellen ein, die nur IDs enthalten. Fügen Sie Nicht-ID-Metadaten in separate Suchtabellen ein, um die Dateigröße und die Verarbeitungszeiten zu reduzieren.

<!-- 

c_lookup_tables.xml

 -->

## Protokolldatei-Metadaten erhöhen die Dateigröße und die Verarbeitungszeit

Eine typische Protokolldatei, die vom [!UICONTROL Delivery Performance] verwendet wird, enthält in der Regel Tausende von Zeilen und Dutzende von Spalten. Es besteht aus numerischen IDs und von Menschen lesbaren Informationen wie Namen für Kreative, Werbetreibende, Insertionsaufträge usw.

Diese Nicht-ID-Informationen werden als *`metadata`* (d. h. Informationen über andere Informationen) bezeichnet und in jede Zeile der Protokolldatei geschrieben.

Der [!UICONTROL Delivery Performance]-Bericht funktioniert jedoch hauptsächlich mit den IDs in der Protokolldatei. Die Metadaten sind nützlich, aber sich wiederholend. Dies erhöht die Dateigröße und die Datenaufnahmezeiten.

## Verringern der Dateigröße und Verkürzen der Verarbeitungszeit mit Indextabellen

Um die Leistung zu verbessern, sollte Ihre Hauptdatendatei nur IDs enthalten. Fügen Sie Metadaten in eine separate Lookup- (oder Index-)Tabelle ein und verknüpfen Sie diese Datensätze mit der Hauptdatei mit einer gemeinsamen Schlüsselvariablen.

## Verringern der Dateigröße durch Lookup-Tabellen

Angenommen, Sie haben eine Datendatei, die der folgenden ähnelt.

| Benutzer-ID | Anzeigen-ID | Anzeigenname | Bestell-ID | Bestellname | Advertiser-ID | Advertiser-Name |
|---|---|---|---|---|---|---|
| 1 | 111 | Schuh A | 456 | Turnschuhe | 27 | Unternehmen A |
| 2 | 111 | Schuh A | 456 | Turnschuhe | 27 | Unternehmen A |
| 3 | 111 | Schuh A | 456 | Turnschuhe | 27 | Unternehmen A |
| 4 | 222 | Schuh B | 789 | Wandern | 14 | Unternehmen B |
| 5 | 222 | Schuh B | 789 | Wandern | 14 | Unternehmen B |

<br> 

Hier sehen Sie dieselbe Protokolldatei mit entfernten Metadaten. Die Datei ist kleiner und einfacher zu verarbeiten, wenn sie nur aus IDs besteht.

| Benutzer-ID | Anzeigen-ID | Bestell-ID | Advertiser-ID |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Die nachstehende Lookup-Datei enthält die Metadaten und kann mit der Anzeigen-ID mit der Hauptdatei verknüpft werden. Beachten Sie auch die Größe. Anstatt die einzelnen Advertiser mehrmals zu wiederholen, benötigen Sie nur jeweils eine Referenz.

| Anzeigen-ID | Anzeigenname | Bestellname | Advertiser-Name |
|---|---|---|---|
| 111 | Schuh A | Turnschuhe | Unternehmen A |
| 222 | Schuh B | Wandern | Unternehmen B |

## APIs können die Notwendigkeit von Lookup-Tabellen beseitigen

Wenn Ihr Anzeigenverwaltungssystem über eine API verfügt, müssen Sie möglicherweise keine Metadaten in einer Lookup-Datei senden. Wir können diese Informationen möglicherweise über die API abrufen. In diesem Fall sollten die Protokolldateien nur IDs enthalten. Wir ermitteln gemeinsam mit Ihnen, ob Metadaten über eine API abgerufen werden können.
