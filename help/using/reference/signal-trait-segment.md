---
description: Erfahren Sie mehr über die Komponenten eines Segments und die Ausdrücke, die zum Festlegen von Kriterien für die Zielgruppenqualifizierung verwendet werden. Hier finden Sie auch Informationen zur Datenübertragung.
landing-page-description: Erfahren Sie mehr über die Komponenten eines Segments und die Ausdrücke, die zum Festlegen von Kriterien für die Zielgruppenqualifizierung verwendet werden. Hier finden Sie auch Informationen zur Datenübertragung.
short-description: Erfahren Sie mehr über die Komponenten eines Segments und die Ausdrücke, die zum Festlegen von Kriterien für die Zielgruppenqualifizierung verwendet werden. Hier finden Sie auch Informationen zur Datenübertragung.
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: Signale, Eigenschaften und Segmente
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 21%

---

# [!UICONTROL Signals], [!UICONTROL Traits]und [!UICONTROL Segments] {#signals-traits-and-segments}

Beschreibt die Komponenten eines [!DNL Audience Manager] [!UICONTROL segment], die Ausdrücke, die zum Festlegen von Kriterien für die Zielgruppenqualifizierung verwendet werden, und die Art und Weise, wie Daten in einem Ereignisaufruf übertragen werden.

## Zusammensetzung und Zweck

[!DNL Audience Manager] Daten bestehen aus [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments]und damit zusammenhängende Qualifikationsregeln. Datenelemente und Regeln werden zu einer [!UICONTROL segments]. [!UICONTROL Segments] Site-Besucher in verwandte Gruppen organisieren. Die folgende Tabelle definiert die drei Hauptkomponenten in einer [!DNL Audience Manager] [!UICONTROL segment].

| Element | Besteht aus | Beispiel |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sind die kleinsten Dateneinheiten in [!DNL Audience Manager] und ausgedrückt als [Schlüssel-Wert-Paare](../reference/key-value-pairs-explained.md).<br><br><ul><li>Der Schlüssel ist eine Konstante, die einen Datensatz definiert (z. B. Geschlecht, Farbe, Preis).</li><li>Der Wert ist eine Variable, die mit der Konstante verknüpft ist (z. B. männlich/weiblich, grün, 100).</li></ul>Vergleichsoperatoren verbinden sich mit dem Schlüssel-Wert-Paar und legen die Beziehung zwischen ihnen fest. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Kombinationen aus einer oder mehreren [!UICONTROL signals].<br><br> [!DNL Boolean] Mit Ausdrücken und Vergleichsoperatoren können Sie [!UICONTROL trait] Qualifikationsregeln. <br><br>Präzise Qualifizierungsanforderungen mit Kombinationen aus [!UICONTROL traits] und [!UICONTROL trait] Gruppen. | In der [!UICONTROL signals], können Sie eine `High End Camera Browser` Regel, ausgedrückt als: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Benutzer, die einen Satz gemeinsamer Attribute teilen und sich für verwandte Attribute qualifizieren [!UICONTROL traits]. [!DNL Boolean] Ausdrücke sowie Neuigkeits-/Häufigkeitsanforderungen können Sie [!UICONTROL segment] Qualifikationsregeln.<br><br> Präzise Qualifizierungsanforderungen mit Kombinationen aus [!UICONTROL trait] und [!UICONTROL segment] Regeln. | In der [!UICONTROL traits] und [!UICONTROL signals], können Sie eine [!UICONTROL segment] Regel, ausgedrückt als:`(product=camera AND type=digital SLR) OR (price>1000)` |

Verwenden Sie das folgende Diagramm, um eine mentale Anmerkung zur Beziehung zwischen [!UICONTROL signals], [!UICONTROL traits]und [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Build [!UICONTROL Traits] und [!UICONTROL Segment] Regeln mit Visual Tools und Code-Editoren**

Kundenverwaltung [!UICONTROL traits] und [!UICONTROL segments] mit visuellen Tools und Code-Editoren im [!DNL Audience Manager] -Benutzeroberfläche. Mit den visuellen Tools können Sie Regeln mithilfe von Suchfunktionen, Popup-Optionen, Dropdownmenüs und Drag &amp; Drop-Funktionen erstellen. Die Code-Editoren bieten erweiterten Benutzern die Möglichkeit, Zielgruppensegmentierungskriterien programmatisch zu entwickeln.

**Ereignisaufrufe Senden von Daten an[!DNL Audience Manager]**

Ein Ereignisaufruf sendet Daten von Ihrer Website an [!DNL Audience Manager]. Der Aufruf enthält [!UICONTROL signal], [!UICONTROL trait]und [!UICONTROL segment] Daten in einer [!DNL HTTP] -Anfrage. Das Ereignis selbst ist alles nach der `/event` Teil eines [!DNL URL] Zeichenfolge. Wie im folgenden Beispiel gezeigt, erfordert dieser Prozess nur einen einzelnen Ereignisaufruf, um mehrere Variablen an [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmente: Zweck, Zusammensetzung und Regeln](../features/segments/segments-purpose.md)

