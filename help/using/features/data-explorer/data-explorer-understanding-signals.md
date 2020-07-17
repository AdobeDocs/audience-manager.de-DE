---
description: Signale sind die kleinste Informationseinheit innerhalb des Audience Managers. Sie stellen Benutzerinteraktionen oder die Aktivität von Benutzern in Ihren Online-Eigenschaften dar und werden an Audience Manager weitergegeben, um in Eigenschaftsregeln verwendet zu werden.
seo-description: Signale sind die kleinste Informationseinheit innerhalb des Audience Managers. Sie stellen Benutzerinteraktionen oder die Aktivität von Benutzern in Ihren Online-Eigenschaften dar und werden an Audience Manager weitergegeben, um in Eigenschaftsregeln verwendet zu werden.
seo-title: Grundlegendes zu Signalen
title: Grundlegendes zu Signalen
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 2%

---


# Grundlegendes zu Signalen

Signale sind die kleinste Informationseinheit innerhalb des Audience Managers. Sie stellen Benutzerinteraktionen oder die Aktivität von Benutzern in Ihren Online-Eigenschaften dar und werden an Audience Manager weitergegeben, um in Eigenschaftsregeln verwendet zu werden.

[!DNL Audience Manager] verwendet Schlüssel-Wert-Paare zur Darstellung von Signalen. Beispielsweise könnte das folgende Signal darauf hindeuten, dass ein Besucher eine Webseite mit Elektronik erreicht hat:

* `page = electronics`

Das [Signal-Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) zeigt mehrere Arten von Signalattributen an, mit denen Sie neue Eigenschaften erstellen können. Im Folgenden finden Sie eine detaillierte Ansicht der verfügbaren Signaleigenschaften:

* *Das Schlüssel-Wert-Paar* zeigt Ihnen das Schlüssel-Wert-Paar des von [!DNL Audience Manager]Ihnen empfangenen Signals.
* *Der Signaltyp* beschreibt die Kategorie der einzelnen Signale. Die Signale fallen in eine der folgenden Kategorien:
   * [Umsetzbare Protokolldateien](/help/using/integration/media-data-integration/actionable-log-files.md): Echtzeitsignale, die von Ihren Protokolldateien zur Medienleistung empfangen werden;
   * [!DNL Adobe Analytics]: von Ihrem [!DNL Adobe Analytics] Konto empfangene Echtzeitsignale;
   * Allgemeine Online-Daten: Echtzeit-Daten, die von Ihrer Audience-Aktivität generiert wurden und nicht in den ausführbaren Protokolldateien enthalten sind, und [!DNL Adobe Analytics];
   * An Bord befindliche Datensätze: Daten, die durch Batch-Datenübertragung empfangen wurden.
* *Signalquelle* hängt vom Signaltyp ab:
   * Bei an Bord befindlichen Signalen ist die Signalquelle der Name der Datenquelle.
   * Bei Signalen, die von [!DNL Adobe Analytics]der Datenquelle stammen, ist die Datenquelle immer eine Report Suite.
   * Für ausführbare Protokolldateien und allgemeine Online-Daten werden keine Informationen zur Signalquelle angezeigt.
* *Die Gesamtanzahl* zeigt an, wie oft ein Echtzeit-Signal in den letzten 7 Tagen empfangen wurde [!DNL Audience Manager] .
* *In Eigenschaften* eingeschlossen zeigt an, ob das Signal Teil einer Eigenschaft ist. Klicken Sie auf den Pfeil, um die Eigenschaften anzuzeigen, die das entsprechende Signal enthalten. Bei Signalen, die nicht Teil einer Eigenschaft sind, ändert sich der Spaltenwert in [!UICONTROL Create Onboarded Trait] oder [!UICONTROL Create Rule-Based Trait].

## Aktualisierungsfrequenz der Signaldaten

Aufgrund der großen Datenmenge, die Audience Manager täglich verarbeitet, [!UICONTROL Data Explorer] werden die angezeigten Signaldaten je nach Signaltyp in festen Zeitabständen aktualisiert:

* Echtzeit-Signaldaten (relevante Protokolldateien, [!DNL Adobe Analytics] Daten und allgemeine Online-Daten) werden alle 4 bis 6 Stunden aktualisiert.
* An Bord befindliche Signaldaten werden alle 24 Stunden aktualisiert.

## Verwandte Konzepte

[Signale, Eigenschaften und Segmente](/help/using/reference/signal-trait-segment.md)