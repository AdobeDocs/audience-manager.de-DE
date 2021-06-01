---
description: Häufig gestellte Fragen zu CDF (Customer Data Feed)-Dateien.
seo-description: Häufig gestellte Fragen zu CDF (Customer Data Feed)-Dateien.
seo-title: Häufig gestellte Fragen zu Kundendaten-Feeds
solution: Audience Manager
title: Häufig gestellte Fragen zu Kundendaten-Feeds
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
feature: Kundendaten-Feeds
exl-id: a948accc-6bec-4748-bcc8-2b77acf6b96a
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 100%

---

# Häufig gestellte Fragen zu Kundendaten-Feeds {#customer-data-feed-faq}

Häufig gestellte Fragen zu CDF (Customer Data Feed)-Dateien.

## Amazon S3-Datenspeicherung {#amazon-s3-storage}

**Wo wird meine CDF-Datei in [!DNL Amazon] gespeichert?**

Ihre CDF-Datei wird im `aam-cdf`-Stammverzeichnis auf einem [!DNL Amazon S3]-Server gespeichert. Dieser Standardbehälter wird von [!DNL Audience Manager] verwaltet. Siehe auch [Namenskonventionen für CDF-Dateien](../features/cdf-files.md#cdf-naming-conventions).

<br>

**Ist mein Datenspeicherbehälter sicher?**

Ja. Kunden haben nur Zugriff auf ihren eigenen Datenspeicherungsbereich. Sie haben nur Lesezugriff auf Ihren Datenspeicherbehälter. Sie haben keinen Schreibzugriff.

<br> 

**Kann ich meinen Datenspeicherbehälter anpassen oder Dateien in einem anderen Verzeichnis speichern?**

Nein. Es stehen keine Optionen für Anpassung und alternative Datenspeicherung zur Verfügung.

<br> 

**In meinem Verzeichnis fehlt eine Datei für eine bestimmte Stunde. Wo ist sie?**

Eine fehlende Datei bedeutet, dass [!DNL Audience Manager] Ihre CDF-Dateien für diese Stunde nicht verarbeiten konnte. Dies geschieht normalerweise, wenn unsere Server mit der Verarbeitung von CDF-Dateien in Verzug geraten. In diesem Fall geht die Datei nicht verloren. Sie wird in einem späteren stündlichen Verzeichnis angezeigt, nachdem unser System die Möglichkeit hat, den Verzug aufzuholen. Siehe auch [Verarbeitungsbenachrichtigungen für CDF-Dateien](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**Woher weiß ich, wann meine CDF-Dateien fertig sind?**

Siehe [Verarbeitungsbenachrichtigungen für CDF-Dateien](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## Dateigrößen {#file-sizes}

**Welche Dateigrößen sollte ich erwarten? Wie groß ist eine durchschnittliche CDF-Datei?**

Es ist schwierig, die Dateigrößen abzuschätzen. Jede Datei kann eine andere Größe haben. Die Größen variieren von Stunde zu Stunde und von Tag zu Tag. Wenn Sie CDF-Dateien erhalten, ist es hilfreich, sich auf die Verwaltung einer Vielzahl von Daten vorzubereiten.

<br> 

**Wie viele Dateien erhalte ich?**

Auch das ist schwer abzuschätzen. Wenn Sie jedoch CDF-Dateien erhalten, ist es hilfreich, sich auf die Verwaltung einer Vielzahl von Daten vorzubereiten.

<br> 

## Datenintegrität {#data-integrity}

**Wie kann ich die Integrität der auf Amazon S3 hochgeladenen Daten überprüfen?**

[!DNL Amazon] teilt große Dateien in kleinere Teile auf und lädt sie mithilfe des mehrteiligen Uploads auf [!DNL Amazon S3] hoch. Anschließend wird ein `ETag`-Wert für den mehrteiligen Upload generiert. Zuerst werden die einzelnen MD5-Prüfsummen jedes hochgeladenen Teils berechnet und dann zu einer einzigen Zeichenfolge verkettet. Anschließend wird die MD5-Prüfsumme der Zeichenfolge berechnet. Die resultierende Prüfsumme (das `ETag`) wird dann mit einem Bindestrich und der Gesamtanzahl der zum Hochladen verwendeten Teile angehängt. Zum Beispiel könnte das `ETag` für eine Datei, die beim Hochladen in 5 Teile aufgeteilt wurde, etwa so aussehen: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Datenaufbewahrung {#data-retension}

**Wie lange speichern Sie CDF-Dateien?**

Die Daten werden nach 8 (acht) Tagen gelöscht.

<br> 

**Kann ich CDF-Dateien rückwirkend oder für frühere Tage erhalten?**

Sie können CDF-Dateien nur für die letzten 8 Tage erstellen. CDF-Dateien für Intervalle, die älter als die letzten 8 Tage sind, können nicht erneut generiert werden.

>[!MORELIKETHIS]
>
>* [Kundendaten-Feeds](../features/cdf-files.md)

