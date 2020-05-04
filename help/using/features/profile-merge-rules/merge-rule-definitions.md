---
description: Mit den Optionen für Zusammenführungsregeln können Sie steuern, welcher Typ von Daten von Audience Manager für die Segmentierung verwendet wird. Eine Zusammenführungsregel kann Profil von Geräten umfassen, die vom Gerätediagramm "Profil Link", dem Adobe Experience Cloud Device Co-op und/oder anderen Drittanbietern für Gerätediagramme zugeordnet werden, die in Audience Manager integriert sind. Sie können maximal 4 Profil Merge Rules erstellen.
seo-description: Mit den Optionen für Zusammenführungsregeln können Sie steuern, welcher Typ von Daten von Audience Manager für die Segmentierung verwendet wird. Eine Zusammenführungsregel kann Profil von Geräten umfassen, die vom Gerätediagramm "Profil Link", dem Adobe Experience Cloud Device Co-op und/oder anderen Drittanbietern für Gerätediagramme zugeordnet werden, die in Audience Manager integriert sind. Sie können maximal 4 Profil Merge Rules erstellen.
seo-title: Profil Merge Rule Options Definiert
solution: Audience Manager
title: Profil Merge Rule Options Definiert
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: e8729366a62ec82aa906fe043cf594bff837c737

---


# Profile Merge Rules Options Defined {#profile-merge-rule-options-defined}

Mit den Optionen für Zusammenführungsregeln können Sie steuern, welcher Typ von Daten von Audience Manager für die Segmentierung verwendet wird. Eine Zusammenführungsregel kann Gerätediagramme enthalten, die vom [!UICONTROL Profile Link] Gerätediagramm, dem [!UICONTROL Adobe Experience Cloud Device Co-op]und/oder anderen Geräteschreiberanbietern von Drittanbietern zugeordnet werden, die in Audience Manager integriert sind. Sie können maximal 4 erstellen [!UICONTROL Profile Merge Rules]. Die vierte Version [!UICONTROL Profile Merge Rule] steht ausschließlich Kunden zur Verfügung, die das [!UICONTROL People-Based Destinations] Add-on gekauft haben.

Sie erstellen eine [!UICONTROL Profile Merge Rule] durch Auswahl der unten beschriebenen Optionen in [!UICONTROL Profile Merge Rule Setup].

![Profil-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Profile Merge Rule Options Overview {#overview}

Die Regeln zum Zusammenführen von Profilen ermöglichen eine Reihe von Regelkombinationen, die jeweils auf bestimmte Anwendungsfälle ausgerichtet sind. Die nachstehende Tabelle beschreibt ausführlich, wann die einzelnen Regelkombinationen zu verwenden sind.

| Geräteübergreifende Option | Geräteoption | Verfügbarkeit | Bewertungstyp | Audience Lab-Unterstützung | Nutzungsszenarios |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| Kein geräteübergreifendes Profil | Profil des Geräts | Alle Kunden | Echtzeit und Stapel | Ja | [Geräte-Targeting](merge-rule-targeting-options.md#device-personalization) |
| Kein geräteübergreifendes Profil | Grafik für externes Gerät (einschließlich Co-op-Gerätediagramm) | Alle Kunden | Echtzeit und Stapel | Nein | [Erweitertes Geräte-Targeting](external-graph-use-cases.md#audience-expansion) |
| Aktuelle authentifizierte Profil | Kein Profil des Geräts | Alle Kunden | Nur Echtzeit | Nein | [Freigegebenes Geräte-Targeting](merge-rule-targeting-options.md#target-shared-devices) |
| Zuletzt authentifizierte Profil | Profil des Geräts | Alle Kunden | Echtzeit und Stapel | Ja | [Online-/Offline-Targeting](merge-rule-targeting-options.md#device-household-targeting) |
| Zuletzt authentifizierte Profil | Gerätediagramm für Profil-Link | Alle Kunden | Echtzeit und Stapel | Ja | [Geräteübergreifendes Targeting](profile-link-use-case.md#cross-device-personalization) |
| Zuletzt authentifizierte Profil | Grafik für externes Gerät (einschließlich Co-op-Gerätediagramm) | Alle Kunden | Echtzeit und Stapel | Nein | [Erweitertes geräteübergreifendes Targeting](external-graph-use-cases.md#advanced-graph-expansion) |
| Alle geräteübergreifenden Profil | nicht angegeben | Kunden, die ausschließlich [Kunden mit benutzerspezifischen Zielen](../destinations/people-based-destinations-overview.md) sind | Nur Stapel | Nein | [Targeting für benutzerspezifische Ziele](merge-rule-targeting-options.md#all-cross-device) |

## Bewertung des Segments Profil Merge Rule {#segment-evaluation}

Abhängig von Ihrer [!UICONTROL Profile Merge Rules] Konfiguration kann Audience Manager die Segmentbewertung in Echtzeit, Stapelverarbeitung oder beidem durchführen.

* Bei der Segmentbewertung in Echtzeit müssen die Besucher [!DNL DCS] sehen, wie sie auf Ihre digitalen Eigenschaften zugreifen können, um sich für das Segment qualifizieren zu können.
* Die Segmentbewertung im Stapelverfahren wird mit zuvor qualifizierten Eigenschaften durchgeführt.
* [!UICONTROL Profile Merge Rules] die sowohl die Echtzeit- als auch die Batch-Segmentbewertung unterstützen, kombinieren die Echtzeit-Besucher-Aktivität mit zuvor qualifizierten Eigenschaften.

## Profil Merge Rules Berichte Latenz {#reporting-latency}

Die Segmentbewertung in Echtzeit spiegelt sich sofort in den [!UICONTROL Profile Merge Rules] Berichten wider.

Die Auswertung von Stapelsegmenten kann bis zu 24 Stunden in Anspruch nehmen, um sie in den Berichten zu [Profil-Zusammenführungsregeln](profile-link-metrics.md)widerzuspiegeln.

## Geräteübergreifende Optionen {#auth-options}

Mit [!UICONTROL Cross-Device Options] dieser Option können Sie authentifizierte und nicht authentifizierte Benutzer auswählen und ihr geräteübergreifendes Profil für die Segmentierung nutzen. Mit diesen Optionen können Sie bestimmte Benutzer auf einem freigegebenen Gerät identifizieren und erreichen. Weitere Informationen zu anonymen und authentifizierten Benutzern finden Sie unter [Besucher-Authentifizierungsstatus in Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Weist Audience Manager an, Daten von allen geräteübergreifenden Profilen unabhängig vom Authentifizierungsstatus zu lesen. Diese Option steht nur für Audience Manager-Kunden zur Verfügung, die das Add-On für benutzerspezifische Ziele erworben haben.</p> </td>
  </tr>
 </tbody>
</table>

## Geräteübergreifende Profil-Optionen {#profile-options}

Die [!UICONTROL Cross-Device Profile Options] Listen Ihrer geräteübergreifenden Datenquellen. Diese Optionen verwenden die Namen, die Sie beim Erstellen einer geräteübergreifenden Datenquelle angegeben haben (siehe [Erstellen einer geräteübergreifenden Datenquelle](merge-rules-start.md#create-data-source)). Sie können bis zu 3 geräteübergreifende Datenquellen auswählen, die mit jeder Profil-Regel verwendet werden sollen. Die [!UICONTROL Authenticated Profile Options] sind verfügbar, wenn Sie wählen **[!UICONTROL Current Authenticated Profiles]** oder **[!UICONTROL Last Authenticated Profiles]**.

## Geräteoptionen {#device-options}

Mit der [!UICONTROL Device Options] Option können Sie den von einem *`device profile`* Benutzer verwendeten Typ auswählen [!UICONTROL Profile Merge Rule]. Ein Profil eines Geräts wird aus Eigenschaften erstellt, die aus der anonymen Browsing-Aktivität erfasst werden. Eine Profil Merge-Regel enthält mindestens eine authentifizierte Option und eine Geräteoption.

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
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, das anonyme Geräte-Profil für die Segmentierung zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gerätediagramm für Profil-Link</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, die Profil vom aktuellen Gerät und bis zu 100 anderen Geräten zu lesen, von denen der Benutzer authentifiziert hat. Dieses Gerätediagramm basiert auf Ihren eigenen Erstanbieterdaten im <span class="keyword"> Audience Manager</span>. Es ist ideal für Kunden, die über eine hohe Authentifizierungsstufe in ihren digitalen Eigenschaften verfügen. Das Gerätediagramm <span class="wintitle"> Profil Link</span> wird in Echtzeit aktualisiert. Diese Option ist verfügbar, wenn Sie " <b><span class="uicontrol"> Aktuelles authentifiziertes Profil</span></b> "oder " <b><span class="uicontrol"> Zuletzt authentifiziertes Profil</span></b>"auswählen. Wenn Sie diese Option verwenden, können Sie nur ein einziges authentifiziertes Profil auswählen (<span class="keyword"> Audience Manager</span> graut die anderen automatisch aus). Siehe auch <a href="profile-link-use-case.md"> Anwendungsfälle</a>für Gerätediagramme zu Profil-Links. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op-Gerätediagramm</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, die Profil vom aktuellen Gerät und bis zu 100 anderen Geräten mithilfe der Links zu lesen, die von der <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud-Gerätekooperation</a>bereitgestellt werden. </p> <p>Die <span class="keyword">-Device Co-op</span> ist eine digitale Kooperation, bei der teilnehmende Kunden Informationen zu Geräteverknüpfungen freigeben. Die <span class="keyword"> Gerätekooperation</span> verarbeitet diese Daten in einem <span class="term"> Gerätediagramm</span>. Ein Gerätediagramm verbindet Geräte mit Formulargerät-Clustern. Diese Links basieren auf <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> probabilistischen und deterministischen Daten</a>. Die Cluster stellen eine Gruppe von Geräten dar, die von einer unbekannten Person verwendet werden. Die <span class="keyword">Device Co-op</span> gibt diese Cluster für die Mitglieder frei, wodurch diese ihren Kunden wertvolle und konsistente Erfahrungen über mehrere Geräte hinweg bieten können. </p> <p> Weitere Informationen zur <span class="wintitle"> Gerätekooperation</span>finden Sie unter: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Übersicht über die Gerätekooperation</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Voraussetzungen für eine Mitgliedschaft</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Gerätediagramm: Interne Prozesse und Output</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Gerätediagrammoptionen</b> von Drittanbietern (Person und Haushalt) </p> </td>
   <td colname="col2"> <p>Mit diesen Optionen können Sie Zusammenführungsregeln basierend auf der Gerätediagrammtechnologie eines Drittanbieters erstellen. Ein Gerätediagramm eines Drittanbieters bietet Folgendes: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Wahrscheinliche und/oder deterministische Daten. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Daten auf der Ebene der Person oder des Haushalts. </li> 
     </ul> </p> <p>Um diese Optionen verwenden zu können, müssen Sie ein Gerätediagramm verwenden, das bereits mit <span class="keyword"> Audience Manager</span>integriert ist. Wenden Sie sich an Ihren Kundenbetreuer, um weitere Informationen zu erhalten oder um zu beginnen. </p> </td>
  </tr>
 </tbody>
</table>

## Richtlinien für externe Zusammenschlüsse {#external-merge-policies}

Audiencen, die auf der Grundlage von Zusammenführungsregeln, die außerhalb von Audience Manager definiert wurden, automatisch aus anderen Experience Cloud-Lösungen erstellt wurden, werden als mit einem [!UICONTROL External Merge Policy]gekennzeichnet. Siehe z. B. Freigabe von [Audiencen zwischen Audience Manager und Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profil-Zusammenführungsregeln](../../faq/faq-profile-merge.md)

