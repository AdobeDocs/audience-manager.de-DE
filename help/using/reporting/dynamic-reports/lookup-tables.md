---
description: Fügen Sie Daten in die Protokolldateien des Versands Performance-Berichts in Tabellen ein, die nur IDs enthalten. Fügen Sie Nicht-ID-Metadaten in separate Suchtabellen ein, um Dateigröße und Verarbeitungszeit zu reduzieren.
seo-description: Fügen Sie Daten in die Protokolldateien des Versands Performance-Berichts in Tabellen ein, die nur IDs enthalten. Fügen Sie Nicht-ID-Metadaten in separate Suchtabellen ein, um Dateigröße und Verarbeitungszeit zu reduzieren.
seo-title: Verbessern der Verarbeitungszeiten für Protokolldateien mit Suchtabellen
solution: Audience Manager
title: Verbessern der Verarbeitungszeiten für Protokolldateien mit Suchtabellen
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 18%

---


# Verbessern der Verarbeitungszeiten für Protokolldateien mit Suchtabellen{#improve-log-file-processing-times-with-lookup-tables}

Fügen Sie Daten in die Protokolldateien des Versands Performance-Berichts in Tabellen ein, die nur IDs enthalten. Fügen Sie Nicht-ID-Metadaten in separate Suchtabellen ein, um Dateigröße und Verarbeitungszeit zu reduzieren.

<!-- 

c_lookup_tables.xml

 -->

## Protokolldatei-Metadaten erhöhen Dateigröße und Verarbeitungszeit

Eine typische Protokolldatei, die vom [!UICONTROL Delivery Performance]-Bericht verwendet wird, enthält in der Regel Tausende von Zeilen und Dutzende von Spalten. Es besteht aus numerischen IDs und für Menschen lesbaren Informationen wie Namen für kreative Elemente, Werbekunden, Einfügebestellungen usw.

Diese Nicht-ID-Informationen werden als *`metadata`* (d.h. Informationen zu anderen Informationen) bezeichnet und in jede Zeile der Protokolldatei geschrieben.

Der Bericht [!UICONTROL Delivery Performance] funktioniert jedoch hauptsächlich mit den IDs in der Protokolldatei. Die Metadaten sind nützlich, aber wiederholt. Dadurch wird die Dateigröße und die Datenerfassungszeit erhöht.

## Reduzierung der Dateigröße und Verkürzung der Verarbeitungszeit mit Indextabellen

Zur Verbesserung der Leistung sollte Ihre Hauptdatendatei nur IDs enthalten. Fügen Sie Metadaten in eine separate Nachschlagetabelle (oder Index) ein und verknüpfen Sie diese Datensätze mit der Hauptdatei, wobei beide Schlüsselvariablen gemeinsam sind.

## Reduzieren der Dateigröße durch Suchtabellen

Nehmen wir an, Sie haben eine Datendatei, die der unten stehenden ähnelt.

| Benutzer-ID | Anzeigen-ID | Anzeigenname | Bestell-ID | Auftragsname | Advertiser-ID | Anzeigenname |
|---|---|---|---|---|---|---|
| 1 | 111 | Schuh A | 456 | Turnschuhe | 27 | Firma A |
| 2 | 111 | Schuh A | 456 | Turnschuhe | 27 | Firma A |
| 3 | 111 | Schuh A | 456 | Turnschuhe | 27 | Firma A |
| 4 | 222 | Schuhe B | 789 | Wandern | 14 | Firma B |
| 5 | 222 | Schuhe B | 789 | Wandern | 14 | Firma B |

<br>

Hier ist die gleiche Protokolldatei mit den Metadaten entfernt. Die Datei ist kleiner und einfacher zu verarbeiten, wenn sie nur aus IDs besteht.

| Benutzer-ID | Anzeigen-ID | Bestell-ID | Advertiser-ID |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Die nachstehende Lookup-Datei enthält die Metadaten und kann mit der Anzeigen-ID wieder mit der Hauptdatei verknüpft werden. Beachten Sie auch die Größe. Anstatt jeden Anbieter mehrmals zu wiederholen, benötigen Sie nur einen Verweis für jeden Anbieter.

| Anzeigen-ID | Anzeigenname | Auftragsname | Anzeigenname |
|---|---|---|---|
| 111 | Schuh A | Turnschuhe | Firma A |
| 222 | Schuhe B | Wandern | Firma B |

## APIs können die Notwendigkeit von Suchtabellen beseitigen

Wenn Ihr Ad-Serving-System über eine API verfügt, müssen Sie möglicherweise keine Metadaten in einer Lookup-Datei senden. Wir können diese Informationen möglicherweise über die API abrufen. In diesem Fall sollten Ihre Protokolldateien nur IDs enthalten. Wir arbeiten mit Ihnen zusammen, um zu ermitteln, ob Metadaten über eine API abgerufen werden können.