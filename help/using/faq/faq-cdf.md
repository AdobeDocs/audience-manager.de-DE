---
description: Häufig gestellte Fragen zu CDF-Dateien (Customer Data Feed).
seo-description: Häufig gestellte Fragen zu CDF-Dateien (Customer Data Feed).
seo-title: Häufig gestellte Fragen zum Kundendatenfeed
solution: Audience Manager
title: Häufig gestellte Fragen zum Kundendatenfeed
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
translation-type: tm+mt
source-git-commit: 7018705c130bf7c65f3a69da5e4bd9e0666423bc

---


# Häufig gestellte Fragen zum Kundendatenfeed{#customer-data-feed-faq}

Häufig gestellte Fragen zu CDF-Dateien (Customer Data Feed).

## Amazon S3-Datenspeicherung {#amazon-s3-storage}

**Wo ist meine CDF-Datei gespeichert[!DNL Amazon]?**

Ihre CDF-Datei wird im `aam-cdf` Stammverzeichnis auf einem [!DNL Amazon S3] Server gespeichert. Dieser Standardbehälter wird von verwaltet [!DNL Audience Manager]. Siehe auch [Benutzerdaten-Feed-Dateibenennungskonventionen](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**Ist meine Datenspeicherung sicher?**

Ja. Kunden haben nur Zugriff auf ihren eigenen Datenspeicherung-Bereich. Sie haben einen schreibgeschützten Zugriff auf Ihre Datenspeicherung. Sie haben keinen Schreibzugriff.

<br> 

**Kann ich meinen Datenspeicherung-Bucket anpassen oder Dateien in einem anderen Verzeichnis speichern?**

Nein. Es stehen keine Optionen für Anpassung und alternative Datenspeicherung zur Verfügung.

<br> 

**In meinem Verzeichnis fehlt eine Datei für eine bestimmte Stunde. Wo ist es?**

Eine fehlende Datei bedeutet, dass Ihre CDF-Dateien für diese Stunde nicht verarbeitet werden [!DNL Audience Manager] konnten. Dies geschieht normalerweise, wenn unsere Server bei der Verarbeitung von CDF-Dateien zurückbleiben. In diesem Fall geht Ihre Datei nicht verloren. Es wird in einem späteren stündlichen Verzeichnis angezeigt, nachdem unser System die Möglichkeit hat, aufzuholen. Siehe auch Benachrichtigungen zur Verarbeitung von [Kundendaten-Feeds](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**Woher weiß ich, wann meine CDF-Dateien fertig sind?**

Siehe Benachrichtigungen zur Verarbeitung von [Kundendaten-Feed-Dateien](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## Dateigrößen {#file-sizes}

**Welche Dateigrößen sollte ich erwarten? Wie groß ist eine durchschnittliche CDF-Datei?**

Es ist schwierig, die Dateigrößen einzuschätzen. Und jede Datei kann eine andere Größe haben. Die Größe variiert von Stunde zu Stunde und von Tag zu Tag. Wenn Sie CDF-Dateien erhalten möchten, ist es hilfreich, sich auf die Verwaltung einer Vielzahl von Daten vorzubereiten.

<br> 

**Wie viele Dateien erhalte ich?**

Auch das ist schwer einzuschätzen. Wenn Sie jedoch CDF-Dateien erhalten möchten, ist es hilfreich, sich auf die Verwaltung einer Vielzahl von Daten vorzubereiten.

<br> 

## Datenintegrität {#data-integrity}

**Wie kann ich die Integrität der auf Amazon S3 hochgeladenen Daten überprüfen?**

[!DNL Amazon] Teilt große Dateien in kleinere Teile und lädt sie hoch, um sie mit dem mehrteiligen Upload zu [!DNL Amazon S3] verwenden. Dann wird ein `ETag` Wert für den mehrteiligen Upload generiert. Zuerst werden die einzelnen MD5-Prüfsummen jedes hochgeladenen Teils berechnet und dann in einer einzigen Zeichenfolge verkettet. Anschließend wird die MD5-Prüfsumme der Zeichenfolge berechnet. Die resultierende Prüfsumme (die `ETag`) wird dann mit einem Bindestrich und der Gesamtanzahl der zum Hochladen verwendeten Teile angehängt. Beispielsweise könnte die `ETag` für eine Datei, die während des Hochladevorgangs in 5 Teile aufgeteilt wurde, wie folgt aussehen: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**Wie lange speichern Sie CDF-Dateien?**

Die Daten werden nach 8 (8) Tagen gelöscht.

<br> 

**Kann ich CDF-Dateien rückwirkend oder für frühere Tage erhalten?**

Sie können CDF-Dateien nur für die letzten 8 Tage erstellen. CDF-Dateien für Intervalle, die älter als die letzten 8 Tage sind, können nicht erneut generiert werden.

>[!MORELIKETHIS]
>
>* [Kundendatenfeeds](../features/cdf-files.md)

