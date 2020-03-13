---
description: Die Eigenschaftsqualifikation oder die Realisierung von Eigenschaften wird in Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Die nachstehende Tabelle enthält detaillierte Informationen zur Qualifikation der Eigenschaften.
keywords: trait qualification;trait realization;Unique Trait Realizations;UTR;Total Trait Population;TTP
seo-description: Die Eigenschaftsqualifikation oder die Realisierung von Eigenschaften wird in Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Die nachstehende Tabelle enthält detaillierte Informationen zur Qualifikation der Eigenschaften.
seo-title: Eigenschaftsqualifikationsreferenz
solution: Audience Manager
title: Eigenschaftsqualifikationsreferenz
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 2f8662aba70254e550bc15417463c3c06492a9d5

---


# Eigenschaftsqualifikationsreferenz {#trait-qualification-reference}

Die Eigenschaftsqualifikation oder die Realisierung von Eigenschaften wird in Audience Manager je nach Eigenschaftstyp unterschiedlich behandelt. Die nachstehende Tabelle enthält detaillierte Informationen zur Qualifikation der Eigenschaften.

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
   <td colname="col2"> <p>Die Qualifizierung von Eigenschaften erfolgt in Echtzeit, da Benutzer sich für eine Eigenschaft in ihrem Browser qualifizieren. Ihre Beginn qualifizieren sich ca. 4 Stunden nach <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> Erstellung der Eigenschaft</a> in der Benutzeroberfläche für eine regelbasierte Eigenschaft. </p> <p>Regelbasierte Eigenschaften ermöglichen Ihnen die Verwendung von <a href="../../features/segments/recency-and-frequency.md"> Neuigkeits- und Häufigkeitssteuerelementen</a> für die Begrenzung der Anzeigenfrequenz und andere Anwendungsfälle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integrierte Eigenschaften </p> </td> 
   <td colname="col2"> <p>Die Qualifizierung von Eigenschaften erfolgt nach der Verarbeitung einer eingehenden Datei, d. h., die eingehende Datei wird in Audience Manager <a href="../../faq/faq-inbound-data-ingestion.md"></a> importiert und dann erfolgt die Qualifizierung der Eigenschaften. Sie sollten etwa 4 Stunden nach dem Erstellen einer nicht integrierten Eigenschaft warten, bevor Sie eine eingehende Datei zur Verarbeitung hochladen.  </p> <p> Bei nicht an Bord befindlichen Eigenschaften beträgt die maximale Anzahl von Qualifikationen für ein Profil 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Algorithmische Eigenschaften </p> </td> 
   <td colname="col2"> <p>Bei algorithmischen Eigenschaften ist die maximale Anzahl von Qualifikationen für ein Profil 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ordnereigenschaften </p> </td> 
   <td colname="col2"> <p>Eine Ordnereigenschaft fasst die Eigenschaftsqualifikationen der darin enthaltenen Eigenschaften zusammen. </p> <p>Eigenschaften <a href="../../features/traits/about-folder-traits.md"> des Read-Ordners: Info</a> für weitere Informationen. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>Eigenschaften der aktiven Audience und von Datenquelle synchronisierte Eigenschaften </p> </td> 
   <td colname="col2"> <p>Die Eigenschaft " <span class="wintitle"> Aktive Audience</span> "enthält alle in Ihrem <span class="wintitle"> Audience Manager</span> -Konto verwalteten Geräte. </p> <p><span class="wintitle"> Mit Datenquelle synchronisierte Eigenschaften</span> verfolgen alle Benutzer, die mit einer Datenquelle verknüpft sind. </p> <p>Mehr über <a href="../../features/traits/client-activity-synced-audience-traits.md"> Eigenschaften von aktiver Audience und von Datenquelle synchronisierte Eigenschaften</a>. </p> </td>
  </tr>
 </tbody>
</table>

## Eindeutige Eigenschaften und Gesamtanzahl der Eigenschaften {#unique-trait-realizations}

![](assets/utr-ttp1.png)

Die **[!UICONTROL Unique Trait Realizations]** Anzahl der Besucher, die das Merkmal innerhalb verschiedener Zeiträume zu ihrem Profil hinzugefügt haben.

Die **[!UICONTROL Total Trait Population]** Anzahl der Besucher, die diese Eigenschaft auf ihrem Profil haben.

Stellen Sie sich die Zahlen so vor. In der obigen Abbildung aus der Ansicht [Eigenschaftendetails](../../features/traits/trait-details-page.md) steht 181 für die Anzahl der aktiven Geräte, die Ihre Eigenschaften gestern besucht haben. Der Wert [!UICONTROL Total Trait Population] von 1.595 stellt die Anzahl der Benutzer dar, die derzeit für diese Eigenschaft qualifiziert sind. Die [!UICONTROL Total Trait Population] Zahl zeigt die Gesamtanzahl der Benutzer an, die für die Segmentierung/das Targeting verwendet werden könnten. Normalerweise bleiben Benutzer 120 Tage lang Teil einer Eigenschaft.

Da wir zwei verschiedene Rechenaufgaben ausführen, um die zwei Populationen zu berechnen, liegt die [!UICONTROL Total Trait Population] immer um 24 Stunden hinter der [!UICONTROL Unique Trait Realizations] . Im Diagramm oben sehen Sie 175 [!UICONTROL Unique Trait Realizations] und eine [!UICONTROL Total Trait Population] von 6 für den 11. Februar. Die 175 Profil werden am [!UICONTROL Total Trait Population] darauffolgenden Tag zum hinzugefügt.

Um den Punkt weiter nach Hause zu bringen, wenn man eine Spitze von 10.000 Besuchern im Moment erlebt, würden sie in der Zukunft erscheinen [!UICONTROL Unique Trait Realizations], aber nur 24 Stunden später in der [!UICONTROL Total Trait Population].

## Qualifikationslimit für Eigenschaften {#trait-qualification-limit}

Für jedes Profil gelten maximal 150.000 Eigenschaftsqualifikationen, unabhängig davon, ob es sich um ein authentifiziertes Profil ( [DPUUID](../../reference/ids-in-aam.md)) oder eine Geräte-ID ( [UUID](../../reference/ids-in-aam.md)) handelt. Beachten Sie, dass die DPUUIDs zwar für eine bestimmte Instanz von eindeutig sind, [!DNL Audience Manager]dass UUIDs jedoch auf der [!DNL Audience Manager] Plattform freigegeben werden. Für [!UICONTROL UUID]uns wird bei der Speicherung von Eigenschaftsqualifikationen eine Fairness-Politik verhängt. Ein Algorithmus stellt sicher, dass für jede Instanz des [!UICONTROL UUID] Profils ein gleich hoher Anteil zur Verfügung steht [!DNL Audience Manager].
