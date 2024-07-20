---
description: Audience Manager legt eine maximale Anzahl von Eigenschaften, Segmenten, Zielen und algorithmischen Modellen fest, die Sie für ein Konto erstellen können. Beschränkungen gelten für diese Elemente, unabhängig davon, ob sie in der Benutzeroberfläche oder programmgesteuert über API-Methoden erstellt wurden. Nutzungsbeschränkungen schützen den Audience Manager vor automatisierten Prozessen, die unsere APIs oder die Benutzeroberfläche beeinträchtigen könnten.
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
ht-degree: 3%

---

# Nutzungsbeschränkungen {#usage-limits}

Audience Manager legt eine maximale Anzahl von Eigenschaften, Segmenten, Zielen und algorithmischen Modellen fest, die Sie für ein Konto erstellen können. Beschränkungen gelten für diese Elemente, unabhängig davon, ob sie in der Benutzeroberfläche oder programmgesteuert über [!DNL API] -Methoden erstellt wurden. Nutzungsbeschränkungen schützen den Audience Manager vor automatisierten Prozessen, die unsere [!DNL API]s- oder -Benutzeroberfläche beeinträchtigen könnten.

## ID-Zuordnungsbeschränkungen {#id-mapping-limits}

In der folgenden Tabelle sind die Beschränkungen für die [ID-Zuordnung](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) für Geräte-IDs aufgeführt. Sobald eine ID eines der unten stehenden Limits erreicht, fügt Audience Manager neue ID-Zuordnungen basierend auf einer FIFO-Logik (first in, first out) hinzu, indem die älteste gespeicherte ID-Zuordnung entfernt und die neue hinzugefügt wird. Weitere Informationen zu den vom Audience Manager unterstützten IDs finden Sie im Audience Manager unter [Index of IDs](../../reference/ids-in-aam.md) .

| ID-Zuordnung | Maximale Beschränkung |
|-----------|-------------- |
| Device Advertising ID ([DAID](../../reference/ids-in-aam.md)) to Cross-Device ID ([DPUUID](../../reference/ids-in-aam.md)) | 100 Geräte-Advertising-IDs ([DAID](../../reference/ids-in-aam.md)) bis 1 geräteübergreifende ID ([DPUUID](../../reference/ids-in-aam.md)) |
| Geräteübergreifende ID ([DPUUID](../../reference/ids-in-aam.md)) für Geräte-Advertising-ID ([DAID](../../reference/ids-in-aam.md)) | 10 geräteübergreifende IDs ([DPUUID](../../reference/ids-in-aam.md)) bis 1 Geräte-Advertising-ID ([DAID](../../reference/ids-in-aam.md)) pro [DPID](../../reference/ids-in-aam.md) |
| Cookie/Browser-ID in Cookie/Browser-ID | 1000 Cookie-/Browser-IDs zu 1 Cookie/Browser-ID |

## Elementbeschränkungen {#item-limits}

In den Tabellen werden die aktuellen Beschränkungen nach Elementtyp aufgelistet. Sie können keine neuen Eigenschaften, Segmente, Ziele oder [!UICONTROL Algorithmic Models] erstellen, wenn Sie eine bestimmte Beschränkung für eines dieser Elemente erreichen. Wenn Sie ein Limit erreichen, müssen Sie ein älteres Element löschen, bevor Sie ein neues erstellen können.

### Eigenschaftsbeschränkungen

| Eigenschaftstyp | Maximale Beschränkung |
| -------------------------- | ------------------------------------- |
| Eigenschaften insgesamt | 100.000 |
| Eigenschaftsqualifikationen insgesamt | 150.000. Weitere Informationen zur Eigenschaftsqualifizierung finden Sie unter Eigenschaftsqualifikationslimit in der [Eigenschaftsqualifikationsreferenz](/help/using/features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit). |
| Algorithmus | 50 |
| Regelbasiert | 100.000 |
| integriert | 100.000 |
| Ordnereigenschaften | 2.000 |

### Segmentbeschränkungen

| Segmenttyp | Maximale Beschränkung |
| -------------- | ------------- |
| Segmente insgesamt | 20.000 |

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
| Aktiv [!UICONTROL Look-Alike Models] | 20. Audience Manager zählt nur algorithmische *aktive* -Modelle gegen die Beschränkung. |
| [!UICONTROL Look-Alike Models] maximale Zielgruppengröße | 25 000 000.  Beachten Sie, dass diese Grenze nicht erhöht werden kann. Sie können die Zielgruppengröße verringern, indem Sie weniger Datenquellen für das Modell auswählen oder ein kürzeres Lookback-Fenster auswählen. |
| Maximale Anzahl der ausgeschlossenen Eigenschaften für einen [!UICONTROL Look-Alike Model] | 500. Siehe [Eigenschaftenausschluss bei der algorithmischen Modellierung](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |
| Maximum [!UICONTROL Predictive Audiences Models] | 10 |
| Maximale Anzahl der Baseline-Rollen für [!UICONTROL Predictive Audiences Models] | 50 |

### Ordnerbeschränkungen

| Element | Maximale Beschränkung |
| ------------- | ------------------ |
| Eigenschaftsordner | 2.000.  Ihre Ordnerstruktur kann maximal 5 Ebenen tief sein. |

### Grenzwerte für abgeleitete Signale

| Element | Maximale Beschränkung |
| --------------- | ------------- |
| Abgeleitete Signale | 50.000. |

### Beschränkung für Unternehmensbenutzerkonten

| Element | Maximale Beschränkung |
| ----------- | ------------- |
| Maximale Anzahl von Benutzerkonten für ein Unternehmen | 1.000. |

## Nutzung überwachen {#monitor-usage}

Sie können die Nutzung und Einschränkungen Ihres Kontos anzeigen, indem Sie zu **[!UICONTROL Administration > Limits]** gehen. Für den Zugriff sind Administratorberechtigungen erforderlich.

![Nutzungsbeschränkungen für Bild](assets/usage-limits.png)

## Erhöhen der Elementgrenzen {#increase-item-limits}

Die hier aufgeführten Standardbeschränkungen sollten ausreichend Kapazität für Ihre Geschäftsanforderungen bieten. Wenn Ihr Unternehmen diese Grenzwerte konsequent erreicht, wenden Sie sich an Ihren Kundenbetreuer, um eine Erhöhung zu besprechen.
