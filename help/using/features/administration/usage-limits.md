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


# Nutzungsbeschränkungen {#usage-limits}

Audience Manager legt eine maximale Anzahl an Eigenschaften, Segmenten, Zielen und algorithmischen Modellen fest, die Sie für ein Konto erstellen können. Beschränkungen gelten für diese Elemente, unabhängig davon, ob sie in der Benutzeroberfläche oder programmatisch über [!DNL API] Methoden erstellt wurden. Nutzungsbeschränkungen helfen Ihnen beim Schutz von Audience Manager vor automatisierten Prozessen, die versuchen könnten, unsere [!DNL API]Benutzeroberfläche oder Benutzeroberfläche zu gefährden.

## ID-Zuordnungs-Begrenzung {#id-mapping-limits}

In der folgenden Tabelle sind [die ID-Zuordnungsgrenzwerte](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md) für Geräte-IDs aufgeführt. Sobald eine ID die unten aufgeführten Grenzwerte erreicht, fügt Audience Manager neue ID-Zuordnungen basierend auf einer [!DNL FIFO] (ersten, ersten) Logik hinzu, indem die älteste gespeicherte ID-Zuordnung entfernt wird und das neue hinzugefügt wird. Einzelheiten zu den von Audience Manager unterstützten IDs finden Sie unter [Index von IDs](../../reference/ids-in-aam.md) in Audience Manager.

| ID-Zuordnung | Maximaler Grenzwert |
|-----------|-------------- |
| Geräte-Anzeigen-ID (DAID) zur geräteübergreifenden ID (CRM-ID) | 100 Geräte-Ids (daids) zu 1 geräteübergreifenden ID (CRM-ID) |
| Geräteübergreifende ID (CRM-ID) zur Gerätewerbung-ID (DAID) | 10 geräteübergreifende IDs (CRM-IDs) bis zu 1 Device Advertising ID (DAID) |
| Cookie-/Browser-ID zur Cookie-/Browser-ID | 1000 Cookie-/Browser-IDs zu 1 Cookie/Browser-ID |

## Elementbeschränkungen {#item-limits}

In den Tabellen werden die aktuellen Beschränkungen nach Elementtyp aufgeführt. Sie können keine neuen Eigenschaften, Segmente, Ziele oder [!UICONTROL Algorithmic Models] eine spezifische Beschränkung für eines dieser Elemente erstellen. Wenn Sie eine Begrenzung erreichen, müssen Sie ein älteres Element löschen, bevor Sie eine neue erstellen können.

### Trait-Beschränkungen

| Eigenschaftstyp | Maximaler Grenzwert |
| -------------------------- | ------------------------------------- |
| Gesamteigenschaften | 100,000 |
| Gesamteigenschaften von Eigenschaften | 150,000. Weitere Informationen zu Trait-Qualifizierung finden Sie unter Trait Skills Limit in [Trait Qualifications Reference](/help/using/features/traits/trait-qualification-reference.md#trait-qualification-limit). |
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
| Aktive algorithmische Modelle | 20. Audience Manager zählt nur *aktive* algorithmische Modelle für den Grenzwert. |
| Maximale Zielgruppengröße für Algorithmische Modelle | 25,000,000.  Beachten Sie, dass diese Beschränkung nicht erhöht werden kann. Sie können die Zielgruppengröße verringern, indem Sie für das Modell weniger Datenquellen auswählen oder ein kürzeres Look-Back-Fenster auswählen. |
| Maximale Anzahl von ausgeschlossenen Eigenschaften für ein Modell | 500. Siehe [Eigenschaften-Ausschluss im algorithmischen Modellieren](/help/using/features/algorithmic-models/trait-exclusion-algo-models.md). |

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

## Überwachung überwachen {#monitor-usage}

Sie können die Nutzung und Beschränkungen für Ihr Konto **[!UICONTROL Administration > Limits]** anzeigen. Zugriff erfordert Administratorberechtigungen.

![Verwendungsgrenzen für Bilder](assets/usage-limits.png)

## Elementgrenzen erhöhen {#increase-item-limits}

Die hier aufgeführten Standardbeschränkungen sollten Ihren geschäftlichen Anforderungen entsprechend ausreichen. Wenn Ihr Unternehmen diese Beschränkungen konsistent erreicht, wenden Sie sich an Ihren Kundenbetreuer, um eine Steigerung zu besprechen.