---
description: Audience Manager legt eine Höchstgrenze für die Anzahl der Eigenschaften, Segmente, Ziele und algorithmischen Modelle fest, die Sie für ein Konto erstellen können. Beschränkungen gelten für diese Elemente, unabhängig davon, ob sie in der Benutzeroberfläche oder programmgesteuert über API-Methoden erstellt wurden. Nutzungsbeschränkungen schützen Audience Manager vor automatisierten Prozessen, die möglicherweise versuchen, unsere APIs oder die Benutzeroberfläche zu gefährden.
seo-description: Audience Manager legt eine Höchstgrenze für die Anzahl der Eigenschaften, Segmente, Ziele und algorithmischen Modelle fest, die Sie für ein Konto erstellen können. Beschränkungen gelten für diese Elemente, unabhängig davon, ob sie in der Benutzeroberfläche oder programmgesteuert über API-Methoden erstellt wurden. Nutzungsbeschränkungen schützen Audience Manager vor automatisierten Prozessen, die möglicherweise versuchen, unsere APIs oder die Benutzeroberfläche zu gefährden.
seo-title: Nutzungsbeschränkungen
solution: Audience Manager
title: Nutzungsbeschränkungen
keywords: ID mapping, ID mappings, cookie mappings
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 6%

---


# Nutzungsbeschränkungen {#usage-limits}

Audience Manager legt eine Höchstgrenze für die Anzahl der Eigenschaften, Segmente, Ziele und algorithmischen Modelle fest, die Sie für ein Konto erstellen können. Beschränkungen gelten für diese Elemente, unabhängig davon, ob sie in der Benutzeroberfläche oder programmgesteuert mit [!DNL API] Methoden erstellt wurden. Nutzungsbeschränkungen schützen Audience Manager vor automatisierten Prozessen, die unsere [!DNL API]s oder Benutzeroberfläche beeinträchtigen könnten.

## ID-Zuordnungs-Begrenzung {#id-mapping-limits}

In der folgenden Tabelle werden die Grenzwerte für die [ID-Zuordnung](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) für Geräte-IDs Liste. Sobald eine ID eine der unten stehenden Beschränkungen erreicht, fügt Audience Manager neue ID-Zuordnungen hinzu, die auf einer FIFO-Logik (first in, first out) basieren, indem die älteste gespeicherte ID-Zuordnung entfernt und die neue hinzugefügt wird. Einzelheiten zu den von Audience Manager unterstützten IDs finden Sie im Audience Manager unter [IDs](../../reference/ids-in-aam.md) -Index.

| ID-Zuordnung | Maximale Beschränkung |
|-----------|-------------- |
| Device Advertising ID ([DAID](../../reference/ids-in-aam.md)) to Cross-Device ID ([DPUUID](../../reference/ids-in-aam.md)) | 100 Geräte-Anzeigen-IDs ([DAID](../../reference/ids-in-aam.md)) bis 1 geräteübergreifende ID ([DPUUID](../../reference/ids-in-aam.md)) |
| Geräteübergreifende ID ([DPUUID](../../reference/ids-in-aam.md)) für Geräte-Advertising-ID ([DAID](../../reference/ids-in-aam.md)) | 10 geräteübergreifende IDs ([DPUUID](../../reference/ids-in-aam.md)) bis 1 Geräte-Anzeigen-ID ([DAID](../../reference/ids-in-aam.md)) pro [DPID](../../reference/ids-in-aam.md) |
| Cookie/Browser-ID zu Cookie-/Browser-ID | 1000 Cookie-/Browser-IDs zu 1 Cookie-/Browser-ID |

## Elementgrenzen {#item-limits}

In den Tabellen werden die aktuellen Grenzwerte nach Elementtyp Liste. Sie können keine neuen Eigenschaften, Segmente, Ziele oder [!UICONTROL Algorithmic Models] Ziele erstellen, wenn Sie eine bestimmte Beschränkung für eines dieser Elemente erreichen. Wenn Sie einen Grenzwert erreichen, müssen Sie ein älteres Element löschen, bevor Sie ein neues erstellen können.

### Eigenschaftsbeschränkungen

| Eigenschaftstyp | Maximale Beschränkung |
| -------------------------- | ------------------------------------- |
| Eigenschaften insgesamt | 100,000 |
| Gesamtqualifikationen für Eigenschaften | 150,000. Weitere Informationen zur Qualifizierung von Eigenschaften finden Sie unter Qualifizierungsgrenze für Eigenschaften in der [Referenzhandbuch](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit)zu Eigenschaften. |
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
| Aktiv [!UICONTROL Look-Alike Models] | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| [!UICONTROL Look-Alike Models] maximale Audience | 25,000,000.  Beachten Sie, dass dieser Grenzwert nicht erhöht werden kann. Sie können die Größe der Audience verringern, indem Sie weniger Datenquellen für das Modell auswählen oder ein kürzeres Lookback-Fenster auswählen. |
| Maximale Anzahl der ausgeschlossenen Eigenschaften für eine [!UICONTROL Look-Alike Model] | 500. Siehe [Eigenschaftsausschluss in Algorithmischer Modellierung](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| Naximum [!UICONTROL Predictive Audiences Models] | 10 |
| Maximale Anzahl der Baseline-Personas für [!UICONTROL Predictive Audiences Models] | 50 |

### Ordnerbeschränkungen

| Element | Maximale Beschränkung |
| ------------- | ------------------ |
| Eigenschaftsordner | 2,000.  Ihre Ordnerstruktur kann maximal 5 Stufen tief sein. |

### Abgeleitete Signalgrenzen

| Element | Maximale Beschränkung |
| --------------- | ------------- |
| Abgeleitete Signale | 50.000. |

### Firma Benutzerkontenbeschränkung

| Element | Maximale Beschränkung |
| ----------- | ------------- |
| Maximale Anzahl Benutzerkonten für eine Firma | 1.000. |

## Nutzung überwachen {#monitor-usage}

Sie können die Nutzung und die Beschränkungen für Ihr Konto unter **[!UICONTROL Administration > Limits]**. Für den Zugriff sind Administratorberechtigungen erforderlich.

![Nutzungsbeschränkungen für Bild](assets/usage-limits.png)

## Elementgrenzen erhöhen {#increase-item-limits}

Die hier aufgelisteten Standardbeschränkungen sollten ausreichend Platz für Ihre geschäftlichen Anforderungen bieten. Wenn Ihr Unternehmen diese Grenzwerte konsequent erreicht, wenden Sie sich an Ihren Kundenbetreuer, um eine Erhöhung zu besprechen.