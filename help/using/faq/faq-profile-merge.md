---
description: Antworten auf häufig gestellte Fragen zur Profil Merge Rule und zum Gerätediagramm.
keywords: Organization ID
seo-description: Antworten auf häufig gestellte Fragen zur Profil Merge Rule und zum Gerätediagramm.
seo-title: Häufig gestellte Fragen zu Profil Merge Rules and Device Graph
solution: Audience Manager
title: Häufig gestellte Fragen zu Profil Merge Rules and Device Graph
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1548'
ht-degree: 2%

---


# Häufig gestellte Fragen zu Profil Merge Rules and Device Graph{#profile-merge-rules-and-device-graph-faq}

Antworten auf häufig gestellte Fragen zur Profil Merge Rule und zum Gerätediagramm.

<!-- profile-merge-faq.xml -->

## Grundlagen zum Gerätediagramm {#device-graph-basics}

**Was ist ein Gerätediagramm?**

Ein Gerätediagramm ist ein Satz von ID-Zuordnungen, die Gruppen anonymer Geräte definieren. Diese Geräte werden einer Person oder einem Haushalt auf der Grundlage gemeinsamer Elemente in den Signalen, die von jedem Gerät erfasst werden, zugeordnet. Diese Signale helfen bei der Identifizierung von Geräten auf der Ebene des Einzelnen oder des Haushalts.

 

**Was ist ein externes Gerätediagramm?**

Ein externes Gerätediagramm ist ein Gerätediagramm, [!DNL Audience Manager] das nicht ausschließlich aus eigenen geräteübergreifenden Datenquellen erstellt wurde. Wenn Sie z. B. eine [Profil Merge Rule](../features/profile-merge-rules/merge-rules-start.md) erstellen und die Diagrammoptionen für Geräte [!UICONTROL Co-op Device Graph] oder von Drittanbietern wählen, arbeiten Sie mit einem externen Gerätediagramm. Siehe [Geräteoptionen](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

 

**Was sind einige häufige Anwendungsfälle für die Verwendung eines externen Gerätediagramms in einem[!UICONTROL Profile Merge Rule]?**

Das Hauptziel der Verwendung eines Gerätediagramms in einem [!UICONTROL Profile Merge Rule] besteht darin, mehrere Geräte einer einzelnen Person oder eines einzelnen Haushalts für ein bestimmtes Segment zu bewerten und zu qualifizieren. Das Segment selbst kann mehrere Anwendungen haben, z. B. zum Targeting einer Audience von Potenzieller Kunden mit einer Anzeige, die von einem DSP bereitgestellt wird, oder zum Personalisieren des Onsite-Erlebnisses eines Kunden über eine Onsite-Personalisierungsplattform. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

 

**Bietet Audience Manager globale Unterstützung für externe Gerätediagramme?**

Nein. Diagramme für externe Geräte sind nur in den USA und Kanada verfügbar.

 

**Wie oft werden[!DNL Audience Manager]externe Gerätediagrammdaten aktualisiert?**

Einmal pro Woche.

 

## Gerätediagramme und Regeln zum Zusammenführen von Profilen {#device-graph-profile-merge-rules}

**Wie wird[!DNL Audience Manager]ein Gerätediagramm verwendet?**

Gerätediagramme werden [!DNL Audience Manager]als Konfigurationsoptionen angezeigt, wenn Sie eine Profil Merge Rule [erstellen](../features/profile-merge-rules/merge-rules-start.md). Diese Gerätegrafiken [!UICONTROL Profile Merge Rules]unterstützen [!DNL Audience Manager]Folgendes:

* Zusammenführen mehrerer Profil Dadurch wird eine einzige Übermenge von Eigenschaften erstellt.
* Bewerten Sie die Eigenschaftenübersetzung für die Segmentqualifizierung (anstatt jedes Profil einzeln zu bewerten).
* Hinzufügen qualifizierte Geräte für verfügbare Segmente.

 

**Wie viele[!UICONTROL Profile Merge Rules]kann ich erstellen?**

Derzeit können Sie maximal 4 [!UICONTROL Profile Merge Rules]erstellen. Die vierte Profil Merge Rule ([!UICONTROL All Cross-Device Profiles]) steht nur Kunden zur Verfügung, die das [!UICONTROL People-Based Destinations] Add-On erwerben.

 

**Wie viele Geräte-Profil werden[!DNL Audience Manager]zusammengeführt und gelesen, wenn ein Gerätediagramm in einem[!UICONTROL Profile Merge Rule]verwendet wird?**

Wenn Sie ein Profil für ein Segment mit einem [!UICONTROL Profile Merge Rule]auswählen, führt Audience Manager das aktuelle Gerätediagramm zusammen und liest es sowie maximal 99 weitere Profil, die mit der ausgewählten Gerätediagrammoption verknüpft sind.

 

**Welche Geräte eignen sich für ein Segment, wenn ein Gerätediagramm in einem[!UICONTROL Profile Merge Rule]verwendet wird?**

Die Geräte [!DNL Audience Manager] zusammenführen und lesen sind dieselben Geräte, die für ein Segment qualifiziert sind.

 

**Wo können Segmente[!DNL Audience Manager]gesendet werden, die von einem[!UICONTROL Profile Merge Rule]Gerät, das ein Diagramm verwendet, qualifiziert wurden?**

[!DNL Audience Manager] kann Segmente in Batch-Dateien oder in Echtzeit an ein Ziel senden.

 

## Segmente, Gerätediagramme und Regeln zum Zusammenführen von Profilen {#segments-device-graphs-rules}

**Wie wird die Segmentierung eines Geräts[!DNL Audience Manager]aufgehoben, wenn es nicht mehr für ein Segment mit einem[!UICONTROL Profile Merge Rule]Gerätediagramm qualifiziert ist?**

Audience Manager führt bei der Segmentauswertung bis zu 100 Geräte mit einem [!UICONTROL Profile Merge Rule] Gerätediagramm zusammen. Wenn das Segmentsignal ausgegeben wird, werden das aktuelle Gerät und bis zu 99 zusätzliche Geräte aus dem Segment im Ziel entfernt. Weitere Informationen zur Aufhebung der Segmentierung finden Sie unter [Profil Merge Rules und Device Un-Segmentation Processes](../features/profile-merge-rules/merge-rule-unsegment.md).

 

**Wenn ein Ziel Geräte aufheben kann, werden Geräte aus Segmenten entfernt,[!UICONTROL Profile Merge Rules]die ein Gerätediagramm verwenden?**

Ja. Siehe die Erklärung oben.

 

**Wenn ich ein Segment mit einem[!UICONTROL Profile Merge Rule]Segment aufbaue, das ein Gerätediagramm verwendet und das Segment sowohl Echtzeitdaten als auch Daten an Bord verwendet, wird mein Segment aktualisiert, wenn sich die Daten an Bord ändern?**

Ja.

 

**Sind in Segmentgrößenschätzungen Geräte enthalten, die für ein Segment auf der Grundlage von Verbindungen infrage kommen, die von einer Gerätediagrammoption bereitgestellt[!UICONTROL Profile Merge Rule]werden?**

Nein. Siehe Definitionen für [!UICONTROL Estimated Real-Time Population] und [!UICONTROL Estimated Total Population] in [Eigenschaften- und Segmentpopulationsdaten im Segmentaufbau](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html).

 

**Sind Geräte[!UICONTROL Addressable Audiences]enthalten, die für ein Segment auf der Grundlage von Verbindungen qualifiziert sind, die von einem[!UICONTROL Profile Merge Rule]Gerät bereitgestellt werden, das eine Gerätediagrammoption verwendet?**

Ja.

 

**Wenn ein Segment eine[!UICONTROL Profile Merge Rule]mit verwendet[!UICONTROL No Cross-Device Profile]und die Eigenschaften, die für das Segment qualifizierende Geräte sind, nur auf dem geräteübergreifenden Profil gespeichert werden, wird dann die Gesamtpopulation des Segments 0 betragen?**

Ja. Audience Manager zählt nicht die Eigenschaften, die im geräteübergreifenden Profil in der Segmentbewertung gespeichert sind, wenn die Profil-Merge-Regel auf [!UICONTROL No Cross-Device Profile]eingestellt ist.

 

## Eigenschafts-, Geräte- und Profil-Zusammenführungsregeln {#trait-freq-device-rules}

**Wie[!DNL Audience Manager]berechnet man die Häufigkeit von Eigenschaften mit einem[!UICONTROL Profile Merge Rule]Gerätediagramm?**

Die Häufigkeit der Eigenschaften wird durch die Summe der Anzahl der Qualifikationen für eine bestimmte Eigenschaft über mehrere Geräte hinweg definiert. Sehen Sie sich den folgenden Anwendungsfall an, um Ihnen zu helfen, dies zu verstehen.

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
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">Geräte A und B werden durch ein Gerätediagramm verknüpft. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">Sie haben eine <span class="wintitle"> Profil Merge Rule</span> , die eine Gerätediagrammoption verwendet. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Ein einzelnes Segment (Segment 1), das aus einer einzelnen Eigenschaft besteht (Eigenschaft 1), wobei Eigenschaft 1 eine Frequenz von 8 hat. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Aktionen</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> liest und führt die Profil für Geräte A und B zusammen. Daraus ergibt sich Folgendes: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Gerät A hat sich für Eigenschaft 1 dreimal qualifiziert. Für Eigenschaft 1 beträgt die Häufigkeit 3. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Gerät B ist fünfmal für Eigenschaft qualifiziert. Es hat eine Frequenz von 5 für Trait 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> fasst die Häufigkeit für Eigenschaft 1 zusammen und verwendet 8 (3 + 5 = 8), um die Segmentqualifizierung zu entscheiden. Geräte A und B sind für Segment 1 qualifiziert, da die Häufigkeit 8 beträgt. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Berichte, Gerätediagramme und Regeln zum Zusammenführen von Profilen {#reports-device-graphs-rules}

**Kann ich die Anzahl der Geräte sehen, die mit einem[!UICONTROL Profile Merge Rule]Gerätediagramm erreicht werden können?**

Ja. Berichte geben Daten auf der [!UICONTROL Profile Merge Rule] Ebene zurück. Die Berichtsdaten werden täglich aktualisiert. Die Daten basieren auf den Geräten in Ihrem Konto, nicht auf den Geräten, die mit einem Gerätediagramm verknüpft sind. Siehe [Berichtsmetriken für Profil-Zusammenführungsregeln](../features/profile-merge-rules/profile-link-metrics.md).

 

**Kann ich die Anzahl der für ein bestimmtes Segment qualifizierten Geräte in *Echtzeit*mit[!UICONTROL Profile Merge Rules]einem Gerätediagramm sehen?**

Ja. Die Echtzeit-Populationsmetrik erfasst Segmentqualifikationen für das aktuelle Gerät (das in Echtzeit gesehen wird) unter Verwendung der Profil aller Geräte, die mit einem Gerätediagramm verknüpft sind.

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
   <td colname="col2"> <p>Angenommen, wir haben: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segment 1 basiert auf diesen Eigenschaften und der Qualifikationslogik: Segment 1 = Eigenschaft A und Eigenschaft B und Eigenschaft C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 Geräte-Profil: Gerät 1 (aktuelles Gerät), Gerät 2 (Gerätediagramm), Gerät 3 (Gerätediagramm). </li> 
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
   <td colname="col2"> <p>Bei den vorherigen Elementen ist die Gesamtpopulation für Segment 1 eins. </p> <p>In diesem Fall verwendet die <span class="wintitle"> Profil Merge Rule</span> alle Geräte und deren Eigenschaften, um die Segmentqualifizierung zu bestimmen. Das bedeutet, dass die Geräte 1, 2 und 3 für Segment 1 qualifiziert sind. Wie oben erwähnt, wird jedoch nur Gerät 1 in der Segmentpopulation in Echtzeit berücksichtigt. Dies liegt daran, </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Gerät 1 ist das aktuelle Gerät, das mit dem Audience Manager <span class="wintitle"> Data Collection Server</span> (<span class="wintitle"> DCS</span>) in Echtzeit interagiert. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Die Geräte 2 und 3 werden mit Gerät 1 durch ein Gerätediagramm verknüpft, sie interagieren jedoch nicht mit dem DCS gleichzeitig mit Gerät 1. </li> 
     </ul> </p> <p>Dementsprechend werden die Geräte 2 und 3 nicht in die Populationsmetrik für Segmente in Echtzeit einbezogen. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Kann ich die Gesamtanzahl der Geräte sehen, die für ein bestimmtes Segment mit einem[!UICONTROL Profile Merge Rule]Gerätediagramm qualifiziert sind?**

Ja. Die Populationsmetrik für das gesamte Segment umfasst die zusätzlichen Geräte, die sich für ein Segment auf der Grundlage der Verbindungen eines Gerätediagramms qualifiziert haben.

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
   <td colname="col2"> <p>Angenommen, wir haben: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segment 1 basiert auf diesen Eigenschaften und der Qualifikationslogik: Segment 1 = Eigenschaft A und Eigenschaft B und Eigenschaft C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 Geräte-Profil: Gerät 1 (aktuelles Gerät), Gerät 2 (Gerätediagramm), Gerät 3 (Gerätediagramm). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Verbände</b> </p> </td> 
   <td colname="col2"> <p>Jede verfügbare Eigenschaft ist mit einem Gerät verknüpft: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Gerät 1: Eigenschaft A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Gerät 2: Eigenschaft B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Gerät 3: Eigenschaft C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Ergebnisse</b> </p> </td> 
   <td colname="col2"> <p>Angesichts der vorherigen Elemente beträgt die Gesamtpopulation für Segment 1 drei (3). </p> <p>In diesem Fall verwendet die <span class="wintitle"> Profil Merge Rule</span> alle Geräte und deren Eigenschaften, um die Segmentqualifizierung zu bestimmen. Das bedeutet, dass die Geräte 1, 2 und 3 für Segment 1 qualifiziert sind und alle drei in der Gesamtpopulation enthalten sind. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Sind Geräte, die für ein Segment mit einem Gerätediagramm in[!UICONTROL Profile Merge Rule]den[!UICONTROL Interactive]Berichten, Berichten und[!UICONTROL Overlap][!UICONTROL Audience Optimization]Berichten qualifiziert sind?**

Nein.

**Warum sehe ich nach dem 16. März 2020 bei Segmentexporten nach Adobe Campaign eine Segmentpopulation von Null?**

Ende 2019 haben wir eine Reihe von Profil Merge Rules Erweiterungen veröffentlicht, um die Genauigkeit von Batch-Dateien zu verbessern, die mit geräteübergreifenden IDs generiert wurden. Diese Verbesserungen werden in Ihrer Audience Manager-Instanz ab Montag, dem 16. März 2020 strikt berücksichtigt. Segmente, die einem Ziel mit geräteübergreifenden IDs zugeordnet sind, produzieren daher in einigen Profil Merge Rules Konfigurationen keine Exporte mehr.

Um die richtige Integration zwischen Ihrer Audience Manager-Instanz und Zielen mithilfe geräteübergreifender IDs, z. B. Adobe Campaign, sicherzustellen, stellen Sie sicher, dass folgende Anforderungen erfüllt sind:

1. Überprüfen Sie die Segmentzusammenführungsregel, die von den Segmenten verwendet wird, die Ihrem Adobe Campaign Deklarierte ID-Ziel zugeordnet sind. Die Profil Merge-Regel muss die [!UICONTROL Last Authenticated Profile] Option verwenden, damit alle authentifizierten Profil in die Exporte einbezogen werden können. Wenn Ihre Profil Merge Rule eine andere Option verwendet, wechseln Sie zu [!UICONTROL Last Authenticated Profile].
2. Wählen Sie in den Einstellungen für die Profil-Zusammenführungsregel die Datenquelle für das Adobe Campaign Deklariert aus.

>[!NOTE]
>
> Für Kunden, die sich in dieser Situation befinden, wurde die Profil Merge Rule-Beschränkung um 1 erhöht, sodass Sie eine dedizierte Profil-Merge-Regel für die Segmente erstellen können, die dem Adobe Campaign Deklarierte ID-Ziel zugeordnet sind, ohne die Profil Merge-Regeln für andere Anwendungsfälle zu ändern.

>[!MORELIKETHIS]
>
>* [Profillink](../features/profile-merge-rules/profile-link-use-case.md)

