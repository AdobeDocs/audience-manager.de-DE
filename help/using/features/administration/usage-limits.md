---
description: Audience Manager legt eine maximale Anzahl an Eigenschaften, Segmenten, Zielen und algorithmischen Modellen fest, die Sie für ein Konto erstellen können. Beschränkungen gelten für diese Elemente, unabhängig davon, ob sie in der Benutzeroberfläche oder programmatisch über API-Methoden erstellt wurden. Nutzungsbeschränkungen unterstützen den Audience Manager vor automatisierten Prozessen, die versuchen könnten, unsere apis oder Benutzeroberfläche zu gefährden.
seo-description: Audience Manager legt eine maximale Anzahl an Eigenschaften, Segmenten, Zielen und algorithmischen Modellen fest, die Sie für ein Konto erstellen können. Beschränkungen gelten für diese Elemente, unabhängig davon, ob sie in der Benutzeroberfläche oder programmatisch über API-Methoden erstellt wurden. Nutzungsbeschränkungen unterstützen den Audience Manager vor automatisierten Prozessen, die versuchen könnten, unsere apis oder Benutzeroberfläche zu gefährden.
seo-title: Nutzungsbeschränkungen
solution: Audience Manager
title: Nutzungsbeschränkungen
topic: DIL-API
uuid: 50 ca 4647-0 b 5 c -409 c -89 fa -4 fa 1799 b 3222
translation-type: tm+mt
source-git-commit: a9550d71bbc6adf939539df05cd38a9d22ef261b

---


# Usage Limits {#usage-limits}

Audience Manager legt eine maximale Anzahl an Eigenschaften, Segmenten, Zielen und algorithmischen Modellen fest, die Sie für ein Konto erstellen können. Limits apply to these items whether created in the user interface or programmatically through [!DNL API] methods. Usage limits help protect Audience Manager from automated processes that may attempt to compromise our [!DNL API]s or user interface.

## ID-Zuordnungs-Begrenzung {#id-mapping-limits}

The table below lists the [ID mapping](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) limits for device IDs. Once an ID reaches any of the limits below, Audience Manager adds new ID mappings based on a [!DNL FIFO] (first in, first out) logic, by removing the oldest stored ID mapping, and adds the new one. Refer to [Index of IDs](../../reference/ids-in-aam.md) in Audience Manager for details on the IDs supported by Audience Manager.

| ID-Zuordnung | Maximaler Grenzwert |
|-----------|-------------- |
| Geräte-Anzeigen-ID (DAID) zur geräteübergreifenden ID (CRM-ID) | 100 Geräte-Ids (daids) zu 1 geräteübergreifenden ID (CRM-ID) |
| Geräteübergreifende ID (CRM-ID) zur Gerätewerbung-ID (DAID) | 10 geräteübergreifende IDs (CRM-IDs) bis zu 1 Device Advertising ID (DAID) |
| Cookie-/Browser-ID zur Cookie-/Browser-ID | 1000 Cookie-/Browser-IDs zu 1 Cookie/Browser-ID |

## Item Limits {#item-limits}

In den Tabellen werden die aktuellen Beschränkungen nach Elementtyp aufgeführt. You cannot create new traits, segments, destinations, or [!UICONTROL Algorithmic Models] if you reach a specific limit for one of these items. Wenn Sie eine Begrenzung erreichen, müssen Sie ein älteres Element löschen, bevor Sie eine neue erstellen können.

### Trait-Beschränkungen

| Eigenschaftstyp | Maximaler Grenzwert |
| -------------------------- | ------------------------------------- |
| Gesamteigenschaften | 100,000 |
| Gesamteigenschaften von Eigenschaften | 150,000. For more information on trait qualification, see Trait Qualification Limit in [Trait Qualifications Reference](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit). |
| Algorithmus | 50 |
| Regelbasiert | 100,000 |
| Onboarded | 100,000 |
| Ordnereigenschaften | 2,000 |

### Segmentbeschränkungen

| Segmenttyp | Maximaler Grenzwert |
| -------------- | ------------- |
| Segmente insgesamt | 20,000 |

### Zielgrenzen

| Zieltyp | Maximaler Grenzwert |
| ------------------ | ------------- |
| Ziele insgesamt | 1.000 |
| Cookie | 1.000 |
| URL | 1.000 |
| S2S | 100 |
| Adobe Analytics | 10 |

### Algorithmische Modellbeschränkungen

| Element | Maximaler Grenzwert |
| -------- | ----- |
| Aktive algorithmische Modelle | 20. Audience Manager only counts *active* algorithmic models against the limit. |
| Maximale Zielgruppengröße für Algorithmische Modelle | 25,000,000.  Beachten Sie, dass diese Beschränkung nicht erhöht werden kann. Sie können die Zielgruppengröße verringern, indem Sie für das Modell weniger Datenquellen auswählen oder ein kürzeres Look-Back-Fenster auswählen. |
| Maximale Anzahl von ausgeschlossenen Eigenschaften für ein Modell | 500. See [Trait Exclusion in Algorithmic Modeling](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |

### Ordnerbeschränkungen

| Element | Maximaler Grenzwert |
| ------------- | ------------------ |
| Eigenschaftenordner | 2,000.  Ihre Ordnerstruktur kann maximal 5 Ebenen tief sein. |

### Beschränkungen für abgeleitete Signale

| Element | Maximaler Grenzwert |
| --------------- | ------------- |
| Abgeleitete Signale | 50.000. |

### Beschränkung der Unternehmensbenutzerkonten

| Element | Maximaler Grenzwert |
| ----------- | ------------- |
| Maximale Anzahl Benutzerkonten für ein Unternehmen | 1.000. |

## Monitor Usage {#monitor-usage}

You can see usage and limits for your account by going to **[!UICONTROL Administration > Limits]**. Zugriff erfordert Administratorberechtigungen.

![Verwendungsgrenzen für Bilder](assets/usage-limits.png)

## Increase Item Limits {#increase-item-limits}

Die hier aufgeführten Standardbeschränkungen sollten Ihren geschäftlichen Anforderungen entsprechend ausreichen. Wenn Ihr Unternehmen diese Beschränkungen konsistent erreicht, wenden Sie sich an Ihren Kundenbetreuer, um eine Steigerung zu besprechen.