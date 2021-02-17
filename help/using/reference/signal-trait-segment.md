---
description: Beschreibt die Komponenten eines Audience Manager-Segments, die Ausdrücke, die zur Festlegung von Kriterien für die Zielgruppenqualifizierung verwendet werden, und die Art und Weise, wie Daten bei einem Ereignisaufruf übertragen werden.
landing-page-description: Beschreibt Segmentkomponenten, Ausdrücke zum Festlegen von Qualifizierungskriterien für Zielgruppen und die Art und Weise, wie Daten übertragen werden.
seo-title: Signale, Eigenschaften und Segmente
solution: Audience Manager
title: Signale, Eigenschaften und Segmente
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: reference
translation-type: tm+mt
source-git-commit: e6348c85e7df6428802d54b2c90385ce95f50e1a
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 15%

---


# [!UICONTROL Signals],  [!UICONTROL Traits]und  [!UICONTROL Segments] {#signals-traits-and-segments}

Beschreibt die Komponenten von [!DNL Audience Manager] [!UICONTROL segment], die Ausdruck, die zum Festlegen von Kriterien für die Audience-Qualifizierung verwendet werden, und wie Daten in einem Ereignis-Aufruf gesendet werden.

## Zusammensetzung und Zweck

[!DNL Audience Manager] Daten bestehen aus  [!UICONTROL signals],  [!UICONTROL traits]und  [!UICONTROL segments]zugehörigen Qualifikationsregeln. Die Datenelemente und Regeln werden kombiniert, um [!UICONTROL segments] zu erstellen. [!UICONTROL Segments] Site-Besucher in verwandte Gruppen zu organisieren. Die folgende Tabelle definiert die drei Hauptkomponenten in einem [!DNL Audience Manager] [!UICONTROL segment].

| Element | Besteht aus | Beispiel |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sind die kleinsten Dateneinheiten in  [!DNL Audience Manager] und werden als  [Schlüssel-Wert-Paare](../reference/key-value-pairs-explained.md) ausgedrückt.<br><br><ul><li>Der Schlüssel ist eine Konstante, die einen Datensatz definiert (z.B. Geschlecht, Farbe, Preis).</li><li>Der Wert ist eine Variable, die sich auf die Konstante bezieht (z. B. männlich/weiblich, grün, 100).</li></ul>Vergleichsoperatoren verbinden das Schlüssel-Wert-Paar und legen die Beziehung zwischen ihnen fest. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Kombinationen aus einem oder mehreren [!UICONTROL signals].<br><br> [!DNL Boolean] Mit Ausdrücken und Vergleichsoperatoren können Sie  [!UICONTROL trait] Qualifikationsregeln erstellen. <br><br>Präzise Qualifizierungsanforderungen mit Kombinationen aus  [!UICONTROL traits] und  [!UICONTROL trait] Gruppen. | In der verfügbaren [!UICONTROL signals]-Regel können Sie eine `High End Camera Browser`-Regel erstellen, die wie folgt ausgedrückt wird: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Benutzer, die einen Satz gemeinsamer Attribute verwenden und sich für verwandte [!UICONTROL traits] qualifizieren. [!DNL Boolean] Mit Ausdrücken können Sie neben Neuigkeits-/Häufigkeitsanforderungen  [!UICONTROL segment] Qualifizierungsregeln erstellen.<br><br> Erstellen Sie präzise Qualifizierungsanforderungen mit Kombinationen aus  [!UICONTROL trait] und  [!UICONTROL segment] Regeln. | Aus den verfügbaren [!UICONTROL traits]- und [!UICONTROL signals]-Regeln können Sie eine [!UICONTROL segment]-Regel erstellen, die folgendermaßen ausgedrückt wird:`(product=camera AND type=digital SLR) OR (price>1000)` |

Verwenden Sie das unten stehende Diagramm, um eine mentale Notiz der Beziehung zwischen [!UICONTROL signals], [!UICONTROL traits] und [!UICONTROL segments] beizubehalten.

![](assets/signals-traits-segments.png)

**Erstellen  [!UICONTROL Traits] und  [!UICONTROL Segment] Regeln mit Visual Tools und Codeeditoren**

Clients verwalten [!UICONTROL traits] und [!UICONTROL segments] mit visuellen Werkzeugen und Codeeditoren in der [!DNL Audience Manager]-Benutzeroberfläche. Mit den visuellen Werkzeugen können Sie Regeln mit Suchfunktionen, Popup-Optionen, Dropdownmenüs und Drag &amp; Drop-Funktionen erstellen. Die Codeeditoren bieten fortgeschrittenen Anwendern die Möglichkeit, Audiencen-Segmentierungskriterien programmatisch zu entwickeln.

**Ereignis-Aufrufe Daten senden an[!DNL Audience Manager]**

Ein Ereignis-Aufruf sendet Daten von Ihrer Website an [!DNL Audience Manager]. Der Aufruf enthält die Daten [!UICONTROL signal], [!UICONTROL trait] und [!UICONTROL segment] in einer [!DNL HTTP]-Anforderung. Das Ereignis selbst ist alles nach dem `/event`-Teil einer [!DNL URL]-Zeichenfolge. Wie im Beispiel unten gezeigt, erfordert dieser Vorgang nur einen einzigen Ereignis-Aufruf, um mehrere Variablen an [!DNL Audience Manager] zu übergeben.

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmente: Zweck, Zusammensetzung und Regeln](../features/segments/segments-purpose.md)

