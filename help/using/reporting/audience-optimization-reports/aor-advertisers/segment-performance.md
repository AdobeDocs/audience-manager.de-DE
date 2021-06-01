---
description: Der Bericht zur Segmentleistung vergleicht zugeordnete und nicht zugeordnete Segmente anhand von Impressionen und Konversionsraten. Ein gemapptes Segment ist ein Segment, das Sie erstellen und zur Zielgruppenbestimmung an ein Ziel senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber nicht zur Zielgruppenbestimmung an ein Ziel gesendet haben. Durch den Vergleich dieser verschiedenen Segmenttypen innerhalb von und zwischen Berichten können Sie vorhandene Kampagnen optimieren und übersehene Segmente finden, die Sie zum Targeting an ein Ziel senden möchten.
seo-description: Der Bericht zur Segmentleistung vergleicht zugeordnete und nicht zugeordnete Segmente anhand von Impressionen und Konversionsraten. Ein gemapptes Segment ist ein Segment, das Sie erstellen und zur Zielgruppenbestimmung an ein Ziel senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber nicht zur Zielgruppenbestimmung an ein Ziel gesendet haben. Durch den Vergleich dieser verschiedenen Segmenttypen innerhalb von und zwischen Berichten können Sie vorhandene Kampagnen optimieren und übersehene Segmente finden, die Sie zum Targeting an ein Ziel senden möchten.
seo-title: Bericht zur Segmentleistung
solution: Audience Manager
title: Bericht zur Segmentleistung
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Berichte zur Zielgruppenoptimierung
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---

# Bericht zur Segmentleistung{#segment-performance-report}

Der Bericht [!UICONTROL Segment Performance] vergleicht zugeordnete und nicht zugeordnete Segmente anhand von Impressionen und Konversionsraten. Ein gemapptes Segment ist ein Segment, das Sie erstellen und zur Zielgruppenbestimmung an ein Ziel senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber nicht zur Zielgruppenbestimmung an ein Ziel gesendet haben. Durch den Vergleich dieser verschiedenen Segmenttypen innerhalb von und zwischen Berichten können Sie vorhandene Kampagnen optimieren und übersehene Segmente finden, die Sie zum Targeting an ein Ziel senden möchten.

## So lesen Sie die zugeordneten Segmentergebnisse {#read-mapped-segment-results}

Der zugeordnete [!UICONTROL Segment Performance] -Bericht zeigt alle Segmente an, die Sie erstellt und an ein Ziel für die Zielgruppenbestimmung gesendet haben. Die Position Ihrer zugeordneten Segmente in einem Bericht kann Ihnen Aufschluss darüber geben, welche Segmente eine gute Performance aufweisen und wo Sie möglicherweise einige Anpassungen vornehmen müssen.

Zum Lesen des Berichts hilft es, die Ergebnisse in 4 Abschnitte mit imaginären Zeilen (in Rot) und den im Beispielbericht unten angezeigten Kategorien zu unterteilen.

![](assets/mapped-segment-performance.png)

Die Bezeichnungen im Beispiel und in der folgenden Tabelle können Ihnen dabei helfen, die Segmentleistung und die Reaktion auf diese Ergebnisse zu verstehen.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Platzierungsangaben </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Oben links</b> </p> </td> 
   <td colname="col2"> <p>Gute Konversionsraten. </p> <p>Sie können möglicherweise mehr Konversionen erhalten, indem Sie die Impressionen erhöhen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten links</b> </p> </td> 
   <td colname="col2"> <p>Niedrige Konversionsraten. </p> <p>Möglicherweise möchten Sie das Targeting dieser Segmente vermeiden. Segmente in diesem Abschnitt eignen sich hervorragend für den Vergleich mit den Segmentergebnissen, die nicht zugeordnet sind. Einige Ihrer nicht zugeordneten Segmente können eine bessere Leistung erzielen als die Segmente, die Sie bereits als Ziel auswählen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Oben rechts</b> </p> </td> 
   <td colname="col2"> <p>Starke Leistung. Lassen Sie diese Segmente in Ruhe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten rechts</b> </p> </td> 
   <td colname="col2"> <p>Niedrige Konversionsraten und hohe Impressionen. </p> <p>Die Leistung von Segmenten in diesem Abschnitt ist nicht gut. Möglicherweise möchten Sie das Budget von diesen Segmenten in Segmente im oberen linken Quadrant des Berichts verschieben. Dies hilft, die Impressionen zu reduzieren und kann dazu beitragen, die Konversionsraten für Segmente in diesem rechten unteren Abschnitt zu verbessern. Vergleichen Sie diese zugeordneten Segmente auch mit Ihren nicht zugeordneten Segmenten. Einige Ihrer nicht zugeordneten Segmente können eine bessere Leistung erzielen als die Segmente, die Sie bereits als Ziel auswählen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lesen der nicht zugeordneten Segmentergebnisse {#read-unmapped-segment-results}

Wenn Sie sich nicht zugeordnete Segmente in einem [!UICONTROL Segment Performance] -Bericht ansehen, ist dies eine großartige Möglichkeit, neue Segmente zu finden, die Sie für das Targeting nicht berücksichtigt haben. Tatsächlich können einige dieser Segmente Ihre zugeordneten Segmente übertreffen. Dies liegt daran, dass ein nicht zugeordnetes Segment einen Satz von Qualifikationskriterien erfüllen muss, um in diesen Bericht aufgenommen zu werden. Um in diesen Bericht aufgenommen zu werden, muss ein nicht zugeordnetes Segment:

* Sie haben Konversionen, die über dem Durchschnitt aller Ihrer zugeordneten Segmente liegen.
* Befinden Sie sich nach Konversionsrate in den 100 nicht zugeordneten Segmenten.

Zum Lesen dieses Berichts hilft es, die Ergebnisse in 4 Abschnitte mit imaginären Zeilen (in Rot) und Kategorien zu unterteilen, die im Beispielbericht unten angezeigt werden.

![](assets/unmapped-segment-performance.png)

In diesem Bericht möchten Sie sich nur auf die nicht zugeordneten Segmente im oberen linken Bereich konzentrieren. Diese nicht zugeordneten Segmente weisen im Vergleich zu Segmenten in den anderen drei Abschnitten hohe Konversionsraten für ein geringes Maß an Impressionen auf.

>[!NOTE]
>
>7- und 30-tägige Rückblickszeiträume sind nur für Sonntag-**[!UICONTROL Date Through]** -Daten verfügbar.
