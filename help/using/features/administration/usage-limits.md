---
description: Audience Manager legt eine Höchstgrenze für die Anzahl der Eigenschaften, Segmente, Ziele und algorithmischen Modelle fest, die Sie für ein Konto erstellen können. Einschränkungen gelten für diese Elemente, unabhängig davon, ob sie in der Benutzeroberfläche oder programmgesteuert über API-Methoden erstellt werden. Nutzungsbeschränkungen helfen, den Audience Manager vor automatisierten Prozessen zu schützen, die versuchen, unsere APIs oder die Benutzeroberfläche zu beeinträchtigen.
seo-description: Audience Manager sets a maximum limit on the number of traits, segments, destinations, and algorithmic models that you can create for an account. Limits apply to these items whether created in the user interface or programmatically through API methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our APIs or user interface.
seo-title: Usage Limits
solution: Audience Manager
title: Nutzungsbeschränkungen
keywords: ID-Zuordnung, ID-Zuordnungen, Cookie-Zuordnungen
uuid: 50ca4647-0b5c-409c-89fa-4fa1799b3222
feature: Usage and Billing
exl-id: 8d29e231-d369-44ad-8e89-e6a4c83175f2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 4%

---

# Nutzungsbeschränkungen {#usage-limits}

Audience Manager legt eine Höchstgrenze für die Anzahl der Eigenschaften, Segmente, Ziele und algorithmischen Modelle fest, die Sie für ein Konto erstellen können. Einschränkungen gelten für diese Elemente, unabhängig davon, ob sie in der Benutzeroberfläche oder programmgesteuert über [!DNL API] Methoden erstellt werden. Nutzungsbeschränkungen helfen, den Audience Manager vor automatisierten Prozessen zu schützen, die unsere [!DNL API] oder die Benutzeroberfläche gefährden könnten.

## ID-Zuordnungsbeschränkungen {#id-mapping-limits}

In der folgenden Tabelle sind die Beschränkungen [ID-Zuordnung](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) für Geräte-IDs aufgeführt. Sobald eine ID einen der unten stehenden Grenzwerte erreicht, fügt Audience Manager neue ID-Zuordnungen hinzu, die auf einer FIFO-Logik (first in, first out) basieren, indem es die älteste gespeicherte ID-Zuordnung entfernt und die neue hinzufügt. Siehe [Index der IDs](../../reference/ids-in-aam.md) im Audience Manager für Details zu den IDs, die vom Audience Manager unterstützt werden.

| ID-Zuordnung | Höchstgrenze |
|-----------|-------------- |
| Geräte-Advertising-ID [DAID](../../reference/ids-in-aam.md) in geräteübergreifende ID ([DPUUID](../../reference/ids-in-aam.md)) | 100 Geräte-Advertising-IDs ([DAID](../../reference/ids-in-aam.md)) bis 1 geräteübergreifende ID ([DPUUID](../../reference/ids-in-aam.md)) |
| Geräteübergreifende ID ([DPUUID](../../reference/ids-in-aam.md)) zu Geräte-Advertising-ID ([DAID](../../reference/ids-in-aam.md)) | 10 geräteübergreifende IDs ([DPUUID](../../reference/ids-in-aam.md)) zu 1 Geräte-Advertising ID ([DAID](../../reference/ids-in-aam.md)) pro [DPID](../../reference/ids-in-aam.md) |
| Cookie/Browser-ID zu Cookie/Browser-ID | 1000 Cookie/Browser-IDs zu 1 Cookie/Browser-ID |

## Elementbegrenzungen {#item-limits}

In den Tabellen werden die aktuellen Beschränkungen nach Elementtyp aufgeführt. Sie können keine neuen Eigenschaften, Segmente, Ziele oder [!UICONTROL Algorithmic Models] erstellen, wenn Sie für eines dieser Elemente ein bestimmtes Limit erreichen. Wenn Sie ein Limit erreichen, müssen Sie ein älteres Element löschen, bevor Sie ein neues erstellen können.

### Eigenschaftenbeschränkungen

| Eigenschaftstyp | Höchstgrenze |
| -------------------------- | ------------------------------------- |
| Gesamteigenschaften | 100.000 |
| Gesamtzahl der Eigenschaftsqualifikationen | 150.000. Weitere Informationen zur Eigenschaftsqualifizierung finden Sie unter Eigenschaftsqualifikationslimit in [Eigenschaftsqualifikationsreferenz](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
| Algorithmisch | 50 |
| Regelbasiert | 100.000 |
| integriert | 100.000 |
| Ordnereigenschaften | 2.000 |

### Segmentbeschränkungen

| Segmenttyp | Höchstgrenze |
| -------------- | ------------- |
| Segmente insgesamt | 20.000 |

### Zielbeschränkungen

| Zieltyp | Höchstgrenze |
| ------------------ | ------------- |
| Ziele insgesamt | 1.000 |
| Cookie | 1.000 |
| URL | 1.000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Algorithmische Modellbeschränkungen

| Element | Höchstgrenze |
| -------- | ----- |
| Aktive [!UICONTROL Look-Alike Models] | 20. Audience Manager zählt nur *aktive* algorithmische Modelle im Vergleich zum Limit. |
| Maximale Zielgruppengröße [!UICONTROL Look-Alike Models] | 25 000 000.  Beachten Sie, dass dieser Grenzwert nicht erhöht werden kann. Sie können die Größe der Zielgruppe verringern, indem Sie weniger Datenquellen für das Modell auswählen oder ein kürzeres Lookback-Fenster auswählen. |
| Maximale Anzahl ausgeschlossener Eigenschaften für eine [!UICONTROL Look-Alike Model] | 500. Siehe [Eigenschaftenausschluss in der algorithmischen Modellierung](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| Maximale [!UICONTROL Predictive Audiences Models] | 10 |
| Maximale Anzahl von Baseline-Personas für [!UICONTROL Predictive Audiences Models] | 50 |

### Ordnerbeschränkungen

| Element | Höchstgrenze |
| ------------- | ------------------ |
| Eigenschaftsordner | 2.000.  Die Ordnerstruktur kann maximal 5 Ebenen tief sein. |

### Grenzwerte für abgeleitete Signale

| Element | Höchstgrenze |
| --------------- | ------------- |
| Abgeleitete Signale | 50.000. |

### Limit für Firmenbenutzerkonten

| Element | Höchstgrenze |
| ----------- | ------------- |
| Maximale Anzahl von Benutzerkonten für eine Firma | 1.000. |

## Überwachen der Nutzung {#monitor-usage}

Sie können die Nutzung und die Beschränkungen für Ihr Konto sehen, indem Sie zu **[!UICONTROL Administration > Limits]** gehen. Der Zugriff erfordert Administratorberechtigungen.

![Nutzungsbeschränkungen für Bilder](assets/usage-limits.png)

## Elementgrenzen erhöhen {#increase-item-limits}

Die hier aufgeführten Standardbeschränkungen sollten ausreichend Kapazität für Ihre Geschäftsanforderungen bereitstellen. Wenn Ihr Unternehmen diese Beschränkungen durchgängig erreicht, wenden Sie sich an Ihren Kundenbetreuer, um eine Erhöhung zu besprechen.
