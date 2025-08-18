---
description: Mit den Optionen für Zusammenführungsregeln können Sie den Datentyp steuern, den Audience Manager für die Segmentierung verwendet. Eine Zusammenführungsregel kann Geräteprofile enthalten, die vom Profilverknüpfungs-Gerätediagramm zugeordnet sind, und/oder andere Drittanbieter-Gerätediagramm-Anbieter, die in Audience Manager integriert sind. Sie können maximal vier Profilzusammenführungsregeln erstellen.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Optionen für Profilzusammenführungsregeln definiert
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---

# [!UICONTROL Profile Merge Rules] Optionen definiert {#profile-merge-rule-options-defined}

Mit den [!UICONTROL profile merge rule] Optionen können Sie den Datentyp steuern, den [!DNL Audience Manager] für die Segmentierung verwendet. Ein [!UICONTROL profile merge rule] kann Geräteprofile enthalten, die vom [!UICONTROL Profile Link] Gerätediagramm zugeordnet sind, und/oder andere Drittanbieter von Gerätediagrammen, die mit [!DNL Audience Manager] integriert sind. Sie können maximal 4 [!UICONTROL Profile Merge Rules] erstellen. Die vierte [!UICONTROL Profile Merge Rule] steht nur Kunden zur Verfügung, die das [!UICONTROL People-Based Destinations]-Add-on erworben haben.

Sie erstellen ein [!UICONTROL Profile Merge Rule], indem Sie unter [!UICONTROL Profile Merge Rule Setup] eine Auswahl aus den unten beschriebenen Optionen treffen.

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Übersicht über [!UICONTROL Profile Merge Rule] {#overview}

[!UICONTROL Profile Merge Rules] ermöglichen eine Reihe von Regelkombinationen, die jeweils auf bestimmte Anwendungsfälle zugeschnitten sind. In der folgenden Tabelle finden Sie Einzelheiten dazu, wann die einzelnen Regelkombinationen verwendet werden sollten.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Verfügbarkeit | Auswertungstyp | [!UICONTROL Audience Lab] | Nutzungsszenarios |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Alle Kunden | Echtzeit und Batch | Ja | [Geräte-Targeting](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Alle Kunden | Echtzeit und Batch | Nein | [Erweitertes Geräte-Targeting](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Alle Kunden | Nur Echtzeit | Nein | [Freigegebenes Geräte-Targeting](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Alle Kunden | Echtzeit und Batch | Ja | [Online-/Offline-Targeting](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Alle Kunden | Echtzeit und Batch | Ja | [Geräteübergreifendes Targeting](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Alle Kunden | Echtzeit und Batch | Nein | [Erweitertes geräteübergreifendes Targeting](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | nicht angegeben | Exklusiv für [People-Based Destinations](../destinations/people-based-destinations-overview.md)-Kunden | Nur Batch | Nein | [Targeting für personenbasierte Ziele](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] {#segment-evaluation}

Abhängig von Ihrer [!UICONTROL Profile Merge Rules]-Konfiguration können [!DNL Audience Manager] die [!UICONTROL segment] in Echtzeit, im Batch oder in beiden durchführen.

* Für die Auswertung von [!UICONTROL segment] in Echtzeit muss der [!DNL DCS] sehen, wie Besucher in Echtzeit auf Ihre digitalen Eigenschaften zugreifen, um sich für die [!UICONTROL segment] zu qualifizieren.
* Die Batch-[!UICONTROL segment] wird anhand zuvor qualifizierter [!UICONTROL traits] durchgeführt.
* [!UICONTROL Profile Merge Rules], die sowohl die Echtzeit- als auch die Batch-[!UICONTROL segment] unterstützen, kombinieren die Echtzeit-Besucheraktivität mit zuvor qualifizierten [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Berichtslatenz {#reporting-latency}

Die [!UICONTROL segment] in Echtzeit spiegelt sich sofort in den [!UICONTROL Profile Merge Rules] wider.

Die [!UICONTROL segment] kann bis zu 24 Stunden dauern, bis sie in den Berichten [Profilzusammenführungsregeln“ angezeigt ](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

Mit dem [!UICONTROL Cross-Device Options] können Sie authentifizierte und nicht authentifizierte Benutzer auswählen und ihr geräteübergreifendes Profil für die Segmentierung nutzen. Diese Optionen helfen Ihnen, bestimmte Benutzende auf einem freigegebenen Gerät zu identifizieren und zu erreichen. Weitere Informationen zu anonymen und authentifizierten Benutzern finden Sie unter [Besucherauthentifizierungsstatus in Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Geräteübergreifende Option </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> kein geräteübergreifendes Profil</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager an</span> keine Daten zu verwenden, die von authentifizierten Benutzern erfasst wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> aktuellen authentifizierten Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager </span> an, Daten zu lesen und in das authentifizierte Profil zu schreiben, wenn sich ein Besucher bei Ihrer Site angemeldet hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> letzten authentifizierten Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Veranlasst <span class="keyword"> Audience Manager</span> Daten aus dem authentifizierten Profil des Benutzers zu lesen, der sich zuletzt auf dem Gerät angemeldet hat. </p> <p><span class="keyword"> Wenn diese Option aktiviert ist, </span> Audience Manager keine neuen Eigenschaftsdaten in das authentifizierte Profil, wenn der Benutzer anonym ist. Nach der Authentifizierung werden neue Eigenschaftsdaten in das authentifizierte Profil des Benutzers geschrieben. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> alle geräteübergreifenden Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Weist Audience Manager an, Daten aus allen geräteübergreifenden Profilen zu lesen, unabhängig vom Authentifizierungsstatus. Diese Option ist nur für Audience Manager-Kunden verfügbar, die das Add-on People-Based Destinations erworben haben.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

Die [!UICONTROL Cross-Device Profile Options] listet Ihre [!UICONTROL cross-device data sources] auf. Diese Optionen verwenden die Namen, die Sie beim Erstellen eines [!UICONTROL cross-device]-[!UICONTROL data source] angegeben haben (siehe [Erstellen eines geräteübergreifenden Daten-Source](merge-rules-start.md#create-data-source)). Sie können für jede Profilregel bis zu 3 [!UICONTROL cross-device data sources] auswählen. Die [!UICONTROL Authenticated Profile Options] sind verfügbar, wenn Sie **[!UICONTROL Current Authenticated Profiles]** oder **[!UICONTROL Last Authenticated Profiles]** auswählen.

## [!UICONTROL Device Options] {#device-options}

Mit der [!UICONTROL Device Options] können Sie den von einem *`device profile`* verwendeten [!UICONTROL Profile Merge Rule] auswählen. Ein Geräteprofil wird aus [!UICONTROL traits] erstellt, die aus der anonymen Browser-Aktivität erfasst wurden. Eine [!UICONTROL profile merge rule] umfasst mindestens eine [!UICONTROL authenticated option] und eine [!UICONTROL device option].

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Geräteoption </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Kein Geräteprofil</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager </span>, die im anonymen Profil enthaltenen Eigenschaften nicht für die Segmentierung zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Geräteprofil</span></b> </p> </td> 
   <td colname="col2"> <p>Veranlasst <span class="keyword"> Audience Manager</span> das anonyme Geräteprofil für die Segmentierung zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> des Profilverknüpfungsgeräts</span></b> </p> </td> 
   <td colname="col2"> <p>Veranlasst <span class="keyword"> Audience Manager</span> die Profile des aktuellen Geräts und von bis zu 100 anderen Geräten zu lesen, von denen sich der Benutzer authentifiziert hat. Dieses Gerätediagramm basiert auf Ihren eigenen First-Party-Daten in <span class="keyword"> Audience Manager</span>. Es ist ideal für Kunden, die über ein hohes Maß an Authentifizierung für ihre digitalen Eigenschaften verfügen. Das Gerätediagramm <span class="wintitle"> Profillink</span> wird in Echtzeit aktualisiert. Diese Option ist verfügbar, wenn Sie <b><span class="uicontrol"> Aktuelles authentifiziertes Profil oder </span></b> <b><span class="uicontrol"> Letztes authentifiziertes Profil </span></b>. Wenn Sie diese Option verwenden, können Sie nur ein einzelnes authentifiziertes Profil auswählen (<span class="keyword"> Audience Manager </span> die anderen automatisch ausgegraut). Siehe auch Anwendungsfälle <a href="profile-link-use-case.md"> Profilverknüpfung von Gerätediagrammen</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Diagrammoptionen für Drittanbieter-Geräte</b> (Person und Haushalt) </p> </td>
   <td colname="col2"> <p>Mit diesen Optionen können Sie Zusammenführungsregeln erstellen, die auf der von einem Drittanbieter bereitgestellten Gerätediagramm-Technologie basieren. Ein Gerätediagramm eines Drittanbieters bietet: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Wahrscheinliche und/oder deterministische Daten. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Daten auf Personen- oder Haushaltsebene. </li> 
     </ul> </p> <p>Um diese Optionen verwenden zu können, müssen Sie Kunde eines Gerätediagramms sein, das bereits in <span class="keyword"> Audience Manager integriert ist</span>. Wenden Sie sich an Ihren Account Manager, um weitere Informationen zu erhalten oder um zu beginnen. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Zielgruppensegmente, die automatisch auf der Grundlage von Zusammenführungsregeln, die außerhalb von [!DNL Experience Cloud] definiert wurden, aus anderen [!DNL Audience Manager]-Lösungen erstellt wurden, werden als mit einem [!UICONTROL External Merge Policy] gekennzeichnet. Ein Beispiel finden Sie unter [Zielgruppenfreigabe zwischen Audience Manager und Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profilzusammenführungsregeln](../../faq/faq-profile-merge.md)
