---
description: Mit den Optionen für die Zusammenführungsregel können Sie steuern, welcher Typ von Daten von Audience Manager für die Segmentierung verwendet wird. Eine Zusammenführungsregel kann Profil von Geräten enthalten, die vom Gerätediagramm "Profil Link", vom Adobe Experience Cloud Device Co-op und/oder anderen Geräteschreiberanbietern von Drittanbietern, die in Audience Manager integriert sind, zugeordnet werden. Sie können maximal 4 Profil Merge Rules erstellen.
seo-description: Mit den Optionen für die Zusammenführungsregel können Sie steuern, welcher Typ von Daten von Audience Manager für die Segmentierung verwendet wird. Eine Zusammenführungsregel kann Profil von Geräten enthalten, die vom Gerätediagramm "Profil Link", vom Adobe Experience Cloud Device Co-op und/oder anderen Geräteschreiberanbietern von Drittanbietern, die in Audience Manager integriert sind, zugeordnet werden. Sie können maximal 4 Profil Merge Rules erstellen.
seo-title: Für Profilzusammenführungsrichtlinien definierte Optionen
solution: Audience Manager
title: Für Profilzusammenführungsrichtlinien definierte Optionen
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 6%

---

# [!UICONTROL Profile Merge Rules] Definierte Optionen  {#profile-merge-rule-options-defined}

Mit den Optionen [!UICONTROL profile merge rule] können Sie den Datentyp [!DNL Audience Manager] für die Segmentierung steuern. Ein [!UICONTROL profile merge rule] kann Gerätediagramme enthalten, die vom [!UICONTROL Profile Link]-Gerätediagramm, dem [!UICONTROL Adobe Experience Cloud Device Co-op] und/oder anderen Geräteschreiberanbietern von Drittanbietern zugeordnet werden, die mit [!DNL Audience Manager] integriert sind. Sie können maximal 4 [!UICONTROL Profile Merge Rules] erstellen. Das vierte [!UICONTROL Profile Merge Rule] ist exklusiv für Kunden verfügbar, die das [!UICONTROL People-Based Destinations] Add-on gekauft haben.

Sie erstellen ein [!UICONTROL Profile Merge Rule], indem Sie eine Auswahl aus den unten beschriebenen Optionen treffen, in [!UICONTROL Profile Merge Rule Setup].

![Profil-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Optionsübersicht  {#overview}

[!UICONTROL Profile Merge Rules] Sie können eine Reihe von Regelkombinationen zulassen, von denen jede auf spezifische Anwendungsfälle ausgerichtet ist. Die nachstehende Tabelle beschreibt ausführlich, wann die einzelnen Regelkombinationen zu verwenden sind.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Verfügbarkeit | Bewertungstyp | [!UICONTROL Audience Lab] Support | Nutzungsszenarios |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Alle Kunden | Echtzeit und Stapel | Ja | [Geräte-Targeting](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (einschließlich  [!UICONTROL Co-op Device Graph]) | Alle Kunden | Echtzeit und Stapel | Nein | [Erweitertes Geräte-Targeting](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Alle Kunden | Nur Echtzeit | Nein | [Freigegebenes Geräte-Targeting](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Alle Kunden | Echtzeit und Stapel | Ja | [Online-/Offline-Targeting](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Alle Kunden | Echtzeit und Stapel | Ja | [Geräteübergreifendes Targeting](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (einschließlich  [!UICONTROL Co-op Device Graph]) | Alle Kunden | Echtzeit und Stapel | Nein | [Erweitertes geräteübergreifendes Targeting](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | nicht angegeben | Ausschließen für [Kunden mit personenbezogenen Zielen](../destinations/people-based-destinations-overview.md) | Nur Stapel | Nein | [Targeting für benutzerspezifische Ziele](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Bewertung  {#segment-evaluation}

Abhängig von Ihrer [!UICONTROL Profile Merge Rules]-Konfiguration kann [!DNL Audience Manager] die [!UICONTROL segment]-Auswertung in Echtzeit, im Stapel oder beidem durchführen.

* Für die Echtzeitauswertung von [!UICONTROL segment] ist das [!DNL DCS] erforderlich, damit Besucher in Echtzeit auf Ihre digitalen Eigenschaften zugreifen können, damit sie sich für das [!UICONTROL segment] qualifizieren können.
* Batch [!UICONTROL segment]-Bewertung wird mit zuvor qualifizierten [!UICONTROL traits] durchgeführt.
* [!UICONTROL Profile Merge Rules] die sowohl die Echtzeit- als auch die Batch- [!UICONTROL segment] Auswertung unterstützen, die Echtzeit-Besucher-Aktivität mit zuvor qualifizierten  [!UICONTROL traits]Benutzern kombinieren.

## [!UICONTROL Profile Merge Rules] Latenz von Berichten  {#reporting-latency}

Die Echtzeitauswertung von [!UICONTROL segment] spiegelt sich sofort in den [!UICONTROL Profile Merge Rules]-Berichten wider.

Die Stapelauswertung [!UICONTROL segment] kann bis zu 24 Stunden in den [Profil Merge Rules Reports](profile-link-metrics.md)-Berichten zurückgeben.

## [!UICONTROL Cross-Device Options] {#auth-options}

Mit dem [!UICONTROL Cross-Device Options] können Sie authentifizierte und nicht authentifizierte Benutzer auswählen und ihr geräteübergreifendes Profil für die Segmentierung nutzen. Mit diesen Optionen können Sie bestimmte Benutzer auf einem freigegebenen Gerät identifizieren und erreichen. Weitere Informationen zu anonymen und authentifizierten Benutzern finden Sie unter [Besucher-Authentifizierungsstatus in Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, keine von authentifizierten Benutzern erfassten Daten zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktuelle authentifizierte Profil</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, Daten zu lesen und in das authentifizierte Profil zu schreiben, wenn sich ein Besucher bei Ihrer Site angemeldet hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Zuletzt authentifizierte Profil</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, Daten aus dem authentifizierten Profil des Benutzers zu lesen, der sich zuletzt auf dem Gerät angemeldet hat. </p> <p>Wenn diese Option aktiviert ist, schreibt <span class="keyword"> Audience Manager</span> keine neuen Eigenschaftsdaten in das authentifizierte Profil, wenn der Benutzer anonym ist. Bei der Authentifizierung werden neue Eigenschaftsdaten in das authentifizierte Profil des Benutzers geschrieben. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Alle geräteübergreifenden Profil</span></b> </p> </td> 
   <td colname="col2"> <p>Weist Audience Manager an, Daten von allen geräteübergreifenden Profilen unabhängig vom Authentifizierungsstatus zu lesen. Diese Option steht nur Audience Manager zur Verfügung, die das Add-on "Benutzerbasierte Ziele"gekauft haben.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

Die [!UICONTROL Cross-Device Profile Options]-Liste gibt Ihre [!UICONTROL cross-device data sources] an. Diese Optionen verwenden die Namen, die Sie beim Erstellen von [!UICONTROL cross-device] [!UICONTROL data source] angegeben haben (siehe [Erstellen einer geräteübergreifenden Datenquelle](merge-rules-start.md#create-data-source)). Sie können bis zu 3 [!UICONTROL cross-device data sources] auswählen, um sie mit jeder Profil-Regel zu verwenden. Die [!UICONTROL Authenticated Profile Options] stehen zur Verfügung, wenn Sie **[!UICONTROL Current Authenticated Profiles]** oder **[!UICONTROL Last Authenticated Profiles]** auswählen.

## [!UICONTROL Device Options] {#device-options}

Mit [!UICONTROL Device Options] können Sie den Typ von *`device profile`* auswählen, der von einem [!UICONTROL Profile Merge Rule] verwendet wird. Ein Profil des Geräts wird aus [!UICONTROL traits] erstellt, das aus der anonymen Browserversion-Aktivität erfasst wird. Mindestens ein [!UICONTROL profile merge rule] enthält ein [!UICONTROL authenticated option] und ein [!UICONTROL device option].

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Geräteoption </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Kein Profil des Geräts</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, die im anonymen Profil enthaltenen Eigenschaften nicht für die Segmentierung zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profil des Geräts</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, das anonyme Gerätegerät für die Segmentierung zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gerätediagramm für Profil-Link</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, die Profil vom aktuellen Gerät und bis zu 100 weitere Geräte zu lesen, von denen der Benutzer authentifiziert hat. Dieses Gerätediagramm basiert auf Ihren eigenen Erstanbieterdaten in <span class="keyword"> Audience Manager</span>. Es ist ideal für Kunden, die über eine hohe Authentifizierungsstufe in ihren digitalen Eigenschaften verfügen. Das Gerätediagramm <span class="wintitle"> Profil-Link</span> wird in Echtzeit aktualisiert. Diese Option ist verfügbar, wenn Sie <b><span class="uicontrol"> Aktuelles authentifiziertes Profil</span></b> oder <b><span class="uicontrol"> Letztes authentifiziertes Profil</span></b> auswählen. Bei Verwendung dieser Option können Sie nur ein einziges authentifiziertes Profil (<span class="keyword"> Audience Manager</span> grau die anderen Elemente automatisch ab) auswählen. Siehe auch <a href="profile-link-use-case.md"> Profil Link Device Graph Use Cases</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op-Gerätediagramm</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, die Profil vom aktuellen Gerät und bis zu 100 weitere Geräte unter Verwendung der Links von <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op</a> zu lesen. </p> <p>Die <span class="keyword">-Device Co-op</span> ist eine digitale Kooperation, bei der teilnehmende Kunden Informationen zu Geräteverknüpfungen freigeben. Die <span class="keyword">-Gerätekooperation</span> verarbeitet diese Daten in einem <span class="term">-Gerätediagramm</span>. Ein Gerätediagramm verbindet Geräte mit Formulargerät-Clustern. Diese Links basieren auf <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> probabilistischen und deterministischen Daten</a>. Die Cluster stellen eine Gruppe von Geräten dar, die von einer unbekannten Person verwendet werden. Die <span class="keyword">Device Co-op</span> gibt diese Cluster für die Mitglieder frei, wodurch diese ihren Kunden wertvolle und konsistente Erfahrungen über mehrere Geräte hinweg bieten können. </p> <p> Weitere Informationen zum <span class="wintitle"> Device Co-op</span> finden Sie unter: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Übersicht über die Gerätekooperation</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Voraussetzungen für eine Mitgliedschaft</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Gerätediagramm: Interne Prozesse und Output</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Gerätediagrammoptionen</b>  von Drittanbietern (Person und Haushalt) </p> </td>
   <td colname="col2"> <p>Mit diesen Optionen können Sie Zusammenführungsregeln basierend auf der Gerätediagrammtechnologie eines Drittanbieters erstellen. Ein Gerätediagramm eines Drittanbieters bietet Folgendes: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Wahrscheinliche und/oder deterministische Daten. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Daten auf der Ebene der Person oder des Haushalts. </li> 
     </ul> </p> <p>Um diese Optionen verwenden zu können, müssen Sie Kunde eines Gerätediagramms sein, das bereits mit <span class="keyword"> Audience Manager</span> integriert ist. Wenden Sie sich an Ihren Kundenbetreuer, um weitere Informationen zu erhalten oder um zu beginnen. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Audiencen-Segmente, die automatisch aus anderen [!DNL Experience Cloud]-Lösungen erstellt wurden, basierend auf Zusammenführungsregeln, die außerhalb von [!DNL Audience Manager] definiert wurden, werden als mit einem [!UICONTROL External Merge Policy] gekennzeichnet. Siehe z. B. [Freigabe von Audiencen zwischen Audience Manager und Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profil-Zusammenführungsregeln](../../faq/faq-profile-merge.md)

