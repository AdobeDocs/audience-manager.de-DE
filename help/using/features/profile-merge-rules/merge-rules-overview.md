---
description: Mit Regeln zur Profilzusammenführung können Sie die für die Segmentierung verwendeten Datensätze steuern und eine Person auf mehreren Geräten präzise ansprechen.
seo-description: Mit Regeln zur Profilzusammenführung können Sie die für die Segmentierung verwendeten Datensätze steuern und eine Person auf mehreren Geräten präzise ansprechen.
seo-title: Übersicht über die Profilzusammenführung
solution: Audience Manager
title: Übersicht über die Profilzusammenführung
uuid: 9 e 7988 cc -9145-432 b -840 a -54 fbd 6657 b 3 b
translation-type: tm+mt
source-git-commit: f42267d3acf2570fc87d50c4c4e65826902d9e55

---


# Profile Merge Rules Overview {#profile-merge-rules-overview}

With [!UICONTROL Profile Merge Rules] you get control over the data sets used for segmentation and can target a person accurately across multiple devices.

## Data collection and targeting with anonymous and authenticated profiles {#data-collection-targeting}

In der Regel basieren die Zielgruppensegmentierung und das Targeting auf Daten, die von allen Benutzern auf einem Gerät erfasst werden. Die Datenerfassung und das Targeting auf Geräteebene haben einige Nachteile. Sie können beispielsweise nicht zwischen mehreren Benutzern unterscheiden, die ein Gerät teilen oder die Benutzer auf mehreren Geräten exakt ansprechen. Die gerätezentrierte Datenerfassung reicht nicht mehr für digitale Marketingkampagnen oder geräteübergreifende Targeting aus.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] Im Wesentlichen ändert, wie [!DNL Audience Manager] Daten und Segmente für das Targeting erfasst werden. Sie können mit zwei verschiedenen Profiltypen, einem Geräteprofil und einem authentifizierten Profil arbeiten.

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Profiltyp </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Gerät Profil </td> 
   <td colname="col2"> <p>Ein Geräteprofil ist für ein bestimmtes Gerät, wie z. B. eine Cookie-ID oder eine Mobilgeräte-ID, an eine ID gebunden. Zu diesem Dienst gehören: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">Regelbasierte Eigenschaften, wenn ein Benutzer nicht authentifiziert wird. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Onboarded-Eigenschaften, die mit einer Geräte-ID, wie Cookie-basierten Drittanbieterdaten, verknüpft sind. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Authentifizierungsprofil </td> 
   <td colname="col2"> <p>Das authentifizierte Profil ist an eine Benutzer-ID gebunden, die weitergegeben wird, wenn sich eine Person bei Ihrer Site anmeldet. Zu diesem Dienst gehören </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Regelbasierte Eigenschaften, die auf Gerätegeräten erfasst werden, wenn ein Benutzer authentifiziert wird. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Onboarded-Eigenschaften in einer Offline-Datei, die mit derselben Benutzer-ID verknüpft ist. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Diese verschiedenen Profile steuern die Daten, die Sie zur Segmentierung verwenden können. Mit einem authentifizierten Profil können Sie beispielsweise präzise Segmente auf Grundlage von Daten aus mehreren Geräten für eine einzelne Person erstellen. Das bedeutet, dass Sie Kunden auf mehreren Geräten ein einheitliches Markenerlebnis bieten können. Additionally, cross-device authentication allows [!DNL Audience Manager] to map the different platforms a person uses for their online activities. [!UICONTROL Profile Link Device Graph]Dies wird als ".

![](assets/authenticated2.png)

## Vorteile {#advantages}

[!UICONTROL Profile Merge Rules] Mit Ihnen können Sie:

* Geben Sie Benutzer basierend auf authentifizierten Profilen, anonymen Profilen oder Kombinationen beider Benutzer an.
* Targeting eines bestimmten Kunden auf allen ihren Geräten
* Erstellen Sie ein Gerätediagramm basierend auf deterministischen Daten.
* Feinabstimmung der Daten in Ihren Segmenten basierend auf verschiedenen Profilen.
* Gewinnen Sie zusätzliche Einblicke in Ihre Zielgruppe.

## Erste Schritte {#getting-started}

See the following sections and the [FAQ](../../faq/faq-profile-merge.md) for more information about [!UICONTROL Profile Merge Rules].

* [Erste Schritte mit Profilzusammenführungsregeln](/help/using/features/profile-merge-rules/merge-rules-start.md)
* [Dashboard für Profilzusammenführung](/help/using/features/profile-merge-rules/merge-rules-dashboard.md)
* [Regeloptionen für Profilzusammenführung definiert](/help/using/features/profile-merge-rules/merge-rule-definitions.md)
* [Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung](/help/using/features/profile-merge-rules/merge-rule-targeting-options.md)
* [Anwendungsbeispiele für Gerätediagramm-Diagramm](/help/using/features/profile-merge-rules/profile-link-use-case.md)
* [Anwendungsbeispiele für Diagramme externer Geräte](/help/using/features/profile-merge-rules/external-graph-use-cases.md)
* [Berichtsmetriken für Regeln zur Profilzusammenführung](/help/using/features/profile-merge-rules/profile-link-metrics.md)
* [Regeln für die Profilzusammenführung und das Aufheben der Segmentierung von Geräten](/help/using/features/profile-merge-rules/merge-rule-unsegment.md)
* [Sofortige geräteübergreifende Unterdrückung](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md)
* [Wichtige Überlegungen zu Profilzusammenführungsregeln mit Gerätediagrammen](/help/using/features/profile-merge-rules/considerations-pmr-device-graph.md)
