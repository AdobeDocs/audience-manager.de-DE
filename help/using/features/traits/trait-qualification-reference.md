---
description: Die Eigenschaftsqualifikation oder die Eigenschaftsrealisierung wird in Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Die nachstehende Tabelle enthält detaillierte Informationen zur Qualifikation der Eigenschaften.
keywords: Eigenschaftsqualifikation;Realisierung von Eigenschaften;Individuelle Eigenschaften;UTR;Gesamtanzahl der Eigenschaften;TTP
seo-description: Die Eigenschaftsqualifikation oder die Eigenschaftsrealisierung wird in Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Die nachstehende Tabelle enthält detaillierte Informationen zur Qualifikation der Eigenschaften.
seo-title: Eigenschaftsqualifikationsreferenz
solution: Audience Manager
title: Eigenschaftsqualifikationsreferenz
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Eigenschaftsqualifikationsreferenz {#trait-qualification-reference}

Die Eigenschaftsqualifikation oder die Eigenschaftsrealisierung wird in Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Die nachstehende Tabelle enthält detaillierte Informationen zur Qualifikation der Eigenschaften.

## Eigenschaftsqualifikation nach Eigenschaftstyp {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Eigenschaftstyp </th> 
   <th colname="col2" class="entry"> Qualifikationskriterien </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Regelbasierte Eigenschaften </p> </td> 
   <td colname="col2"> <p>Die Qualifizierung von Eigenschaften erfolgt in Echtzeit, da Benutzer sich für eine Eigenschaft in ihrem Browser qualifizieren. Ihre Benutzer können sich etwa 4 Stunden nach <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> Erstellung der Eigenschaft</a> in der Benutzeroberfläche für eine regelbasierte Eigenschaft qualifizieren. </p> <p>Regelbasierte Eigenschaften ermöglichen Ihnen die Verwendung von <a href="../../features/segments/recency-and-frequency.md"> Neuigkeits- und Häufigkeitssteuerelementen</a> für die Begrenzung der Anzeigenfrequenz und andere Anwendungsfälle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integrierte Eigenschaften </p> </td> 
   <td colname="col2"> <p>Die Qualifizierung von Eigenschaften erfolgt nach der Verarbeitung einer eingehenden Datei, d. h., die eingehende Datei wird in Audience Manager<a href="../../faq/faq-inbound-data-ingestion.md"> </a> importiert und dann erfolgt die Qualifizierung der Eigenschaften. </p> <p> Bei nicht an Bord befindlichen Eigenschaften beträgt die maximale Anzahl an Qualifikationen für ein Benutzerprofil 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Algorithmische Eigenschaften </p> </td> 
   <td colname="col2"> <p>Bei algorithmischen Eigenschaften beträgt die maximale Anzahl an Qualifikationen für ein Benutzerprofil 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ordnereigenschaften </p> </td> 
   <td colname="col2"> <p>Eine Ordnereigenschaft fasst die Eigenschaftsqualifikationen der darin enthaltenen Eigenschaften zusammen. </p> <p>Eigenschaften <a href="../../features/traits/about-folder-traits.md"> des Read-Ordners: Info</a> für weitere Informationen. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>Eigenschaften aktiver Zielgruppen und von Datenquelle synchronisierte Eigenschaften </p> </td> 
   <td colname="col2"> <p>Eine Eigenschaft <span class="wintitle"> Aktive Zielgruppe</span> enthält alle Geräte, die in Ihrem <span class="wintitle"> Audience Manager</span> -Konto verwaltet werden. </p> <p><span class="wintitle"> Mit Datenquelle synchronisierte Eigenschaften</span> verfolgen alle Benutzer, die mit einer Datenquelle verknüpft sind. </p> <p>Lesen Sie mehr über <a href="../../features/traits/client-activity-synced-audience-traits.md"> Aktive Zielgruppeneigenschaften und Datenquelle-synchronisierte Eigenschaften</a>. </p> </td>
  </tr>
 </tbody>
</table>

## Eindeutige Eigenschaften und Gesamtanzahl der Eigenschaften {#unique-trait-realizations}

![](assets/utr-ttp1.png)

Die **[!UICONTROL Unique Trait Realizations]** Anzahl der Besucher, die das Merkmal innerhalb verschiedener Zeiträume zu ihrem Profil hinzugefügt haben.

Die **[!UICONTROL Total Trait Population]** Anzahl der Besucher, die diese Eigenschaft in ihrem Profil haben.

Stellen Sie sich die Zahlen so vor. In der Abbildung oben zeigt die Ansicht [Eigenschaftendetails](../../features/traits/trait-details-page.md) 181 die Anzahl der aktiven Geräte an, die Ihre Eigenschaften gestern besucht haben. Der Wert [!UICONTROL Total Trait Population] von 1.595 stellt die Anzahl der Benutzer dar, die derzeit für diese Eigenschaft qualifiziert sind. Die [!UICONTROL Total Trait Population] Zahl zeigt die Gesamtanzahl der Benutzer an, die für die Segmentierung/das Targeting verwendet werden könnten. Normalerweise bleiben Benutzer 120 Tage lang Teil einer Eigenschaft.

Da wir zwei verschiedene Rechenaufgaben ausführen, um die zwei Populationen zu berechnen, liegt die [!UICONTROL Total Trait Population] immer um 24 Stunden hinter der [!UICONTROL Unique Trait Realizations] . Im Diagramm oben sehen Sie 175 [!UICONTROL Unique Trait Realizations] und eine [!UICONTROL Total Trait Population] von 6 für den 11. Februar. Die 175 Profile werden am folgenden Tag zum [!UICONTROL Total Trait Population] hinzugefügt.

Um den Punkt weiter nach Hause zu bringen, wenn Sie eine Spitze von 10.000 Besuchern im Moment erleben würden, würden sie morgen erscheinen [!UICONTROL Unique Trait Realizations], aber nur 24 Stunden später in der [!UICONTROL Total Trait Population].

## Qualifikationslimit für Eigenschaften {#trait-qualification-limit}

Für jedes Benutzerprofil gelten maximal 150.000 Eigenschaftsqualifikationen, unabhängig davon, ob es sich um ein authentifiziertes Profil ( [DPUUID](../../reference/ids-in-aam.md)) oder eine Geräte-ID ( [UUID](../../reference/ids-in-aam.md)) handelt. Beachten Sie, dass die DPUUIDs zwar für eine bestimmte Instanz von eindeutig sind, [!DNL Audience Manager]dass UUIDs jedoch auf der [!DNL Audience Manager] Plattform freigegeben werden. Für [!UICONTROL UUID]uns wird bei der Speicherung von Eigenschaftsqualifikationen eine Fairness-Politik vorgeschrieben. Ein Algorithmus stellt sicher, dass für jede Instanz des Profils ein gleich hoher Anteil des [!UICONTROL UUID] Profils zur Verfügung gestellt [!DNL Audience Manager]wird.
