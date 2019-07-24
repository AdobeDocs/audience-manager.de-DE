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


# Customer Data Feed FAQ{#customer-data-feed-faq}

Häufig gestellte Fragen zu Kundendatenfeeds (CDF).

## Amazon S3 Storage {#amazon-s3-storage}

**Wo[!DNL Amazon]befindet sich meine CDF-Datei?**

Your CDF file is stored in the `aam-cdf` root directory on an [!DNL Amazon S3] server. This default bucket is managed by [!DNL Audience Manager]. See also [Customer Data Feed File Naming Conventions](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**Ist mein Speicher sicher?**

Ja. Kunden erhalten nur Zugriff auf ihren eigenen Speicherplatz. Sie haben schreibgeschützten Zugriff auf Ihren Speicherbehälter. Sie haben keinen Schreibzugriff.

<br> 

**Kann ich meine Speicherbehälter anpassen oder Dateien in einem anderen Verzeichnis speichern?**

Nein. Es sind keine benutzerdefinierten und alternativen Speicheroptionen verfügbar.

<br> 

**In meinem Verzeichnis fehlt eine Datei für eine bestimmte Stunde. Where is it?**

A missing file means [!DNL Audience Manager] was not able to process your CDF files for that hour. Dies geschieht normalerweise, wenn unsere Server bei der Verarbeitung von CDF-Dateien hinter uns kommen. In diesem Fall geht Ihre Datei nicht verloren. Sie wird in einem späteren stündlichen Verzeichnis angezeigt, nachdem unser System die Möglichkeit haben konnte, sich abzufangen. See also, [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**Woher weiß ich, wann meine CDF-Dateien bereit sind?**

See [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## File Sizes {#file-sizes}

**Welche Art von Dateigrößen sollte ich erwarten? How big is an average CDF file?**

Es ist schwierig, Dateigrößen zu schätzen. Außerdem kann jede Datei eine andere Größe haben. Die Größen variieren von Stunde zu Stunde und von Tag zu Tag. Wenn Sie CDF-Dateien erhalten, hilft es Ihnen, eine Vielzahl von Daten zu verwalten.

<br> 

**Wie viele Dateien werden erhalte?**

Auch dies ist schwer zu schätzen. Wenn Sie jedoch CDF-Dateien erhalten, hilft es Ihnen, eine Vielzahl von Daten zu verwalten.

<br> 

## Data Integrity {#data-integrity}

**Wie kann ich die Integrität der auf Amazon S 3 hochgeladenen Daten prüfen?**

Files exceeding 16MiB in size are split into 16MiB chunks and uploaded to [!DNL Amazon S3] using multi-part upload.

[!DNL Amazon] generiert einen `ETag` Wert für mehrteilige Uploads. Zuerst werden die einzelnen MD 5-Prüfsummen jedes hochgeladenen Teils berechnet und anschließend in eine einzelne Zeichenfolge verkettet. Anschließend berechnet sie die MD 5-Prüfsumme der Zeichenfolge. The resulting checksum (the `ETag`) is then appended with a hyphen and the total number of parts used for upload. For instance, the `ETag` for a file that was split into 5 parts during upload could look something like this: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**Wie lange speichern Sie CDF-Dateien?**

Daten werden nach 8 (8) Tagen gelöscht.

<br> 

**Kann ich CDF-Dateien rückwirkend oder für vorherige Tage abrufen?**

Sie können in den letzten 8 Tagen nur CDF-Dateien generieren. CDF-Dateien für Intervalle, die älter als die letzten 8 Tage sind, können nicht erneut generiert werden.

>[!MORE_ LIKE_ THIS]
>
>* [Kundendatenfeeds](../features/cdf-files.md)

