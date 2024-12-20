---
description: Der Bericht zur Segmentleistung vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressions und Konversionsraten. Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und zur Zielgruppenbestimmung an ein Ziel senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber noch nicht zur Zielgruppenbestimmung an ein Ziel gesendet haben. Der Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten hilft Ihnen, bestehende Kampagnen zu optimieren und übersehene Segmente zu finden, die Sie möglicherweise zur Zielgruppenbestimmung an ein Ziel senden möchten.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and conversion rates. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: Bericht zur Segmentleistung
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization Reports
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---

# Bericht zur Segmentleistung{#segment-performance-report}

Der [!UICONTROL Segment Performance] vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressions und Konversionsraten. Ein zugeordnetes Segment ist ein Segment, das Sie erstellen und zur Zielgruppenbestimmung an ein Ziel senden. Ein nicht zugeordnetes Segment ist ein Segment, das Sie erstellt, aber noch nicht zur Zielgruppenbestimmung an ein Ziel gesendet haben. Der Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten hilft Ihnen, bestehende Kampagnen zu optimieren und übersehene Segmente zu finden, die Sie möglicherweise zur Zielgruppenbestimmung an ein Ziel senden möchten.

## Lesen der Ergebnisse zugeordneter Segmente {#read-mapped-segment-results}

Der Bericht Zugeordnete [!UICONTROL Segment Performance] zeigt alle Segmente an, die Sie für das Targeting erstellt und an ein Ziel gesendet haben. Die Position Ihrer zugeordneten Segmente in einem Bericht kann Ihnen eine Menge darüber verraten, welche Segmente eine gute Leistung erbringen und wo Sie möglicherweise Anpassungen vornehmen müssen.

Um den Bericht zu lesen, hilft es, die Ergebnisse in 4 Abschnitte mit imaginären Linien (in rot) und den im folgenden Beispielbericht angezeigten Kategorien zu unterteilen.

![](assets/mapped-segment-performance.png)

Die Beschriftungen im Beispiel und in der folgenden Tabelle können Ihnen dabei helfen, die Segmentleistung zu verstehen und zu verstehen, wie Sie auf diese Ergebnisse reagieren sollen.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Platzierung zeigt Folgendes an </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Oben links</b> </p> </td> 
   <td colname="col2"> <p>Gute Konversionsraten. </p> <p>Möglicherweise können Sie mehr Konversionen erzielen, indem Sie die Impressionen erhöhen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten links</b> </p> </td> 
   <td colname="col2"> <p>Niedrige Konversionsraten. </p> <p>Es empfiehlt sich, diese Segmente nicht anzusprechen. Segmente in diesem Abschnitt eignen sich hervorragend für einen Vergleich mit denen in den nicht zugeordneten Segmentergebnissen. Einige Ihrer nicht zugeordneten Segmente erzielen möglicherweise eine bessere Leistung als die Segmente, auf die Sie bereits abzielen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Oben rechts</b> </p> </td> 
   <td colname="col2"> <p>Hohe Leistung. Lassen Sie diese Segmente unberührt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten rechts</b> </p> </td> 
   <td colname="col2"> <p>Niedrige Konversionsraten und hohe Impressionen. </p> <p>Die Segmente in diesem Abschnitt weisen eine schlechte Leistung auf. Sie können das Budget von diesen Segmenten in Segmente im oberen linken Quadranten des Berichts verschieben. Dadurch werden die Impressionen reduziert und die Konversionsraten für Segmente in diesem Abschnitt unten rechts verbessert. Vergleichen Sie diese zugeordneten Segmente außerdem mit Ihren nicht zugeordneten Segmenten. Einige Ihrer nicht zugeordneten Segmente erzielen möglicherweise eine bessere Leistung als die Segmente, auf die Sie bereits abzielen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lesen der nicht zugeordneten Segmentergebnisse {#read-unmapped-segment-results}

Das Anzeigen nicht zugeordneter Segmente in einem [!UICONTROL Segment Performance] Bericht ist eine hervorragende Möglichkeit, neue Segmente zu finden, die Sie für das Targeting nicht in Betracht gezogen haben. Tatsächlich können einige dieser Segmente Ihre zugeordneten Segmente übertreffen. Dies liegt daran, dass ein nicht gemapptes Segment eine Reihe von Qualifizierungskriterien erfüllen muss, damit es in diesen Bericht aufgenommen werden kann. Um in diesen Bericht aufgenommen zu werden, muss ein nicht zugeordnetes Segment:

* Die Konversionen sind größer als der Durchschnitt aller zugeordneten Segmente.
* Unter den 100 nicht zugeordneten Segmenten nach Konversionsrate sein.

Um diesen Bericht zu lesen, hilft es, die Ergebnisse in 4 Abschnitte mit imaginären Linien (in rot) und Kategorien zu unterteilen, die im folgenden Beispielbericht angezeigt werden.

![](assets/unmapped-segment-performance.png)

In diesem Bericht möchten Sie sich nur auf die nicht zugeordneten Segmente im linken oberen Abschnitt konzentrieren. Diese nicht zugeordneten Segmente zeigen hohe Konversionsraten für eine niedrige Anzahl von Impressions im Vergleich zu den Segmenten in den anderen drei Abschnitten.

>[!NOTE]
>
>7-tägige und 30-tägige Lookback-Zeiträume sind nur für **[!UICONTROL Date Through]** verfügbar.
