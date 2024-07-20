---
description: Mit den Optionen für Zusammenführungsregeln können Sie den Datentyp steuern, den Audience Manager für die Segmentierung verwendet. Eine Zusammenführungsregel kann Geräteprofile enthalten, die vom Profillink-Gerätediagramm zugeordnet werden, und/oder andere, in Audience Manager integrierte Gerätediagramm-Drittanbieter. Sie können maximal 4 Profilzusammenführungsrichtlinien erstellen.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Definierte Optionen für Profilzusammenführungsregeln
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---

# [!UICONTROL Profile Merge Rules] Definierte Optionen {#profile-merge-rule-options-defined}

Mit den Optionen [!UICONTROL profile merge rule] können Sie den Datentyp steuern, den [!DNL Audience Manager] für die Segmentierung verwendet. Ein [!UICONTROL profile merge rule] kann Geräteprofile enthalten, die vom [!UICONTROL Profile Link] -Gerätediagramm und/oder anderen, mit [!DNL Audience Manager] integrierten Gerätediagramm-Anbietern von Drittanbietern zugeordnet werden. Sie können maximal 4 [!UICONTROL Profile Merge Rules] erstellen. Die vierte [!UICONTROL Profile Merge Rule] ist ausschließlich für Kunden verfügbar, die das [!UICONTROL People-Based Destinations]-Add-on erworben haben.

Sie erstellen eine &quot;[!UICONTROL Profile Merge Rule]&quot;, indem Sie eine Auswahl aus den unten beschriebenen Optionen in &quot;[!UICONTROL Profile Merge Rule Setup]&quot;treffen.

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Optionsübersicht {#overview}

[!UICONTROL Profile Merge Rules] ermöglicht eine Reihe von Regelkombinationen, die jeweils auf bestimmte Anwendungsfälle ausgerichtet sind. Die nachstehende Tabelle beschreibt ausführlich, wann die einzelnen Regelkombinationen zu verwenden sind.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Verfügbarkeit | Testtyp | [!UICONTROL Audience Lab] Unterstützung | Nutzungsszenarios |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Alle Kunden | Echtzeit und Batch | Ja | [Geräte-Targeting](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Alle Kunden | Echtzeit und Batch | Nein | [ Erweitertes Geräte-Targeting](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Alle Kunden | Nur in Echtzeit | Nein | [Freigegebenes Geräte-Targeting](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Alle Kunden | Echtzeit und Batch | Ja | [Online-/Offline-Targeting](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Alle Kunden | Echtzeit und Batch | Ja | [Geräteübergreifendes Targeting](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Alle Kunden | Echtzeit und Batch | Nein | [Erweitertes geräteübergreifendes Targeting](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | nicht angegeben | Ausschließlich Kunden mit [personenbasierten Zielen](../destinations/people-based-destinations-overview.md) | Nur Batch | Nein | [Targeting für personenbasierte Ziele](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Auswertung {#segment-evaluation}

Abhängig von Ihrer [!UICONTROL Profile Merge Rules] -Konfiguration kann [!DNL Audience Manager] die [!UICONTROL segment]-Bewertung in Echtzeit, im Batch-Modus oder beidem durchführen.

* Für die Echtzeit-Bewertung von [!UICONTROL segment] ist die [!DNL DCS] erforderlich, damit Besucher in Echtzeit auf Ihre digitalen Eigenschaften zugreifen und sich für die [!UICONTROL segment] qualifizieren können.
* Die Batch [!UICONTROL segment]-Auswertung wird mit dem zuvor qualifizierten [!UICONTROL traits] durchgeführt.
* [!UICONTROL Profile Merge Rules], die sowohl die Echtzeit- als auch die Batch-Auswertung [!UICONTROL segment] unterstützen, kombinieren die Echtzeit-Besucheraktivität mit der zuvor qualifizierten [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Berichtslatenz {#reporting-latency}

Die Echtzeit-Bewertung von [!UICONTROL segment] spiegelt sich sofort in den [!UICONTROL Profile Merge Rules] -Berichten wider.

Die Batch-Auswertung [!UICONTROL segment] kann bis zu 24 Stunden dauern, bis sie in den Berichten für die [Profilzusammenführungsrichtlinien](profile-link-metrics.md) angezeigt wird.

## [!UICONTROL Cross-Device Options] {#auth-options}

Mit dem [!UICONTROL Cross-Device Options] können Sie authentifizierte und nicht authentifizierte Benutzer auswählen und ihr geräteübergreifendes Profil für die Segmentierung nutzen. Diese Optionen helfen Ihnen dabei, bestimmte Benutzer auf einem gemeinsam genutzten Gerät zu identifizieren und zu erreichen. Weitere Informationen zu anonymen und authentifizierten Benutzern finden Sie unter [Authentifizierungsstatus von Besuchern in Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Geräteübergreifende Option </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Kein geräteübergreifendes Profil</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, keine Daten zu verwenden, die von authentifizierten Benutzern erfasst wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktuelle authentifizierte Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, Daten zu lesen und in das authentifizierte Profil zu schreiben, wenn sich ein Besucher bei Ihrer Site angemeldet hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Letzte authentifizierte Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, Daten aus dem authentifizierten Profil des Benutzers zu lesen, der sich zuletzt auf dem Gerät angemeldet hat. </p> <p>Wenn diese Option aktiviert ist, schreibt <span class="keyword"> Audience Manager</span> keine neuen Eigenschaftsdaten in das authentifizierte Profil, wenn der Benutzer anonym ist. Bei der Authentifizierung werden neue Eigenschaftsdaten in das authentifizierte Profil des Benutzers geschrieben. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Alle geräteübergreifenden Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Weist Audience Manager an, Daten aus allen geräteübergreifenden Profilen zu lesen, unabhängig vom Authentifizierungsstatus. Diese Option steht nur Audience Manager zur Verfügung, die das Add-on "People-Based Destinations"erworben haben.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

Die [!UICONTROL Cross-Device Profile Options] listet Ihre [!UICONTROL cross-device data sources] auf. Diese Optionen verwenden die Namen, die Sie beim Erstellen einer [!UICONTROL cross-device] [!UICONTROL data source] angegeben haben (siehe [Erstellen einer geräteübergreifenden Daten-Source](merge-rules-start.md#create-data-source)). Sie können bis zu 3 [!UICONTROL cross-device data sources] auswählen, um diese für jede Profilregel zu verwenden. Die [!UICONTROL Authenticated Profile Options] sind verfügbar, wenn Sie **[!UICONTROL Current Authenticated Profiles]** oder **[!UICONTROL Last Authenticated Profiles]** auswählen.

## [!UICONTROL Device Options] {#device-options}

Mit dem [!UICONTROL Device Options] können Sie den Typ von *`device profile`* auswählen, der von einem [!UICONTROL Profile Merge Rule] verwendet wird. Ein Geräteprofil wird aus [!UICONTROL traits] erstellt, das aus der anonymen Browsing-Aktivität erfasst wurde. Eine [!UICONTROL profile merge rule] enthält mindestens eine [!UICONTROL authenticated option] und eine [!UICONTROL device option].

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
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, die im anonymen Profil enthaltenen Eigenschaften nicht für die Segmentierung zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Geräteprofil</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, das anonyme Geräteprofil für die Segmentierung zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profil-Link-Gerätediagramm</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, die Profile vom aktuellen Gerät und bis zu 100 weitere Geräte zu lesen, von denen sich der Benutzer authentifiziert hat. Dieses Gerätediagramm basiert auf Ihren eigenen Erstanbieterdaten in <span class="keyword"> Audience Manager</span>. Es ist ideal für Kunden, die über ihre digitalen Eigenschaften hinweg über einen hohen Authentifizierungsgrad verfügen. Das Gerätediagramm <span class="wintitle"> Profil-Link</span> wird in Echtzeit aktualisiert. Diese Option ist verfügbar, wenn Sie <b><span class="uicontrol"> Aktuelles authentifiziertes Profil</span></b> oder <b><span class="uicontrol"> Letztes authentifiziertes Profil</span></b> auswählen. Bei Verwendung dieser Option können Sie nur ein einziges authentifiziertes Profil auswählen (<span class="keyword"> Audience Manager</span> graut die anderen automatisch aus). Siehe auch <a href="profile-link-use-case.md"> Anwendungsfälle für Profillinkgerät-Diagramme</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Gerätediagrammoptionen von Drittanbietern</b> (Personen und Haushalt) </p> </td>
   <td colname="col2"> <p>Mit diesen Optionen können Sie Zusammenführungsregeln basierend auf der Gerätediagrammtechnologie erstellen, die von einem Drittanbieter bereitgestellt wird. Ein Gerätediagramm von Drittanbietern bietet Folgendes: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Probabilistische und/oder deterministische Daten. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Daten auf Personen- oder Haushaltsebene. </li> 
     </ul> </p> <p>Um diese Optionen verwenden zu können, müssen Sie Kunde eines Gerätediagramms sein, das bereits mit <span class="keyword"> Audience Manager</span> integriert ist. Wenden Sie sich an Ihren Kundenbetreuer, um weitere Informationen zu erhalten oder zu beginnen. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Zielgruppensegmente, die basierend auf außerhalb von [!DNL Audience Manager] definierten Zusammenführungsregeln automatisch aus anderen [!DNL Experience Cloud] -Lösungen erstellt wurden, werden mit einem [!UICONTROL External Merge Policy] markiert. Siehe beispielsweise [Zielgruppenfreigabe zwischen Audience Manager und Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profilzusammenführungsregeln](../../faq/faq-profile-merge.md)
