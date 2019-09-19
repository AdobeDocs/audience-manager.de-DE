---
description: Signale sind die kleinste Informationseinheit in Audience Manager. Sie stellen Benutzerinteraktionen oder Benutzeraktivitäten in Ihren Online-Eigenschaften dar und werden an Audience Manager weitergeleitet, um in Eigenschaftsregeln verwendet zu werden.
seo-description: Signale sind die kleinste Informationseinheit in Audience Manager. Sie stellen Benutzerinteraktionen oder Benutzeraktivitäten in Ihren Online-Eigenschaften dar und werden an Audience Manager weitergeleitet, um in Eigenschaftsregeln verwendet zu werden.
seo-title: Signale verstehen
title: Signale verstehen
uuid: 04a0554e-954e-484a-8838-9161ef416872
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Signale verstehen

Signale sind die kleinste Informationseinheit in Audience Manager. Sie stellen Benutzerinteraktionen oder Benutzeraktivitäten in Ihren Online-Eigenschaften dar und werden an Audience Manager weitergeleitet, um in Eigenschaftsregeln verwendet zu werden.

[!DNL Audience Manager] verwendet Schlüssel-Wert-Paare zur Darstellung von Signalen. Beispielsweise könnte das folgende Signal darauf hindeuten, dass ein Besucher eine Webseite mit Elektronik erreicht hat:

* `page = electronics`

Das [Signal-Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) zeigt mehrere Arten von Signalattributen an, mit denen Sie neue Eigenschaften erstellen können. Im Folgenden finden Sie eine detaillierte Übersicht der verfügbaren Signaleigenschaften:

* *Das Schlüssel-Wert-Paar* zeigt Ihnen das Schlüssel-Wert-Paar des von [!DNL Audience Manager]Ihnen empfangenen Signals.
* *Der Signaltyp* beschreibt die Kategorie jedes Signals. Signale fallen in eine der folgenden Kategorien:
   * [Umsetzbare Protokolldateien](/help/using/integration/media-data-integration/actionable-log-files.md): Echtzeitsignale, die von Ihren Protokolldateien zur Medienleistung empfangen werden;
   * [!DNL Adobe Analytics]: von Ihrem [!DNL Adobe Analytics] Konto empfangene Echtzeitsignale;
   * Allgemeine Online-Daten: Echtzeitdaten, die durch Ihre Zielgruppenaktivität generiert wurden und nicht in den ausführbaren Protokolldateien enthalten sind, [!DNL Adobe Analytics];
   * An Bord befindliche Datensätze: Daten, die durch Batch-Datenübertragung empfangen wurden.
* *Signalquelle* hängt vom Signaltyp ab:
   * Bei an Bord befindlichen Signalen ist die Signalquelle der Name der Datenquelle.
   * Bei Signalen, die von [!DNL Adobe Analytics]der Datenquelle stammen, ist die Datenquelle immer eine Report Suite.
   * Für ausführbare Protokolldateien und allgemeine Online-Daten werden keine Informationen zur Signalquelle angezeigt.
* *Die Gesamtanzahl* zeigt an, wie oft ein Echtzeit-Signal in den letzten 7 Tagen empfangen wurde [!DNL Audience Manager] .
* *In Eigenschaften* eingeschlossen zeigt an, ob das Signal Teil einer Eigenschaft ist. Klicken Sie auf den Pfeil, um die Eigenschaften anzuzeigen, die das entsprechende Signal enthalten. Bei Signalen, die nicht Teil einer Eigenschaft sind, ändert sich der Spaltenwert in [!UICONTROL Create Onboarded Trait] oder [!UICONTROL Create Rule-Based Trait].

## Aktualisierungsfrequenz der Signaldaten

Aufgrund der großen Datenmenge, die Audience Manager täglich verarbeitet, [!UICONTROL Data Explorer] werden die angezeigten Signaldaten je nach Signaltyp in festen Zeitintervallen aktualisiert:

* Echtzeit-Signaldaten (relevante Protokolldateien, [!DNL Adobe Analytics] Daten und allgemeine Online-Daten) werden alle 4 bis 6 Stunden aktualisiert.
* An Bord befindliche Signaldaten werden alle 24 Stunden aktualisiert.

## Verwandte Konzepte

[Signale, Eigenschaften und Segmente](/help/using/reference/signal-trait-segment.md)