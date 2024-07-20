---
description: Signale sind die kleinste Informationseinheit innerhalb des Audience Managers. Sie stellen Benutzerinteraktionen oder Benutzeraktivitäten in Ihren Online-Eigenschaften dar und werden an Audience Manager weitergegeben, um in Eigenschaftsregeln verwendet zu werden.
seo-description: Signals are the smallest unit of information within Audience Manager. They represent user interactions or user activity on your online properties, and get passed on to Audience Manager to be used in trait rules.
seo-title: Understanding Signals
title: Grundlagen zu Signalen
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# Grundlagen zu Signalen

Signale sind die kleinste Informationseinheit innerhalb des Audience Managers. Sie stellen Benutzerinteraktionen oder Benutzeraktivitäten in Ihren Online-Eigenschaften dar und werden an Audience Manager weitergegeben, um in Eigenschaftsregeln verwendet zu werden.

[!DNL Audience Manager] verwendet Schlüssel-Wert-Paare zur Darstellung von Signalen. Beispielsweise könnte das folgende Signal darauf hinweisen, dass ein Besucher eine Webseite mit Elektronik erreicht hat:

* `page = electronics`

Das [Signale-Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) zeigt mehrere Arten von Signalattributen an, die Sie zum Erstellen neuer Eigenschaften verwenden können. Im Folgenden finden Sie eine detaillierte Ansicht der verfügbaren Signaleigenschaften:

* *Schlüssel-Wert-Paar* zeigt das Schlüssel-Wert-Paar des von [!DNL Audience Manager] empfangenen Signals an.
* *Signaltyp* beschreibt die Kategorie jedes Signals. Signale fallen in eine der folgenden Kategorien:
   * [Ausführbare Protokolldateien](/help/using/integration/media-data-integration/actionable-log-files.md): Echtzeitsignale, die von Ihren Protokolldateien zur Medienleistung empfangen werden;
   * [!DNL Adobe Analytics]: Echtzeit-Signale, die von Ihrem [!DNL Adobe Analytics]-Konto empfangen werden;
   * Allgemeine Online-Daten: von Ihrer Zielgruppenaktivität generierte Echtzeitdaten, die nicht in ausführbaren Protokolldateien und [!DNL Adobe Analytics] enthalten sind;
   * Integrierte Datensätze: Daten, die durch Batch-Datenübertragungen empfangen werden.
* *Signal Source* hängt vom Signaltyp ab:
   * Bei integrierten Signalen ist die Signalquelle der Name der Datenquelle.
   * Bei Signalen, die von [!DNL Adobe Analytics] stammen, ist die Datenquelle immer eine Report Suite.
   * Für ausführbare Protokolldateien und allgemeine Online-Daten werden keine Informationen zur Signalquelle angezeigt.
* *Zählung insgesamt* gibt an, wie oft ein Echtzeit-Signal insgesamt von [!DNL Audience Manager] in den letzten sieben Tagen empfangen wurde.
* *In Eigenschaften eingeschlossen* zeigt Ihnen, ob das Signal Teil einer Eigenschaft ist. Klicken Sie auf den Pfeil, um die Eigenschaften anzuzeigen, die das entsprechende Signal enthalten. Bei Signalen, die nicht Teil einer Eigenschaft sind, ändert sich der Spaltenwert in [!UICONTROL Create Onboarded Trait] oder [!UICONTROL Create Rule-Based Trait].

## Aktualisierungshäufigkeit der Signaldaten

Aufgrund der großen Datenmenge, die Audience Manager täglich verarbeitet, aktualisiert [!UICONTROL Data Explorer] die angezeigten Signaldaten in festen Zeitintervallen, je nach Signaltyp:

* Echtzeit-Signaldaten (ausführbare Protokolldateien, [!DNL Adobe Analytics] -Daten und allgemeine Online-Daten) werden alle 4 bis 6 Stunden aktualisiert.
* Die integrierten Signaldaten werden alle 24 Stunden aktualisiert.

## Verwandte Konzepte

[Signale, Eigenschaften und Segmente](/help/using/reference/signal-trait-segment.md)
