---
description: Antworten auf häufig gestellte Fragen zur Profilzusammenführungsrichtlinie und zum Gerätediagramm.
keywords: Organisations-ID
seo-description: Antworten auf häufig gestellte Fragen zur Profilzusammenführungsrichtlinie und zum Gerätediagramm.
seo-title: Häufig gestellte Fragen zu Profilzusammenführungsrichtlinien und zum Gerätediagramm
solution: Audience Manager
title: Häufig gestellte Fragen zu Profilzusammenführungsrichtlinien und zum Gerätediagramm
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
feature: Profilzusammenführung
exl-id: 03ad79b7-a111-437e-82c5-c7406bd33c39
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1552'
ht-degree: 86%

---

# Häufig gestellte Fragen zu Profilzusammenführungsrichtlinien und zum Gerätediagramm{#profile-merge-rules-and-device-graph-faq}

Antworten auf häufig gestellte Fragen zur Profilzusammenführungsrichtlinie und zum Gerätediagramm.

<!-- profile-merge-faq.xml -->

## Grundlagen zum Gerätediagramm {#device-graph-basics}

**Was ist ein Gerätediagramm?**

Ein Gerätediagramm ist ein Satz von ID-Zuordnungen, der Gruppen anonymer Geräte definiert. Diese Geräte werden basierend auf gemeinsamen Elementen in den von jedem Gerät gesammelten Signalen einer Person oder einem Haushalt zugeordnet. Diese Signale helfen bei der Identifizierung von Geräten auf individueller oder Haushaltsebene.

 

**Was ist ein externes Gerätediagramm?**

Ein externes Gerätediagramm ist ein Gerätediagramm in [!DNL Audience Manager], das nicht ausschließlich aus Ihren eigenen geräteübergreifenden Datenquellen erstellt wurde. Wenn Sie z. B. eine [Profilzusammenführungsrichtlinie](../features/profile-merge-rules/merge-rules-start.md) erstellen und das [!UICONTROL Co-op Device Graph] oder ein Gerätediagramm von Drittanbietern auswählen, arbeiten Sie mit einem externen Gerätediagramm. Siehe [Geräteoptionen](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

 

**Was sind einige häufige Anwendungsfälle für die Verwendung eines externen Gerätediagramms in einer [!UICONTROL Profile Merge Rule]?**

Ein Gerätediagramm wird in einer [!UICONTROL Profile Merge Rule] hauptsächlich dazu verwendet, mehrere Geräte, die einer einzelnen Person oder einem Haushalt gehören, für ein bestimmtes Segment zu bewerten und zu qualifizieren. Das Segment selbst kann mehrere Verwendungszwecke haben, z. B., um eine potenzielle Zielgruppe mit einer von einer DSP gelieferten Anzeige anzusprechen oder das On-site-Erlebnis eines Kunden über eine On-site-Personalisierungsplattform zu personalisieren. Siehe [Anwendungsfälle für externe Gerätediagramme](../features/profile-merge-rules/external-graph-use-cases.md).

 

**Bietet Audience Manager globale Unterstützung für externe Gerätediagramme?**

Nein. Externe Gerätediagramme sind nur in den USA und Kanada verfügbar.

 

**Wie oft aktualisiert [!DNL Audience Manager] externe Gerätediagrammdaten?**

Einmal pro Woche.

 

## Gerätediagramme und Profilzusammenführungsrichtlinien {#device-graph-profile-merge-rules}

**Wie werden Gerätediagramme in [!DNL Audience Manager] verwendet?**

Gerätediagramme werden in [!DNL Audience Manager] als Konfigurationsoptionen angezeigt, wenn Sie eine [Profilzusammenführungsrichtlinien erstellen](../features/profile-merge-rules/merge-rules-start.md). Über Ihre [!UICONTROL Profile Merge Rules] unterstützen diese Gerätediagramme [!DNL Audience Manager] bei Folgendem:

* Zusammenführen mehrerer Geräteprofile. Dadurch wird eine Obermenge von Eigenschaften erstellt.
* Bewerten der Obermenge der Eigenschaften zur Segmentqualifizierung (anstatt jedes Geräteprofil einzeln zu bewerten).
* Hinzufügen qualifizierter Geräte zu verfügbaren Segmenten.

 

**Wie viele [!UICONTROL Profile Merge Rules] kann ich erstellen?**

Derzeit können Sie maximal 4 [!UICONTROL Profile Merge Rules]erstellen. Die vierte Profilzusammenführungsrichtlinie ([!UICONTROL All Cross-Device Profiles]) steht nur Kunden zur Verfügung, die das Add-on [!UICONTROL People-Based Destinations] erwerben.

 

**Wie viele Geräteprofile werden von [!DNL Audience Manager] zusammengeführt und gelesen, wenn ein Gerätediagramm in einer [!UICONTROL Profile Merge Rule] verwendet wird?**

Beim Qualifizieren eines Geräts für ein Segment mithilfe einer [!UICONTROL Profile Merge Rule], führt Audience Manager das aktuelle Geräteprofil und maximal 99 weitere zusätzliche Geräteprofile, die durch die ausgewählte Gerätediagrammoption verknüpft sind, zusammen und liest diese.

 

**Welche Geräte qualifizieren sich für ein Segment, wenn ein Gerätediagramm in einer [!UICONTROL Profile Merge Rule] verwendet wird?**

Die Geräte, die von [!DNL Audience Manager] zusammenführt und gelesen werden, sind dieselben Geräte, die für ein Segment qualifiziert sind.

 

**Wohin kann [!DNL Audience Manager] Segmente senden, die von einer [!UICONTROL Profile Merge Rule] qualifiziert wurden, die ein Gerätediagramm verwendet?**

[!DNL Audience Manager] kann Segmente in Batch-Dateien oder in Echtzeit an ein Ziel senden.

 

## Segmente, Gerätediagramme und Profilzusammenführungsrichtlinien {#segments-device-graphs-rules}

**Wie wird die Segmentierung eines Geräts in [!DNL Audience Manager] aufgehoben, wenn es nicht mehr für ein Segment mit einer [!UICONTROL Profile Merge Rule] qualifiziert ist, die ein Gerätediagramm verwendet?**

Audience Manager führt bis zu 100 Geräte zusammen, wenn Segmente mit einer [!UICONTROL Profile Merge Rule] ausgewertet werden, die ein Gerätediagramm verwendet. Wenn das Signal zur Aufhebung der Segmentierung ausgegeben wird, werden das aktuelle Gerät und bis zu 99 zusätzliche Geräte aus dem Segment im Ziel entfernt. Weitere Informationen zur Aufhebung der Segmentierung finden Sie unter [Profilzusammenführungsrichtlinien und Prozesse zum Aufhebung der Gerätesegmentierung](../features/profile-merge-rules/merge-rule-unsegment.md).

 

**Wenn ein Ziel die Segmentierung von Geräten aufheben kann, werden Geräte von [!UICONTROL Profile Merge Rules], die ein Gerätediagramm verwenden, aus den Segmenten entfernt?**

Ja. Siehe die Erklärung oben.

 

**Wenn ich ein Segment mit einer [!UICONTROL Profile Merge Rule] erstelle, die ein Gerätediagramm verwendet, und das Segment sowohl Echtzeitdaten als auch integrierte Daten verwendet, wird mein Segment aktualisiert, wenn sich die integrierten Daten ändern?**

Ja.

 

**Umfassen Schätzungen der Segmentgröße Geräte, die sich für ein Segment qualifizieren, basierend auf Verbindungen, die von einer [!UICONTROL Profile Merge Rule] bereitgestellt werden, die eine Gerätediagrammoption verwendet?**

Nein. Siehe die Definitionen für [!UICONTROL Estimated Real-Time Population] und [!UICONTROL Estimated Total Population] in [Eigenschafts- und Segmentpopulationsdaten in Segment Builder](https://docs.adobe.com/content/help/de-DE/audience-manager/user-guide/features/segments/segment-builder-data.html).

 

**Umfassen [!UICONTROL Addressable Audiences] Geräte, die sich für ein Segment qualifizieren, basierend auf Verbindungen, die von einer [!UICONTROL Profile Merge Rule] bereitgestellt werden, die eine Gerätediagrammoption verwendet?**

Ja.

 

**Wenn ein Segment eine [!UICONTROL Profile Merge Rule] mit [!UICONTROL No Cross-Device Profile] verwendet und die Eigenschaften, die Geräte für das Segment qualifizieren, nur im geräteübergreifenden Profil gespeichert werden, beträgt die Gesamtpopulation des Segments 0?**

Ja. Audience Manager zählt die im geräteübergreifenden Profil in der Segmentbewertung gespeicherten Eigenschaften nicht, wenn die Profilzusammenführungsrichtlinie auf [!UICONTROL No Cross-Device Profile] festgelegt ist.

 

## Häufigkeit von Eigenschaften, Gerätediagramme und Profilzusammenführungsrichtlinien {#trait-freq-device-rules}

**Wie berechnet [!DNL Audience Manager] die Häufigkeit von Eigenschaften mit einer [!UICONTROL Profile Merge Rule], die einen Gerätegraphen verwendet?**

Die Häufigkeit der Eigenschaften wird durch die Summe der Anzahl der Qualifikationen für eine bestimmte Eigenschaft über mehrere Geräte hinweg definiert. Sehen Sie sich den folgenden Anwendungsfall an, um dies zu verstehen.

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Anwendungsfall </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Bedingungen</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">Geräte A und B sind durch ein Gerätediagramm verknüpft. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">Sie haben eine <span class="wintitle">Profilzusammenführungsrichtlinie</span>, die eine Gerätediagrammoption verwendet. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Ein einzelnes Segment (Segment 1), das aus einer einzelnen Eigenschaft besteht (Eigenschaft 1), wobei Eigenschaft 1 eine Häufigkeit von 8 hat. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Aktionen</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> liest und führt die Geräteprofile für Geräte A und B zusammen. Daraus ergibt sich Folgendes: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Gerät A hat sich für Eigenschaft 1 dreimal qualifiziert. Für Eigenschaft 1 beträgt die Häufigkeit 3. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Gerät B hat sich für Eigenschaft 1 fünfmal qualifiziert. Für Eigenschaft 1 beträgt die Häufigkeit 5. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> fasst die Häufigkeit für Eigenschaft 1 zusammen und verwendet 8 (3 + 5 = 8), um die Segmentqualifizierung zu bestimmen. Geräte A und B sind für Segment 1 qualifiziert, da die Häufigkeit 8 beträgt. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Berichte, Gerätediagramme und Profilzusammenführungsrichtlinien {#reports-device-graphs-rules}

**Kann ich die Anzahl der Geräte sehen, die von einer [!UICONTROL Profile Merge Rule], die ein Gerätediagramm verwendet, erreicht werden können?**

Ja. Berichte geben Daten auf der Ebene der [!UICONTROL Profile Merge Rule] zurück. Die Berichtsdaten werden täglich aktualisiert. Die Daten basieren auf den Geräten, die in Ihrem Konto zu sehen sind, nicht auf denen, die durch ein Gerätediagramm verknüpft sind. Siehe [Berichtsmetriken für Profilzusammenführungsrichtlinien](../features/profile-merge-rules/profile-link-metrics.md).

 

**Kann ich die Anzahl der Geräte sehen, die sich für ein bestimmtes Segment mit [!UICONTROL Profile Merge Rules], die ein Gerätediagramm verwenden, in *Echtzeit* qualifiziert haben?**

Ja. Die Echtzeit-Populationsmetrik erfasst Segmentqualifikationen für das aktuelle Gerät (das in Echtzeit angezeigte Gerät) anhand der Profile aller Geräte, die durch ein Gerätediagramm verknüpft sind.

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element des Anwendungsfalls </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Bedingungen</b> </p> </td> 
   <td colname="col2"> <p>Annahme: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segment 1 basiert auf diesen Eigenschaften und der Qualifikationslogik: Segment 1 = Eigenschaft A und Eigenschaft B und Eigenschaft C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 Geräteprofile: Gerät 1 (aktuelles Gerät), Gerät 2 (Gerätediagramm), Gerät 3 (Gerätediagramm). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Aktionen</b> </p> </td> 
   <td colname="col2"> <p>Jede verfügbare Eigenschaft ist mit einem Gerät verknüpft: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Gerät 1: Eigenschaft A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Gerät 2: Eigenschaft B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Gerät 3: Eigenschaft C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p>Bei den vorherigen Elementen ist die Gesamtpopulation für Segment 1 eins. </p> <p>In diesem Fall verwendet die <span class="wintitle">Profilzusammenführungsrichtlinie</span> alle Geräte und deren Eigenschaften, um die Segmentqualifizierung zu bestimmen. Das bedeutet, dass die Geräte 1, 2 und 3 für Segment 1 qualifiziert sind. Wie oben erwähnt, wird jedoch nur Gerät 1 in der Segmentpopulation in Echtzeit berücksichtigt. Dies liegt an Folgendem: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Gerät 1 ist das aktuelle Gerät, das mit den <span class="wintitle"> Datenerfassungs-Servern</span> (<span class="wintitle">DCS</span>) von Audience Manager in Echtzeit interagiert. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Die Geräte 2 und 3 werden mit Gerät 1 durch ein Gerätediagramm verknüpft, sie interagieren jedoch nicht mit den DCS gleichzeitig mit Gerät 1. </li> 
     </ul> </p> <p>Dementsprechend werden die Geräte 2 und 3 nicht in die Populationsmetrik für Segmente in Echtzeit einbezogen. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Kann ich die Gesamtzahl der Geräte anzeigen, die für ein bestimmtes Segment mit einer [!UICONTROL Profile Merge Rule] qualifiziert sind, die ein Gerätediagramm verwendet?**

Ja. Die Populationsmetrik für das gesamte Segment umfasst die zusätzlichen Geräte, die sich für ein Segment auf der Grundlage der Verbindungen eines Gerätediagramms qualifiziert haben.

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element des Anwendungsfalls </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Bedingungen</b> </p> </td> 
   <td colname="col2"> <p>Annahme: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segment 1 basiert auf diesen Eigenschaften und der Qualifikationslogik: Segment 1 = Eigenschaft A und Eigenschaft B und Eigenschaft C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 Geräteprofile: Gerät 1 (aktuelles Gerät), Gerät 2 (Gerätediagramm), Gerät 3 (Gerätediagramm). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Verknüpfungen</b> </p> </td> 
   <td colname="col2"> <p>Jede verfügbare Eigenschaft ist mit einem Gerät verknüpft: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Gerät 1: Eigenschaft A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Gerät 2: Eigenschaft B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Gerät 3: Eigenschaft C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p>Bei den vorherigen Elementen ist die Gesamtpopulation für Segment 1 drei (3). </p> <p>In diesem Fall verwendet die <span class="wintitle">Profilzusammenführungsrichtlinie</span> alle Geräte und deren Eigenschaften, um die Segmentqualifizierung zu bestimmen. Das bedeutet, dass die Geräte 1, 2 und 3 für Segment 1 qualifiziert sind und alle drei in der Gesamtpopulation enthalten sind. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Sind Geräte, die sich für ein Segment mit einer [!UICONTROL Profile Merge Rule] qualifizieren, die ein Gerätediagramm verwendet, in den [!UICONTROL Interactive]-Berichten, [!UICONTROL Overlap]-Berichten und den [!UICONTROL Audience Optimization]-Berichten enthalten?**

Nein.

**Warum sehe ich nach dem 16. März 2020 für Segmentexporte nach Adobe Campaign eine Segmentpopulation von null?**

Ende 2019 haben wir eine Reihe von Verbesserungen der Profilzusammenführungsrichtlinien veröffentlicht, um die Genauigkeit von Batch-Dateien zu verbessern, die mit geräteübergreifenden IDs generiert wurden. Diese Verbesserungen werden in Ihrer Audience Manager-Instanz ab Montag, dem 16. März 2020 strikt berücksichtigt. Folglich produzieren Segmente, die mit geräteübergreifenden IDs einem Ziel zugeordnet sind, in einigen Konfigurationen der Profilzusammenführungsrichtlinien keine Exporte mehr.

Um die korrekte Integration zwischen Ihrer Audience Manager-Instanz und Zielen mithilfe geräteübergreifender IDs wie Adobe Campaign sicherzustellen, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:

1. Überprüfen Sie die Profilzusammenführungsrichtlinie , die von den Segmenten verwendet wird, die Ihrem Adobe Campaign Declared ID-Ziel zugeordnet sind. Die Profilzusammenführungsrichtlinie muss die Option [!UICONTROL Last Authenticated Profile] verwenden, damit alle authentifizierten Profile in die Exporte einbezogen werden können. Wenn Ihre Profilzusammenführungsrichtlinie eine andere Option verwendet, wechseln Sie zu [!UICONTROL Last Authenticated Profile].
2. Wählen Sie die Datenquelle Adobe Campaign Declared ID in den Profilzusammenführungsregeleinstellungen aus.

>[!NOTE]
>
> Für Kunden, die sich dieser Situation gegenübersehen, wurde die Beschränkung der Profilzusammenführungsrichtlinie um 1 erhöht, sodass Sie eine dedizierte Profilzusammenführungsrichtlinie für die Segmente erstellen können, die dem Adobe Campaign Declared ID-Ziel zugeordnet sind, ohne die Profilzusammenführungsrichtlinien für andere Anwendungsfälle zu ändern.

>[!MORELIKETHIS]
>
>* [Profil-Link](../features/profile-merge-rules/profile-link-use-case.md)

