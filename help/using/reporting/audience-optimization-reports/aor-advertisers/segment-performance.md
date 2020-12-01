---
description: Der Segmentleistungsbericht vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressionen und Konversionsraten. Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde. Durch den Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten können Sie vorhandene Kampagnen optimieren und übersehene Segmente finden, die Sie zum Targeting an ein Ziel senden möchten.
seo-description: Der Segmentleistungsbericht vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressionen und Konversionsraten. Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde. Durch den Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten können Sie vorhandene Kampagnen optimieren und übersehene Segmente finden, die Sie zum Targeting an ein Ziel senden möchten.
seo-title: Bericht zur Segmentleistung
solution: Audience Manager
title: Bericht zur Segmentleistung
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 1%

---


# Bericht zur Segmentleistung{#segment-performance-report}

Der Bericht [!UICONTROL Segment Performance] vergleicht zugeordnete und nicht zugeordnete Segmente nach Impressionen und Konversionsraten. Ein zugeordnete Segment ist ein Segment, das Sie erstellen und zum Targeting an ein Ziel senden. Ein nicht zugeordnete Segment ist ein Segment, das Sie erstellt haben, das jedoch nicht zum Targeting an ein Ziel gesendet wurde. Durch den Vergleich dieser verschiedenen Segmenttypen innerhalb und zwischen Berichten können Sie vorhandene Kampagnen optimieren und übersehene Segmente finden, die Sie zum Targeting an ein Ziel senden möchten.

## Lesen der zugeordneten Segmentergebnisse {#read-mapped-segment-results}

Der zugeordnete [!UICONTROL Segment Performance]-Bericht zeigt alle Segmente an, die Sie erstellt haben und an ein Targeting-Ziel gesendet haben. Die Position Ihrer zugeordneten Segmente in einem Bericht kann Ihnen eine Menge darüber vermitteln, welche Segmente sich gut entwickeln und wo Sie möglicherweise einige Anpassungen vornehmen müssen.

Zum Lesen des Berichts hilft er, die Ergebnisse in 4 Abschnitte mit imaginären Zeilen (in Rot) und den Kategorien im Beispielbericht unten aufzuteilen.

![](assets/mapped-segment-performance.png)

Die Beschriftungen im Beispiel und in der folgenden Tabelle können Ihnen dabei helfen, die Segmentleistung und die Reaktion auf diese Ergebnisse zu verstehen.

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
   <td colname="col2"> <p>Gute Konversionsraten. </p> <p>Möglicherweise erhalten Sie mehr Konversionen, indem Sie die Impressionen erhöhen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten links</b> </p> </td> 
   <td colname="col2"> <p>Niedrige Konversionsraten. </p> <p>Möglicherweise sollten Sie das Targeting dieser Segmente vermeiden. Segmente in diesem Abschnitt bieten gute Kandidaten für einen Vergleich mit denen in den nicht zugeordneten Segmentergebnissen. Einige Ihrer nicht zugeordneten Segmente können leistungsfähiger sein als die Segmente, für die Sie bereits Targeting durchführen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Oben rechts</b> </p> </td> 
   <td colname="col2"> <p>Starke Leistung. Lassen Sie diese Segmente allein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Unten rechts</b> </p> </td> 
   <td colname="col2"> <p>Niedrige Konversionsraten und hohe Impressionen. </p> <p>Segmente in diesem Abschnitt funktionieren nicht gut. Möglicherweise möchten Sie das Budget von diesen Segmenten in Segmente im oberen linken Quadranten des Berichts verschieben. Dies wird dazu beitragen, die Impressionen zu reduzieren, und kann dazu beitragen, die Konversionsraten für Segmente in diesem Abschnitt unten rechts zu verbessern. Vergleichen Sie diese zugeordneten Segmente auch mit Ihren nicht zugeordneten Segmenten. Einige Ihrer nicht zugeordneten Segmente können leistungsfähiger sein als die Segmente, für die Sie bereits Targeting durchführen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lesen der nicht zugeordneten Segmentergebnisse {#read-unmapped-segment-results}

Wenn Sie sich nicht zugeordnete Segmente in einem [!UICONTROL Segment Performance]-Bericht ansehen, können Sie auf diese Weise neue Segmente finden, die Sie für das Targeting nicht berücksichtigt haben. Tatsächlich können einige dieser Segmente Ihre zugeordneten Segmente übertreffen. Dies liegt daran, dass ein nicht zugeordnete Segment eine Reihe von Qualifikationskriterien erfüllen muss, die in diesen Bericht aufgenommen werden müssen. Um in diesen Bericht aufgenommen zu werden, muss ein nicht zugeordnete Segment:

* Übernehmen Sie Konversionen, die den Durchschnitt aller zugeordneten Segmente überschreiten.
* Befinden Sie sich Konversionsrat in den 100 unzugeordneten Segmenten.

Zum Lesen dieses Berichts hilft es, die Ergebnisse in 4 Abschnitte mit imaginären Zeilen (in Rot) und Kategorien im Beispielbericht unten aufzuteilen.

![](assets/unmapped-segment-performance.png)

In diesem Bericht möchten Sie sich nur auf die nicht zugeordneten Segmente im oberen linken Abschnitt konzentrieren. Diese nicht zugeordneten Segmente weisen im Vergleich zu Segmenten in den anderen drei Abschnitten hohe Konversionsraten für eine niedrige Impressionsstufe auf.

>[!NOTE]
>
>7-Tage- und 30-Tage-Lookback-Zeiträume sind nur für Sonntag **[!UICONTROL Date Through]**-Daten verfügbar.
