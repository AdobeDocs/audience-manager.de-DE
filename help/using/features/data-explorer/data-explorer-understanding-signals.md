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

Das Dashboard [Signale](../../features/data-explorer/data-explorer-signals-dashboard.md) zeigt mehrere Arten von Signalattributen an, mit denen Sie neue Eigenschaften erstellen können. Im Folgenden finden Sie eine detaillierte Ansicht der verfügbaren Signaleigenschaften:

* *Key-Value-* Paare zeigen Ihnen das Schlüssel-Wert-Paar des von  [!DNL Audience Manager]Ihnen empfangenen Signals.
* *Das Signal* beschreibt die Kategorie jedes Signals. Die Signale fallen in eine der folgenden Kategorien:
   * [Umsetzbare Protokolldateien](/help/using/integration/media-data-integration/actionable-log-files.md): Echtzeitsignale, die von Ihren Protokolldateien zur Medienleistung empfangen werden;
   * [!DNL Adobe Analytics]: von Ihrem  [!DNL Adobe Analytics] Konto empfangene Echtzeitsignale;
   * Allgemeine Online-Daten: Echtzeitdaten, die von Ihrer Audience-Aktivität generiert wurden und nicht in den ausführbaren Protokolldateien und [!DNL Adobe Analytics] enthalten sind;
   * An Bord befindliche Datensätze: Daten, die durch Batch-Datenübertragung empfangen wurden.
* *Signalquellen* hängen vom Signaltyp ab:
   * Bei an Bord befindlichen Signalen ist die Signalquelle der Name der Datenquelle.
   * Bei Signalen, die von [!DNL Adobe Analytics] stammen, ist die Datenquelle immer eine Report Suite.
   * Für ausführbare Protokolldateien und allgemeine Online-Daten werden keine Informationen zur Signalquelle angezeigt.
* *Die Gesamtanzahl* zeigt Ihnen, wie oft ein Echtzeit-Signal  [!DNL Audience Manager] in den letzten 7 Tagen empfangen wurde.
* *Im Lieferumfang von* Traitszeigt Ihnen, ob das Signal Teil einer Eigenschaft ist. Klicken Sie auf den Pfeil, um die Eigenschaften anzuzeigen, die das entsprechende Signal enthalten. Bei Signalen, die nicht Teil einer Eigenschaft sind, ändert sich der Spaltenwert in [!UICONTROL Create Onboarded Trait] oder [!UICONTROL Create Rule-Based Trait].

## Aktualisierungsfrequenz der Signaldaten

Aufgrund der großen Datenmenge, die Audience Manager täglich verarbeitet, aktualisiert [!UICONTROL Data Explorer] die angezeigten Signaldaten je nach Signaltyp in festen Zeitintervallen:

* Echtzeit-Signaldaten (umsetzbare Protokolldateien, [!DNL Adobe Analytics]-Daten und allgemeine Online-Daten) werden alle 4 bis 6 Stunden aktualisiert.
* An Bord befindliche Signaldaten werden alle 24 Stunden aktualisiert.

## Verwandte Konzepte

[Signale, Eigenschaften und Segmente](/help/using/reference/signal-trait-segment.md)