---
description: Die Signale sind die kleinste Informationseinheit innerhalb von Audience Manager. Sie stellen Benutzerinteraktionen oder Benutzeraktivitäten in Ihren Online-Eigenschaften dar und werden an Audience Manager übergeben, damit sie in Eigenschaftsregeln verwendet werden können.
seo-description: Signals are the smallest unit of information within Audience Manager. They represent user interactions or user activity on your online properties, and get passed on to Audience Manager to be used in trait rules.
seo-title: Understanding Signals
title: Grundlegendes zu Signalen
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
TQID: https://experienceleague.adobe.com/KA-oQWZi6lAXcKN5DY5-sYRYjSmR1AWkOVJkq4w8voo
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 364
ht-degree: 1%

---

# Grundlegendes zu Signalen

Die Signale sind die kleinste Informationseinheit innerhalb von Audience Manager. Sie stellen Benutzerinteraktionen oder Benutzeraktivitäten in Ihren Online-Eigenschaften dar und werden an Audience Manager übergeben, damit sie in Eigenschaftsregeln verwendet werden können.

[!DNL Audience Manager] werden Schlüssel-Wert-Paare zur Darstellung von Signalen verwendet. So könnte beispielsweise das folgende Signal darauf hindeuten, dass ein Besucher eine Webseite mit elektronischen Daten erreicht hat:

* `page = electronics`

Das [Signale-Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) zeigt verschiedene Arten von Signalattributen an, mit denen Sie neue Eigenschaften erstellen können. Im Folgenden finden Sie eine detaillierte Ansicht der verfügbaren Signaleigenschaften:

* *Schlüssel-Wert-*: zeigt das Schlüssel-Wert-Paar des von [!DNL Audience Manager] empfangenen Signals.
* *Signaltyp* beschreibt die Kategorie jedes Signals. Signale fallen in eine der folgenden Kategorien:
   * [Verwertbare Protokolldateien](/help/using/integration/media-data-integration/actionable-log-files.md): Echtzeitsignale, die von Ihren Protokolldateien für die Medienleistung empfangen werden;
   * [!DNL Adobe Analytics]: Echtzeit-Signale von Ihrem [!DNL Adobe Analytics]-Konto;
   * Allgemeine Online-Daten: von Ihrer Audience-Aktivität generierte Echtzeitdaten, die nicht in verwertbaren Protokolldateien und [!DNL Adobe Analytics] enthalten sind;
   * Onboarding-Datensätze: Daten, die durch Batch-Datenübertragungen empfangen werden.
* *Signal Source* hängt vom Signaltyp ab:
   * Bei eingebauten Signalen ist die Signalquelle der Name der Datenquelle.
   * Bei Signalen, die von [!DNL Adobe Analytics] stammen, ist die Datenquelle immer eine Report Suite.
   * Für verwertbare Protokolldateien und allgemeine Online-Daten werden keine Informationen zu Signalquellen angezeigt.
* *Gesamtanzahl* zeigt an, wie oft ein Echtzeitsignal in den letzten sieben Tagen von [!DNL Audience Manager] empfangen wurde.
* *In Eigenschaften enthalten* zeigt an, ob das Signal Teil einer Eigenschaft ist. Klicken Sie auf den Pfeil, um die Eigenschaften anzuzeigen, die das entsprechende Signal enthalten. Bei Signalen, die nicht Teil eines Merkmals sind, ändert sich der Spaltenwert in [!UICONTROL Create Onboarded Trait] oder [!UICONTROL Create Rule-Based Trait].

## Signaldatenauffrischfrequenz

Aufgrund der großen Datenmenge, die Audience Manager täglich verarbeitet, aktualisiert [!UICONTROL Data Explorer] die angezeigten Signaldaten je nach Signaltyp in festen Zeitintervallen:

* Die Echtzeit-Signaldaten (verwertbare Protokolldateien, [!DNL Adobe Analytics] und allgemeine Online-Daten) werden alle 4 bis 6 Stunden aktualisiert.
* Die Signaldaten des integrierten Geräts werden alle 24 Stunden aktualisiert.

## Verwandte Konzepte

[Signale, Eigenschaften und Segmente](/help/using/reference/signal-trait-segment.md)
