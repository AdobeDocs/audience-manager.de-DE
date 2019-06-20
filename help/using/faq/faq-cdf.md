---
description: Häufig gestellte Fragen zu Kundendatenfeeds (CDF).
seo-description: Häufig gestellte Fragen zu Kundendatenfeeds (CDF).
seo-title: Häufig gestellte Fragen zu Kundendaten
solution: Audience Manager
title: Häufig gestellte Fragen zu Kundendaten
uuid: 7183 b 3 e 2-e 999-4 e 1 e -892 f -2 bab 335 c 13 b 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Häufig gestellte Fragen zu Kundendaten{#customer-data-feed-faq}

Häufig gestellte Fragen zu Kundendatenfeeds (CDF).

## Amazon S 3 Storage {#amazon-s3-storage}

**Wo[!DNL Amazon]befindet sich meine CDF-Datei?**

Ihre CDF-Datei wird im `aam-cdf` Stammordner auf einem [!DNL Amazon S3] Server gespeichert. Dieses Standardpaket [!DNL Audience Manager]wird verwaltet. Siehe auch [Benennungskonventionen für Customer Data Feed](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**Ist mein Speicher sicher?**

Ja. Kunden erhalten nur Zugriff auf ihren eigenen Speicherplatz. Sie haben schreibgeschützten Zugriff auf Ihren Speicherbehälter. Sie haben keinen Schreibzugriff.

<br> 

**Kann ich meine Speicherbehälter anpassen oder Dateien in einem anderen Verzeichnis speichern?**

Nein. Es sind keine benutzerdefinierten und alternativen Speicheroptionen verfügbar.

<br> 

**In meinem Verzeichnis fehlt eine Datei für eine bestimmte Stunde. Wo ist es?**

Eine fehlende Datei konnte [!DNL Audience Manager] Ihre CDF-Dateien für diese Stunde nicht verarbeiten. Dies geschieht normalerweise, wenn unsere Server bei der Verarbeitung von CDF-Dateien hinter uns kommen. In diesem Fall geht Ihre Datei nicht verloren. Sie wird in einem späteren stündlichen Verzeichnis angezeigt, nachdem unser System die Möglichkeit haben konnte, sich abzufangen. Siehe auch Benachrichtigungen zur [Verarbeitung von Data Data Feed](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**Woher weiß ich, wann meine CDF-Dateien bereit sind?**

Siehe [Feed zur Verarbeitung von Datendateidaten für Kunden](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## Dateigrößen {#file-sizes}

**Welche Art von Dateigrößen sollte ich erwarten? Wie groß ist eine durchschnittliche CDF-Datei?**

Es ist schwierig, Dateigrößen zu schätzen. Außerdem kann jede Datei eine andere Größe haben. Die Größen variieren von Stunde zu Stunde und von Tag zu Tag. Wenn Sie CDF-Dateien erhalten, hilft es Ihnen, eine Vielzahl von Daten zu verwalten.

<br> 

**Wie viele Dateien werden erhalte?**

Auch dies ist schwer zu schätzen. Wenn Sie jedoch CDF-Dateien erhalten, hilft es Ihnen, eine Vielzahl von Daten zu verwalten.

<br> 

## Datenintegrität {#data-integrity}

**Wie kann ich die Integrität der auf Amazon S 3 hochgeladenen Daten prüfen?**

Dateien mit mehr als 16 mib werden in 16 mib-Blöcke aufgeteilt und in [!DNL Amazon S3] den mehrteiligen Upload hochgeladen.

[!DNL Amazon] generiert einen `ETag` Wert für mehrteilige Uploads. Zuerst werden die einzelnen MD 5-Prüfsummen jedes hochgeladenen Teils berechnet und anschließend in eine einzelne Zeichenfolge verkettet. Anschließend berechnet sie die MD 5-Prüfsumme der Zeichenfolge. Die resultierende Prüfsumme (die `ETag`) wird dann mit einem Bindestrich und der Gesamtanzahl der zum Hochladen verwendeten Teile angehängt. So könnte z. B. die Datei `ETag` für eine Datei, die während des Uploads in 5 Teile aufgeteilt wurde, wie folgt aussehen: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Datenaufbewahrung {#data-retension}

**Wie lange speichern Sie CDF-Dateien?**

Daten werden nach 8 (8) Tagen gelöscht.

<br> 

**Kann ich CDF-Dateien rückwirkend oder für vorherige Tage abrufen?**

Sie können in den letzten 8 Tagen nur CDF-Dateien generieren. CDF-Dateien für Intervalle, die älter als die letzten 8 Tage sind, können nicht erneut generiert werden.

>[!MORE_ LIKE_ THIS]
>
>* [Kundendatenfeeds](../features/cdf-files.md)

