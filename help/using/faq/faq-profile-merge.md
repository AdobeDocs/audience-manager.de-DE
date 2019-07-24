---
description: Antworten auf häufig verwendete Regeln für Profilzusammenführung und Gerätediagramm.
keywords: Organisations-ID
seo-description: Antworten auf häufig verwendete Regeln für Profilzusammenführung und Gerätediagramm.
seo-title: Regeln für die Profilzusammenführung und häufig gestellte Fragen zum Gerätediagramm
solution: Audience Manager
title: Regeln für die Profilzusammenführung und häufig gestellte Fragen zum Gerätediagramm
uuid: ba 7986 f 1-078 f -4162-aef 3-b 5 c 8740 cebf 4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rules and Device Graph FAQ{#profile-merge-rules-and-device-graph-faq}

Antworten auf häufig verwendete Regeln für Profilzusammenführung und Gerätediagramm.

<!-- 

profile-merge-faq.xml

 -->

## Device Graph Basics {#device-graph-basics}

**Was ist ein Gerätediagramm?**

Ein Gerätediagramm ist eine Reihe von ID-Zuordnungen, die Gruppen anonymer Geräte definieren. Sie verknüpft diese Geräte einer Person oder einem Haushalt basierend auf gemeinsamen Elementen in den von jedem Gerät erfassten Signalen. Diese Signale helfen bei der Identifizierung von Geräten auf individueller oder privater Ebene.

<br> 

**Was ist ein externes Gerätediagramm?**

An external device graph is any device graph in [!DNL Audience Manager] that has not been created exclusively from your own cross-device data sources. For example, when you create a [Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md) and choose the [!UICONTROL Co-op Device Graph] or third-party device graph options, you're working with an external device graph. See [Device Options](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

<br> 

**Was sind einige häufige Anwendungsfälle für die Verwendung eines externen Gerätediagramms in einem[!UICONTROL Profile Merge Rule]?**

The main objective of using a device graph in a [!UICONTROL Profile Merge Rule] is to evaluate and qualify multiple devices belonging to a single person or household for a specific segment. Das Segment selbst kann mehrere Verwendungen haben, z. B. das Targeting einer Zielgruppe von potenziellen potenziellen Werten durch eine DSP oder das Personalisieren des Onsite-Erlebnisses eines Kunden über eine Personalisierungs-Plattform auf der Site. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

<br> 

**Bietet Audience Manager globale Unterstützung für externe Gerätediagramme?**

Nein. Externe Gerätediagramme sind nur in den USA und Kanada verfügbar.

<br> 

**Wie oft werden[!DNL Audience Manager]externe Gerätediagrammdaten aktualisiert?**

Einmal wöchentlich.

<br> 

## Device Graphs and Profile Merge Rules {#device-graph-profile-merge-rules}

**Wie wird ein Gerätediagramm[!DNL Audience Manager]verwendet?**

In [!DNL Audience Manager], device graphs appear as configuration options when you [create a Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md). Through your [!UICONTROL Profile Merge Rules], these device graphs help [!DNL Audience Manager]:

* Zusammenführen mehrerer Geräteprofile. Dadurch wird eine einzelne Überlagerung der Eigenschaften erstellt.
* Werten Sie die Überlagerung für die Segmentqualifizierung aus (anstatt jedes Geräteprofil einzeln zu bewerten).
* Hinzufügen qualifizierter Geräte zu verfügbaren Segmenten.

<br> 

**Wie viele[!UICONTROL Profile Merge Rules]kann ich erstellen?**

Currently, you can create a maximum of 3 [!UICONTROL Profile Merge Rules].

<br> 

**Wie viele Geräteprofile[!DNL Audience Manager]werden zusammengeführt und gelesen, wenn Sie ein Gerätediagramm in einem[!UICONTROL Profile Merge Rule]Diagramm verwenden?**

When qualifying a device for a segment using a [!UICONTROL Profile Merge Rule], Audience Manager merges and reads the current device profile and a maximum of 3 additional device profiles linked by your selected device graph option.

<br> 

**Welche Geräte qualifizieren sich bei Verwendung eines Gerätediagramms in[!UICONTROL Profile Merge Rule]einer?**

The devices [!DNL Audience Manager] merges and reads are the same devices that are qualified for a segment.

>[!NOTE]
>
>[!DNL Audience Manager] Speichert für externe Gerätediagramme die Zuordnung zwischen Geräten auf Plattformebene und wählt 3 aus, ohne die Beziehung zu den Geräten zu analysieren, die in Ihrer Instanz angezeigt [!DNL Audience Manager]werden.

<br> 

**Welche Geräte *können für ein Segment*mit einem[!UICONTROL Profile Merge Rule]Gerätediagramm qualifiziert werden?**

To qualify for a segment, devices must have been seen by Audience Manager on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created. Außerdem werden die Edge-Server:

* Speichern Sie Profildaten für maximal 14 Tage.
* Löschen Sie ein Geräteprofil, wenn es für über 14 Tage inaktiv war. Hinweis: Diese Aktion entfernt nur Daten von der Kante. Andere Systeme behalten Datensätze für längere Zeiträume bei. See the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).
* Reset the 14-day interval if [!DNL Audience Manager] records any activity for that profile across the entire platform.

See also, [Data Collection Components](../reference/system-components/components-data-collection.md).

<br> 

**Wo können[!DNL Audience Manager]durch ein[!UICONTROL Profile Merge Rule]Gerät qualifizierte Segmente gesendet werden, die ein Gerätediagramm verwenden?**

[!DNL Audience Manager] können Segmente in Batch-Dateien oder in Echtzeit an ein Ziel senden. And, as noted in the FAQ entry above, To qualify for a segment, devices must have been seen by [!DNL Audience Manager] on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created.

<br> 

## Segments, Device Graphs, and Profile Merge Rules {#segments-device-graphs-rules}

**Wie[!DNL Audience Manager]wird ein Gerät nicht mehr segmentiert, wenn es nicht mehr für ein Segment mit einem[!UICONTROL Profile Merge Rule]Gerätediagramm qualifiziert ist?**

Audience Manager merges up to four devices when evaluating segments with a [!UICONTROL Profile Merge Rule] that uses a device graph. Wenn das unsegmentsignal ausgegeben wird, werden das aktuelle Gerät und drei weitere in Echtzeit angezeigte Geräte im Ziel aus dem Segment entfernt. Beispielsweise werden in einem sechs Gerätecluster bis zu vier Geräte zusammengeführt, ausgewertet und für ein Segment qualifiziert. Gleichermaßen werden bis zu vier Geräte zusammengeführt, ausgewertet und nicht segmentiert.

<br> 

**Wenn ein Ziel Geräte aufheben kann, werden Geräte aus Segmenten entfernt, indem[!UICONTROL Profile Merge Rules]Sie ein Gerätediagramm verwenden?**

Ja. Siehe Erläuterung oben.

<br> 

**Wenn ich ein Segment mit einem[!UICONTROL Profile Merge Rule]Gerät erstelle, das ein Gerätediagramm verwendet und das Segment sowohl Echtzeit- als auch Voreingestellte Daten verwendet, wird mein Segment aktualisiert, wenn sich die Daten auf der Seite ändern?**

Nein. Currently, [!DNL Audience Manager] evaluates segments with a [!UICONTROL Profile Merge Rule] that uses a device graph in real-time only. Updates made to on-boarded traits after the segment has been evaluated will be used to qualify the segment when the device is next seen by our [edge data servers](../reference/system-components/components-edge.md). Dies geht davon aus, dass das Geräteprofil weiterhin auf den Edge-Servern aktiv ist und die Daten auf dem lokalen Gerät diesen Systemen zur Verfügung gestellt wurden. See also, the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**Umfassen die Segmentgrößenschätzungen Geräte, die sich auf ein Segment beziehen, das auf Verbindungen basiert,[!UICONTROL Profile Merge Rule]die eine Gerätediagrammoption verwenden?**

Nein. See the definitions for the [!UICONTROL Estimated Real-Time Population] and [!UICONTROL Estimated Total Population] in [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

**Sind[!UICONTROL Addressable Audiences]Geräte, die sich auf ein Segment beziehen, auf der Grundlage von Verbindungen enthalten, die[!UICONTROL Profile Merge Rule]eine Gerätediagrammoption verwenden?**

Ja.

<br> 

**Wenn ein Segment a[!UICONTROL Profile Merge Rule]und die[!UICONTROL No Authenticated Profile]Eigenschaften verwendet, die Geräte für das Segment nur für das authentifizierte Profil qualifizieren, wird die Gesamtpopulation des Segments 0 betragen?**

Nein. Heute zählt Audience Manager die Geräte, die dem authentifizierten Profil als qualifiziert für das Segment zugeordnet sind.

<br> 

## Trait Frequency, Device Graphs, and Profile Merge Rules {#trait-freq-device-rules}

**Wie[!DNL Audience Manager]wird die Berechnung der Eigenschaftsfrequenz mit einem[!UICONTROL Profile Merge Rule]Gerätediagramm berechnet?**

Die Eigenschaftsfrequenz wird durch die Summe der Qualifikationen für eine bestimmte Eigenschaft auf mehreren Geräten definiert. Um dies zu verstehen, sollten Sie sich den folgenden Verwendungsfall ansehen.

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nutzungsszenario </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Bedingungen</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">Geräte A und Gerät B werden durch ein Gerätediagramm verknüpft. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">You have a <span class="wintitle"> Profile Merge Rule</span> that uses a device graph option. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Ein einzelnes Segment (Segment 1), bestehend aus einer einzelnen Eigenschaft (Trait 1), bei der Trait 1 eine Frequenz von 8 hat. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Aktionen</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> liest und führt die Geräteprofile für Geräte A und Gerät B zusammen. Hier sehen wir Folgendes: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Device A ist für Trait 1 dreimal qualifiziert. Für Trait 1 gibt es eine Frequenz von 3. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Gerät B ist fünfmal für Trait qualifiziert. Es hat eine Frequenz von 5 für Trait 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> gibt die Frequenz für Trait 1 zurück und verwendet 8 (3 + 5 = 8), um die Segmentqualifizierung zu bestimmen. Das Gerät A und das Gerät B qualifizieren sich für Segment 1, da es eine Frequenz von 8 aufweist. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

## Reports, Device Graphs, and Profile Merge Rules {#reports-device-graphs-rules}

**Kann ich die Anzahl der Geräte sehen, die durch ein[!UICONTROL Profile Merge Rule]Gerätediagramm erreicht werden können?**

Ja. Reports return data at the [!UICONTROL Profile Merge Rule] level. Die Berichtsdaten werden täglich aktualisiert. Daten basieren auf den Geräten, die in Ihrem Konto angezeigt werden, nicht auf den von einem Gerätediagramm verknüpften Geräten. See [Report Metrics for Profile Merge Rules](../features/profile-merge-rules/profile-link-metrics.md).

<br> 

**Kann ich feststellen, wie viele Geräte für ein bestimmtes Segment in *Echtzeit*qualifiziert sind, wobei[!UICONTROL Profile Merge Rules]es ein Gerätediagramm verwendet?**

Ja. Die Echtzeit-Populationsmetrik erfasst Segmentqualifikationen für das aktuelle Gerät (das in Echtzeit angezeigte Gerät) anhand der Profile aller Geräte, die mit einem Gerätediagramm verknüpft sind.

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element des Nutzungsszenarios </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Bedingungen</b> </p> </td> 
   <td colname="col2"> <p>Angenommen wir haben: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segment 1 baut auf folgenden Eigenschaften und Qualifizierungslogik auf: Segment 1 = Merkmal A und Trait B und Trait C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 Geräteprofile: Gerät 1 (aktuelles Gerät), Gerät 2 (Gerätediagramm), Gerät 3 (Gerätediagramm). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Aktionen</b> </p> </td> 
   <td colname="col2"> <p>Jede verfügbare Eigenschaft ist mit einem Gerät verknüpft: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Gerät 1: Merkmal A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Gerät 2: Trait B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Gerät 3: Trait C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p>Bei den vorherigen Elementen ist die Gesamtpopulation für Segment 1 1. </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. Das bedeutet, dass Geräte 1, 2 und 3 für Segment 1 qualifiziert sind, aber wie oben vermerkt, ist in der Echtzeit-Segmentpopulation nur Device 1 enthalten. Dies liegt daran, dass: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Device 1 is the current device interacting with the Audience Manager <span class="wintitle"> Data Collection Servers</span> (<span class="wintitle"> DCS</span>) in real-time. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Geräte 2 und 3 sind mit Device 1 durch ein Gerätediagramm verknüpft, aber sie interagieren nicht gleichzeitig mit dem DCS mit Gerät 1. </li> 
     </ul> </p> <p>Daher sind die Geräte 2 und 3 nicht in der Echtzeit-Segmentmetrik enthalten. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**Kann ich erkennen, wie viele Geräte für ein bestimmtes Segment qualifiziert sind, das[!UICONTROL Profile Merge Rule]ein Gerätediagramm verwendet?**

Ja. Die Gesamtanzahl der Segmentpopulationen umfasst die zusätzlichen Geräte, die auf der Grundlage der Verbindungen von einem Gerätediagramm für ein Segment qualifiziert sind.

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element des Nutzungsszenarios </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Bedingungen</b> </p> </td> 
   <td colname="col2"> <p>Angenommen wir haben: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segment 1 baut auf folgenden Eigenschaften und Qualifizierungslogik auf: Segment 1 = Merkmal A und Trait B und Trait C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 Geräteprofile: Gerät 1 (aktuelles Gerät), Gerät 2 (Gerätediagramm), Gerät 3 (Gerätediagramm). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Verbindungen</b> </p> </td> 
   <td colname="col2"> <p>Jede verfügbare Eigenschaft ist mit einem Gerät verknüpft: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Gerät 1: Merkmal A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Gerät 2: Trait B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Gerät 3: Trait C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p>Bei den vorherigen Elementen beträgt die Gesamtpopulation für Segment 1 drei (3). </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. Dies bedeutet, dass die Geräte 1, 2 und 3 für Segment 1 qualifiziert sind und alle drei in der Gesamtpopulation enthalten sind. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**Sind Geräte, die sich für ein Segment qualifizieren,[!UICONTROL Profile Merge Rule]in den[!UICONTROL Interactive]Berichten,[!UICONTROL Overlap]Berichten und[!UICONTROL Audience Optimization]Berichten ein Gerätediagramm enthalten?**

Nein

>[!MORE_ LIKE_ THIS]
>
>* [Profillink](../features/profile-merge-rules/merge-rules-overview.md)

