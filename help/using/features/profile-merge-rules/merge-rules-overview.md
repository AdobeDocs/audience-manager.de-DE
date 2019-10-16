---
description: Mit den Regeln zur Profilzusammenführung erhalten Sie Kontrolle über die für die Segmentierung verwendeten Datensätze und können eine Person präzise auf mehreren Geräten ansprechen.
seo-description: Mit den Regeln zur Profilzusammenführung erhalten Sie Kontrolle über die für die Segmentierung verwendeten Datensätze und können eine Person präzise auf mehreren Geräten ansprechen.
seo-title: Übersicht über Regeln zum Profilzusammenführen
solution: Audience Manager
title: Übersicht über Regeln zum Profilzusammenführen
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Übersicht über Regeln zum Profilzusammenführen {#profile-merge-rules-overview}

Mit [!UICONTROL Profile Merge Rules] dieser Funktion können Sie steuern, welche Datensätze für die Segmentierung verwendet werden, und Benutzer präzise auf mehrere Geräte ausrichten.

>[!VIDEO](https://video.tv.adobe.com/v/28974?captions=ger)

## Datenerfassung und Targeting mit anonymen und authentifizierten Profilen {#data-collection-targeting}

Die Zielgruppensegmentierung und das Targeting basieren in der Regel auf Daten, die von allen Benutzern auf einem Gerät erfasst werden. Die Datenerfassung und das Targeting auf der Grundlage von Daten auf Geräteebene haben einige Nachteile. Sie können beispielsweise nicht zwischen mehreren Benutzern unterscheiden, die ein Gerät gemeinsam verwenden oder Benutzer auf mehreren Geräten genau ansprechen. Die gerätezentrierte Datenerfassung reicht nicht mehr für digitale Marketingkampagnen oder geräteübergreifendes Targeting aus.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] Die Art und Weise, wie Daten und Segmente für Benutzer zum Targeting erfasst werden, wird grundlegend geändert. [!DNL Audience Manager] Damit können Sie mit zwei verschiedenen Profiltypen, einem Geräteprofil und einem [authentifizierten Profil](../../reference/visitor-authentication-states.md)arbeiten.

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
   <td colname="col2"> <p>Ein Geräteprofil ist an eine ID für ein bestimmtes Gerät, z. B. eine Cookie-ID oder eine Mobilgerät-ID, gebunden. Zu diesem Dienst gehören: </p> <p>
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

Diese verschiedenen Profile steuern die Daten, die Sie für die Segmentierung verwenden können. Beispielsweise können Sie mit einem [authentifizierten Profil](../../reference/visitor-authentication-states.md)genaue Segmente erstellen, die auf Daten von mehreren Geräten für einen einzelnen Benutzer basieren. Dies bedeutet, dass Sie Kunden auf mehreren Geräten eine einheitliche Markendarstellung bieten können. Dazu speichert Audience Manager die Zuordnung der verschiedenen Geräte, die eine Person für ihre Online-Aktivitäten verwendet, zu ihrem [authentifizierten Profil](../../reference/visitor-authentication-states.md). Diese Zuordnungen werden als " [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Vorteile {#advantages}

Mit [!UICONTROL Profile Merge Rules] der folgenden Funktion:

* Targeting von Benutzern basierend auf [authentifiziertem Profil](../../reference/visitor-authentication-states.md), anonymen Profilen oder Kombinationen aus beiden.
* Targeting eines bestimmten Kunden auf allen Geräten.
* Erstellen Sie ein Gerätediagramm basierend auf deterministischen Daten.
* Feinabstimmung der Daten in Ihren Segmenten auf der Grundlage verschiedener Profile.
* Erhalten Sie weitere Einblicke in Ihre Zielgruppe.
