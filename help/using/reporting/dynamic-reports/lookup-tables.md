---
description: Fügen Sie Daten in die Protokolldateien des Berichts "Versandleistung"in Tabellen ein, die nur IDs enthalten. Fügen Sie Nicht-ID-Metadaten in separate Suchtabellen ein, um die Dateigröße und Verarbeitungszeiten zu reduzieren.
seo-description: Fügen Sie Daten in die Protokolldateien des Berichts "Versandleistung"in Tabellen ein, die nur IDs enthalten. Fügen Sie Nicht-ID-Metadaten in separate Suchtabellen ein, um die Dateigröße und Verarbeitungszeiten zu reduzieren.
seo-title: Verbessern der Verarbeitungszeiten für Protokolldateien mit Suchtabellen
solution: Audience Manager
title: Verbessern der Verarbeitungszeiten für Protokolldateien mit Suchtabellen
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Berichtsreferenz
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 18%

---

# Verbessern der Verarbeitungszeiten für Protokolldateien mit Suchtabellen{#improve-log-file-processing-times-with-lookup-tables}

Fügen Sie Daten in die Protokolldateien des Berichts &quot;Versandleistung&quot;in Tabellen ein, die nur IDs enthalten. Fügen Sie Nicht-ID-Metadaten in separate Suchtabellen ein, um die Dateigröße und Verarbeitungszeiten zu reduzieren.

<!-- 

c_lookup_tables.xml

 -->

## Protokolldatei-Metadaten erhöhen Dateigröße und Verarbeitungszeit

Eine typische Protokolldatei, die vom [!UICONTROL Delivery Performance] -Bericht verwendet wird, enthält in der Regel Tausende von Zeilen und Dutzende von Spalten. Sie besteht aus numerischen IDs und für Menschen lesbaren Informationen wie Namen für Kreative, Werbetreibende, Einfügeaufträge usw.

Diese Nicht-ID-Informationen werden als *`metadata`* (d. h. Informationen zu anderen Informationen) bezeichnet und in jede Zeile der Protokolldatei geschrieben.

Der Bericht [!UICONTROL Delivery Performance] funktioniert jedoch hauptsächlich mit den IDs in der Protokolldatei. Die Metadaten sind nützlich, aber wiederholt. Dadurch werden die Dateigröße und die Datenerfassungszeiten erhöht.

## Reduzierung der Dateigröße und Verkürzung der Verarbeitungszeit mit Indextabellen

Um die Leistung zu verbessern, sollte Ihre Hauptdatendatei nur IDs enthalten. Fügen Sie Metadaten in eine separate Lookup- (oder Index-) Tabelle ein und verknüpfen Sie diese Datensätze mit der Hauptdatei, wobei eine für beide gemeinsame Schlüsselvariable vorhanden ist.

## Verringern der Dateigröße durch Suchtabellen

Angenommen, Sie haben eine Datendatei, die der unten stehenden ähnelt.

| Benutzer-ID | Anzeigen-ID | Anzeigenname | Bestell-ID | Auftragsname | Advertiser-ID | Advertiser Name |
|---|---|---|---|---|---|---|
| 1 | 111 | Shoe A | 456 | Turnschuhe | 27 | Unternehmen A |
| 2 | 111 | Shoe A | 456 | Turnschuhe | 27 | Unternehmen A |
| 3 | 111 | Shoe A | 456 | Turnschuhe | 27 | Unternehmen A |
| 4 | 222 | Schuhe B | 789 | Wandern | 14 | Unternehmen B |
| 5 | 222 | Schuhe B | 789 | Wandern | 14 | Unternehmen B |

<br>

Im Folgenden finden Sie die gleiche Protokolldatei mit entfernten Metadaten. Die Datei ist kleiner und einfacher zu verarbeiten, wenn sie nur aus IDs besteht.

| Benutzer-ID | Anzeigen-ID | Bestell-ID | Advertiser-ID |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 1 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Die nachstehende Lookup-Datei enthält die Metadaten und kann mit der Anzeigen-ID wieder mit der Hauptdatei verknüpft werden. Beachten Sie auch die Größe. Anstatt jeden Advertiser mehrmals zu wiederholen, benötigen Sie nur jeweils eine Referenz.

| Anzeigen-ID | Anzeigenname | Auftragsname | Advertiser Name |
|---|---|---|---|
| 111 | Shoe A | Turnschuhe | Unternehmen A |
| 222 | Schuhe B | Wandern | Unternehmen B |

## APIs können die Notwendigkeit von Suchtabellen eliminieren

Wenn Ihr Adserving-System über eine API verfügt, müssen Sie möglicherweise keine Metadaten in einer Lookup-Datei senden. Möglicherweise können wir diese Informationen über die API abrufen. In diesem Fall sollten Ihre Protokolldateien nur IDs enthalten. Wir arbeiten mit Ihnen zusammen, um zu ermitteln, ob Metadaten über eine API abgerufen werden können.
