---
description: Beschreibt die Komponenten eines Audience Manager-Segments, die Ausdrücke, die zur Festlegung von Kriterien für die Zielgruppenqualifizierung verwendet werden, und die Art und Weise, wie Daten bei einem Ereignisaufruf übertragen werden.
landing-page-description: Beschreibt Segmentkomponenten, Ausdrücke zum Festlegen von Qualifizierungskriterien für Zielgruppen und die Art und Weise, wie Daten übertragen werden.
seo-title: Signale, Eigenschaften und Segmente
solution: Audience Manager
title: Signale, Eigenschaften und Segmente
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: 'Referenz '
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 15%

---

# [!UICONTROL Signals],  [!UICONTROL Traits] und  [!UICONTROL Segments] {#signals-traits-and-segments}

Beschreibt die Komponenten eines [!DNL Audience Manager] [!UICONTROL segment], die Ausdrücke, die zum Festlegen von Kriterien für die Zielgruppenqualifizierung verwendet werden, und die Art und Weise, wie Daten bei einem Ereignisaufruf übertragen werden.

## Zusammensetzung und Zweck

[!DNL Audience Manager] -Daten bestehen aus  [!UICONTROL signals],  [!UICONTROL traits],  [!UICONTROL segments]und zugehörigen Qualifikationsregeln. Die Datenelemente und Regeln werden zu [!UICONTROL segments] kombiniert. [!UICONTROL Segments] Site-Besucher in verwandte Gruppen organisieren. Die folgende Tabelle definiert die drei Hauptkomponenten in einem [!DNL Audience Manager] [!UICONTROL segment].

| Element | Besteht aus | Beispiel |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] sind die kleinsten Dateneinheiten in  [!DNL Audience Manager] und werden als  [Schlüssel-Wert-Paare](../reference/key-value-pairs-explained.md) ausgedrückt.<br><br><ul><li>Der Schlüssel ist eine Konstante, die einen Datensatz definiert (z. B. Geschlecht, Farbe, Preis).</li><li>Der Wert ist eine Variable, die mit der Konstante verknüpft ist (z. B. männlich/weiblich, grün, 100).</li></ul>Vergleichsoperatoren verbinden sich mit dem Schlüssel-Wert-Paar und legen die Beziehung zwischen ihnen fest. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Kombinationen von [!UICONTROL signals].<br><br> [!DNL Boolean] Mit Ausdrücken und Vergleichsoperatoren können Sie  [!UICONTROL trait] Qualifizierungsregeln erstellen. <br><br>Erstellen Sie präzise Qualifizierungsanforderungen mit Kombinationen aus  [!UICONTROL traits] und  [!UICONTROL trait] Gruppen. | Aus dem verfügbaren [!UICONTROL signals] können Sie eine `High End Camera Browser`-Regel erstellen, die wie folgt ausgedrückt wird: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Benutzer, die einen Satz gemeinsamer Attribute teilen und sich für verwandte [!UICONTROL traits] qualifizieren. [!DNL Boolean] Ausdrücke sowie Neuigkeits-/Frequenzanforderungen ermöglichen Ihnen das Erstellen von  [!UICONTROL segment] Qualifizierungsregeln.<br><br> Erstellen Sie genaue Qualifizierungsanforderungen mit Kombinationen aus  [!UICONTROL trait] und  [!UICONTROL segment] Regeln. | Aus den verfügbaren [!UICONTROL traits] und [!UICONTROL signals] können Sie eine [!UICONTROL segment]-Regel erstellen, die wie folgt ausgedrückt wird:`(product=camera AND type=digital SLR) OR (price>1000)` |

Verwenden Sie das folgende Diagramm, um eine mentale Anmerkung der Beziehung zwischen [!UICONTROL signals], [!UICONTROL traits] und [!UICONTROL segments] zu erhalten.

![](assets/signals-traits-segments.png)

**Erstellen  [!UICONTROL Traits] und  [!UICONTROL Segment] Regeln mit Visual Tools und Code-Editoren**

Clients verwalten [!UICONTROL traits] und [!UICONTROL segments] mit visuellen Tools und Code-Editoren in der [!DNL Audience Manager]-Benutzeroberfläche. Mit den visuellen Tools können Sie Regeln mithilfe von Suchfunktionen, Popup-Optionen, Dropdownmenüs und Drag &amp; Drop-Funktionen erstellen. Die Code-Editoren bieten fortgeschrittenen Benutzern die Möglichkeit, Zielgruppensegmentierungskriterien programmatisch zu entwickeln.

**Ereignisaufrufe Senden von Daten an[!DNL Audience Manager]**

Ein Ereignisaufruf sendet Daten von Ihrer Website an [!DNL Audience Manager]. Der Aufruf enthält die Daten [!UICONTROL signal], [!UICONTROL trait] und [!UICONTROL segment] in einer [!DNL HTTP]-Anfrage. Das Ereignis selbst ist alles nach dem `/event`-Teil einer [!DNL URL]-Zeichenfolge. Wie im folgenden Beispiel gezeigt, erfordert dieser Prozess nur einen einzelnen Ereignisaufruf, um mehrere Variablen an [!DNL Audience Manager] zu übergeben.

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmente: Zweck, Zusammensetzung und Regeln](../features/segments/segments-purpose.md)

