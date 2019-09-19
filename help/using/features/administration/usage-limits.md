---
description: Audience Manager legt eine Höchstgrenze für die Anzahl der Eigenschaften, Segmente, Ziele und algorithmischen Modelle fest, die Sie für ein Konto erstellen können. Beschränkungen gelten für diese Elemente, unabhängig davon, ob sie in der Benutzeroberfläche oder programmgesteuert über API-Methoden erstellt wurden. Nutzungsbeschränkungen schützen Audience Manager vor automatisierten Prozessen, die möglicherweise versuchen, unsere APIs oder die Benutzeroberfläche zu gefährden.
seo-description: Audience Manager legt eine Höchstgrenze für die Anzahl der Eigenschaften, Segmente, Ziele und algorithmischen Modelle fest, die Sie für ein Konto erstellen können. Beschränkungen gelten für diese Elemente, unabhängig davon, ob sie in der Benutzeroberfläche oder programmgesteuert über API-Methoden erstellt wurden. Nutzungsbeschränkungen schützen Audience Manager vor automatisierten Prozessen, die möglicherweise versuchen, unsere APIs oder die Benutzeroberfläche zu gefährden.
seo-title: Nutzungsbeschränkungen
solution: Audience Manager
title: Nutzungsbeschränkungen
keywords: ID-Zuordnung, ID-Zuordnungen, Cookie-Zuordnungen
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
translation-type: tm+mt
source-git-commit: d893998e9e59dbce64195a167e267c6f7ed16f90

---


# Nutzungsbeschränkungen {#usage-limits}

Audience Manager legt eine Höchstgrenze für die Anzahl der Eigenschaften, Segmente, Ziele und algorithmischen Modelle fest, die Sie für ein Konto erstellen können. Beschränkungen gelten für diese Elemente, unabhängig davon, ob sie in der Benutzeroberfläche oder programmgesteuert mit [!DNL API] Methoden erstellt wurden. Nutzungsbeschränkungen schützen Audience Manager vor automatisierten Prozessen, die möglicherweise versuchen, unsere [!DNL API]s oder Benutzeroberfläche zu gefährden.

## ID-Zuordnungs-Begrenzung {#id-mapping-limits}

In der folgenden Tabelle sind die Grenzwerte für die [ID-Zuordnung](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) für Geräte-IDs aufgeführt. Sobald eine ID eine der unten stehenden Beschränkungen erreicht, fügt Audience Manager neue ID-Zuordnungen hinzu, die auf einer Logik [!DNL FIFO] (first in, first out) basieren, indem die älteste gespeicherte ID-Zuordnung entfernt und die neue hinzugefügt wird. Einzelheiten zu den von Audience Manager unterstützten IDs finden Sie im [Index der IDs](../../reference/ids-in-aam.md) in Audience Manager.

| ID-Zuordnung | Maximale Beschränkung |
|-----------|-------------- |
| Geräte-Advertising-ID (DAID) für geräteübergreifende ID (CRM-ID) | 100 Geräte-Advertising-IDs (DAIDs) bis 1 geräteübergreifende ID (CRM-ID) |
| Geräteübergreifende ID (CRM-ID) für Geräte-Advertising-ID (DAID) | 10 geräteübergreifende IDs (CRM-IDs) bis 1 Geräte-Advertising-ID (DAID) |
| Cookie/Browser-ID zu Cookie-/Browser-ID | 1000 Cookie-/Browser-IDs zu 1 Cookie-/Browser-ID |

## Elementgrenzen {#item-limits}

Die Tabellen zeigen die aktuellen Beschränkungen nach Elementtyp an. Sie können keine neuen Eigenschaften, Segmente, Ziele oder [!UICONTROL Algorithmic Models] Ziele erstellen, wenn Sie eine bestimmte Beschränkung für eines dieser Elemente erreichen. Wenn Sie einen Grenzwert erreichen, müssen Sie ein älteres Element löschen, bevor Sie ein neues erstellen können.

### Eigenschaftsbeschränkungen

| Eigenschaftstyp | Maximale Beschränkung |
| -------------------------- | ------------------------------------- |
| Eigenschaften insgesamt | 100,000 |
| Eigenschaften gesamt | 150,000. Weitere Informationen zur Qualifizierung von Eigenschaften finden Sie unter Qualifizierungsgrenze für Eigenschaften in der [Referenzhandbuch](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit)zu Eigenschaften. |
| Algorithmus | 50 |
| Regelbasiert | 100,000 |
| Onboarded | 100,000 |
| Ordnereigenschaften | 2,000 |

### Segmentbeschränkungen

| Segmenttyp | Maximale Beschränkung |
| -------------- | ------------- |
| Segmente insgesamt | 20,000 |

### Zielbeschränkungen

| Zieltyp | Maximale Beschränkung |
| ------------------ | ------------- |
| Ziele insgesamt | 1.000 |
| Cookie | 1.000 |
| URL | 1.000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Algorithmische Modellbeschränkungen

| Element | Maximale Beschränkung |
| -------- | ----- |
| Aktive Algorithmische Modelle | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| Algorithmische Modelle - maximale Zielgruppengröße | 25,000,000.  Beachten Sie, dass dieser Grenzwert nicht erhöht werden kann. Sie können die Größe der Zielgruppe verringern, indem Sie weniger Datenquellen für das Modell auswählen oder ein kürzeres Lookback-Fenster auswählen. |
| Maximale Anzahl ausgeschlossener Eigenschaften für ein Modell | 500. Siehe [Eigenschaftsausschluss in Algorithmischer Modellierung](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |

### Ordnerbeschränkungen

| Element | Maximale Beschränkung |
| ------------- | ------------------ |
| Eigenschaftsordner | 2,000.  Ihre Ordnerstruktur kann maximal 5 Stufen tief sein. |

### Abgeleitete Signalgrenzen

| Element | Maximale Beschränkung |
| --------------- | ------------- |
| Abgeleitete Signale | 50.000. |

### Beschränkung für Unternehmensbenutzerkonten

| Element | Maximale Beschränkung |
| ----------- | ------------- |
| Maximale Anzahl der Benutzerkonten für ein Unternehmen | 1.000. |

## Nutzung überwachen {#monitor-usage}

Sie können die Nutzung und die Beschränkungen für Ihr Konto unter **[!UICONTROL Administration > Limits]**. Zugriff erfordert Administratorberechtigungen.

![Nutzungsbeschränkungen für Bild](assets/usage-limits.png)

## Elementgrenzen erhöhen {#increase-item-limits}

Die hier aufgelisteten Standardbeschränkungen sollten ausreichend Platz für Ihre geschäftlichen Anforderungen bieten. Wenn Ihr Unternehmen diese Grenzwerte konsequent erreicht, wenden Sie sich an Ihren Kundenbetreuer, um eine Erhöhung zu besprechen.