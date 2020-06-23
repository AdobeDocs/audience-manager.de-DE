---
description: Beschreibt die Komponenten eines Audience Manager-Segments, die Ausdruck, die zum Festlegen von Kriterien für die Audience-Qualifizierung verwendet werden, und wie Daten in einem Ereignis-Aufruf gesendet werden.
seo-description: Beschreibt die Komponenten eines Audience Manager-Segments, die Ausdruck, die zum Festlegen von Kriterien für die Audience-Qualifizierung verwendet werden, und wie Daten in einem Ereignis-Aufruf gesendet werden.
seo-title: Signale, Eigenschaften und Segmente
solution: Audience Manager
title: Signale, Eigenschaften und Segmente
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
translation-type: tm+mt
source-git-commit: 620730ab1596d4777a768de4453b73538671279d
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 0%

---


# [!UICONTROL Signals], [!UICONTROL Traits]und [!UICONTROL Segments] {#signals-traits-and-segments}

Beschreibt die Komponenten eines [!DNL Audience Manager] [!UICONTROL segment]Ereignisses, die Ausdruck zum Festlegen von Kriterien für die Audience-Qualifizierung und die Art und Weise, wie Daten in einem Aufruf gesendet werden.

## Zusammensetzung und Zweck

[!DNL Audience Manager] Daten bestehen aus [!UICONTROL signals], [!UICONTROL traits]und [!UICONTROL segments]zugehörigen Qualifikationsregeln. Die Datenelemente und -regeln werden zu [!UICONTROL segments]ihrer Erstellung kombiniert. [!UICONTROL Segments] Site-Besucher in verwandte Gruppen zu organisieren. In der folgenden Tabelle sind die drei Hauptkomponenten in einem [!DNL Audience Manager][!UICONTROL segment]definiert.

| Element | Besteht aus | Beispiel  |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sind die kleinsten Dateneinheiten in [!DNL Audience Manager] und werden als [Schlüssel-Wert-Paare](../reference/key-value-pairs-explained.md)ausgedrückt.<br><br><ul><li>Der Schlüssel ist eine Konstante, die einen Datensatz definiert (z.B. Geschlecht, Farbe, Preis).</li><li>Der Wert ist eine Variable, die sich auf die Konstante bezieht (z. B. männlich/weiblich, grün, 100).</li></ul>Vergleichsoperatoren verbinden das Schlüssel-Wert-Paar und legen die Beziehung zwischen ihnen fest. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Kombinationen aus einer oder mehreren Kombinationen [!UICONTROL signals].<br><br> [!DNL Boolean] Mit Ausdrücken und Vergleichsoperatoren können Sie [!UICONTROL trait] Qualifikationsregeln erstellen. <br><br>Präzise Qualifizierungsanforderungen mit Kombinationen aus [!UICONTROL traits] und [!UICONTROL trait] Gruppen. | In der verfügbaren Liste [!UICONTROL signals]können Sie eine `High End Camera Browser` Regel erstellen, die wie folgt aussieht: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Benutzer, die einen Satz gemeinsamer Attribute verwenden und sich für verwandte Attribute qualifizieren [!UICONTROL traits]. [!DNL Boolean] Mit Ausdrücken können Sie neben Neuigkeits-/Häufigkeitsanforderungen auch [!UICONTROL segment] Qualifizierungsregeln erstellen.<br><br> Erstellen Sie präzise Qualifizierungsanforderungen mit Kombinationen aus [!UICONTROL trait] und [!UICONTROL segment] Regeln. | In der verfügbaren [!UICONTROL traits] und [!UICONTROL signals]können Sie eine [!UICONTROL segment] Regel erstellen, die wie folgt ausdrückt:`(product=camera AND type=digital SLR) OR (price>1000)` |

Verwenden Sie das unten stehende Diagramm, um eine mentale Notiz der Beziehung zwischen [!UICONTROL signals], [!UICONTROL traits]und zu behalten [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Erstellen[!UICONTROL Traits]und[!UICONTROL Segment]Erstellen von Regeln mit Visual Tools und Codeeditoren**

Kunden verwalten [!UICONTROL traits] und [!UICONTROL segments] mit visuellen Werkzeugen und Codeeditoren in der [!DNL Audience Manager] Benutzeroberfläche. Mit den visuellen Werkzeugen können Sie Regeln mit Suchfunktionen, Popup-Optionen, Dropdownmenüs und Drag &amp; Drop-Funktionen erstellen. Die Codeeditoren bieten fortgeschrittenen Anwendern die Möglichkeit, Audiencen-Segmentierungskriterien programmatisch zu entwickeln.

**Ereignis-Aufrufe Daten senden an[!DNL Audience Manager]**

Ein Ereignis-Aufruf sendet Daten von Ihrer Website an [!DNL Audience Manager]. Der Aufruf enthält [!UICONTROL signal], [!UICONTROL trait]und [!UICONTROL segment] Daten in einer [!DNL HTTP] Anforderung. Das Ereignis selbst ist alles nach dem `/event` Teil einer [!DNL URL] Zeichenfolge. Wie im folgenden Beispiel gezeigt, erfordert dieser Vorgang nur einen einzigen Ereignis-Aufruf, um mehrere Variablen an [!DNL Audience Manager]zu übergeben.

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmente: Zweck, Zusammensetzung und Regeln](../features/segments/segments-purpose.md)

