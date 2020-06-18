---
description: Mit Profil Merge Rules erhalten Sie die Kontrolle über die für die Segmentierung verwendeten Datensätze und können eine Zielgruppe auf mehreren Geräten durchführen.
seo-description: Mit Profil Merge Rules erhalten Sie die Kontrolle über die für die Segmentierung verwendeten Datensätze und können eine Zielgruppe auf mehreren Geräten durchführen.
seo-title: Übersicht über Profil Merge Rules
solution: Audience Manager
title: Übersicht über Profil Merge Rules
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 2%

---


# Übersicht über Profil Merge Rules {#profile-merge-rules-overview}

Mit [!UICONTROL Profile Merge Rules] dieser Funktion können Sie steuern, welche Datensätze für die Segmentierung verwendet werden, und Benutzer auf mehreren Geräten präzise Zielgruppen vornehmen.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Datenerfassung und Targeting mit anonymen und authentifizierten Profilen {#data-collection-targeting}

Normalerweise basieren die Segmentierung und das Targeting von Audiencen auf Daten, die von allen Benutzern auf einem Gerät erfasst werden. Die Datenerfassung und das Targeting auf der Grundlage von Daten auf Geräteebene haben einige Nachteile. Beispielsweise können Sie nicht zwischen mehreren Benutzern unterscheiden, die ein Gerät gemeinsam verwenden, oder Benutzer mit einer genauen Zielgruppe über mehrere Geräte hinweg. Die gerätezentrierte Datenerfassung reicht nicht mehr für Kampagnen des digitalen Marketings oder geräteübergreifendes Targeting aus.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] Die Art und Weise, wie Daten und Segmente für Benutzer zum Targeting erfasst werden, wird grundlegend geändert. [!DNL Audience Manager] Damit können Sie mit zwei verschiedenen Typen von Profilen arbeiten, einem Profil und einem [authentifizierten Profil](../../reference/visitor-authentication-states.md).

<table id="table_CE98C0E32A964B27804736A896233869"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Profil </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Gerät Profil </td> 
   <td colname="col2"> <p>Ein Profil eines Geräts ist an eine ID für ein bestimmtes Gerät, z. B. eine Cookie-ID oder eine Mobilgerät-ID, gebunden. Zu diesem Dienst gehören: </p> <p>
     <ul id="ul_0420875DE65E44FFAC76E0DD205CFEC4"> 
      <li id="li_044AD85C644A41FB8EF48164BAC0CE34">Regelbasierte Eigenschaften, die realisiert werden, wenn ein Benutzer nicht authentifiziert ist. </li> 
      <li id="li_984D9790A6984139AFCFC2DFE4DF1BFC">Integrierte Eigenschaften, die mit einer Geräte-ID verknüpft sind, z. B. Cookie-basierte Daten von Drittanbietern. </li>
     </ul> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> Authentifiziertes Profil </td> 
   <td colname="col2"> <p>Das authentifizierte Profil ist an eine Benutzer-ID gebunden, die weitergegeben wird, wenn sich eine Person bei Ihrer Site anmeldet. Zu diesem Dienst gehören </p>
    <ul id="ul_18319CAA875148DBAE095134D42637B3"> 
     <li id="li_E24BD33E049849E5A594B0750F530475">Regelbasierte Eigenschaften, die auf allen Geräten erfasst werden, wenn ein Benutzer authentifiziert wird. </li>
     <li id="li_531AC9E0EC9D45108457FEC8E8D4E66C">Eigenschaften, die mit einer mit derselben Benutzer-ID verknüpften Offlinedatei integriert sind. </li>
    </ul> </td>
  </tr>
 </tbody>
</table>

Diese verschiedenen Profil steuern die Daten, die Sie für die Segmentierung verwenden können. Mit einem [authentifizierten Profil](../../reference/visitor-authentication-states.md)können Sie beispielsweise für einen Benutzer genaue Segmente erstellen, die auf Daten von mehreren Geräten basieren. Dies bedeutet, dass Sie Kunden auf mehreren Geräten eine einheitliche Markendarstellung bieten können. [!DNL Audience Manager] Dies wird erreicht, indem die Zuordnung der verschiedenen Geräte, die eine Person für ihre Online-Aktivitäten verwendet, zu ihrem [authentifizierten Profil](../../reference/visitor-authentication-states.md)gespeichert wird. Diese Zuordnungen werden als &quot; [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Vorteile {#advantages}

Mit [!UICONTROL Profile Merge Rules] der folgenden Funktion:

* Target-Benutzer basierend auf [authentifiziertem Profil](../../reference/visitor-authentication-states.md), anonymen Profilen oder Kombinationen aus beidem.
* Target eines bestimmten Kunden auf allen Geräten.
* Erstellen Sie ein Gerätediagramm basierend auf deterministischen Daten.
* Feinabstimmung der Daten in Ihren Segmenten auf Grundlage verschiedener Profil.
* Erhalten Sie weitere Einblicke in Ihre Audience.
