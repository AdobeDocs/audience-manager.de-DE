---
description: Mit den Optionen für Zusammenführungsregeln können Sie den Typ der Daten steuern, die Audience Manager für die Segmentierung verwendet. Eine Zusammenführungsregel kann Geräteprofile enthalten, die vom Profillink-Gerätediagramm, dem Adobe Experience Cloud-Gerätekop und/oder anderen Geräteschreiberanbietern von Drittanbietern zugeordnet werden, die in Audience Manager integriert sind. Sie können maximal 4 Regeln zur Profilzusammenführung erstellen.
seo-description: Mit den Optionen für Zusammenführungsregeln können Sie den Typ der Daten steuern, die Audience Manager für die Segmentierung verwendet. Eine Zusammenführungsregel kann Geräteprofile enthalten, die vom Profillink-Gerätediagramm, dem Adobe Experience Cloud-Gerätekop und/oder anderen Geräteschreiberanbietern von Drittanbietern zugeordnet werden, die in Audience Manager integriert sind. Sie können maximal 4 Regeln zur Profilzusammenführung erstellen.
seo-title: Optionen für Profilzusammenführungsregeln definiert
solution: Audience Manager
title: Optionen für Profilzusammenführungsregeln definiert
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: 3a272e31fd388e2b15245f231f11ecf68a7d55e9

---


# Profile Merge Rules Options Defined {#profile-merge-rule-options-defined}

Mit den Optionen für Zusammenführungsregeln können Sie den Typ der Daten steuern, die Audience Manager für die Segmentierung verwendet. Eine Zusammenführungsregel kann Geräteprofile enthalten, die vom [!UICONTROL Profile Link] Gerätediagramm, den [!UICONTROL Adobe Experience Cloud Device Co-op]und/oder anderen Drittanbieter für Gerätediagramme zugeordnet sind, die mit Audience Manager integriert sind. Sie können maximal 4 erstellen [!UICONTROL Profile Merge Rules]. Die vierte Version [!UICONTROL Profile Merge Rule] steht ausschließlich Kunden zur Verfügung, die das [!UICONTROL People-Based Destinations] Add-on gekauft haben.

Sie erstellen eine [!UICONTROL Profile Merge Rule] durch Auswahl der unten beschriebenen Optionen in [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Profile Merge Rule Options Overview {#overview}

Profile Merge Rules ermöglichen eine Reihe von Regelkombinationen, die jeweils auf bestimmte Anwendungsfälle ausgerichtet sind. Die nachstehende Tabelle beschreibt ausführlich, wann die einzelnen Regelkombinationen zu verwenden sind.

| Geräteübergreifende Option | Geräteoption | Verfügbarkeit | Bewertungstyp | Unterstützung für Audience Lab | Nutzungsszenarios |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| Kein geräteübergreifendes Profil | Geräteprofil | Alle Kunden | Echtzeit und Stapel | Ja | [Geräte-Targeting](merge-rule-targeting-options.md#device-personalization) |
| Kein geräteübergreifendes Profil | Grafik für externes Gerät (einschließlich Co-op-Gerätediagramm) | Alle Kunden | Echtzeit und Stapel | Nein | [Erweitertes Geräte-Targeting](external-graph-use-cases.md#audience-expansion) |
| Aktuelle authentifizierte Profile | Kein Geräteprofil | Alle Kunden | Nur Echtzeit | Nein | [Freigegebenes Geräte-Targeting](merge-rule-targeting-options.md#target-shared-devices) |
| Zuletzt authentifizierte Profile | Geräteprofil | Alle Kunden | Echtzeit und Stapel | Ja | [Online-/Offline-Targeting](merge-rule-targeting-options.md#device-household-targeting) |
| Zuletzt authentifizierte Profile |  Gerätediagramm für Profillink | Nur Nordamerika und Kanada | Echtzeit und Stapel | Ja | [Geräteübergreifendes Targeting](profile-link-use-case.md#cross-device-personalization) |
| Zuletzt authentifizierte Profile | Grafik für externes Gerät (einschließlich Co-op-Gerätediagramm) | Alle Kunden | Echtzeit und Stapel | Nein | [Erweitertes geräteübergreifendes Targeting](external-graph-use-cases.md#advanced-graph-expansion) |
| Alle geräteübergreifenden Profile | nicht angegeben | Kunden mit [benutzerspezifischen Zielen](../destinations/people-based-destinations-overview.md) exklusiv | Nur Stapel | Nein | [Personales Targeting](merge-rule-targeting-options.md#all-cross-device) |

## Bewertung des Segments zur Profilzusammenführung {#segment-evaluation}

Abhängig von Ihrer [!UICONTROL Profile Merge Rules] Konfiguration kann Audience Manager die Segmentbewertung in Echtzeit, im Stapel oder beidem durchführen.

* Bei der Segmentbewertung in Echtzeit müssen die Besucher [!DNL DCS] auf Ihre digitalen Eigenschaften in Echtzeit zugreifen können, um sich für das Segment zu qualifizieren.
* Die Segmentbewertung im Stapelverfahren wird mit zuvor qualifizierten Eigenschaften durchgeführt.
* [!UICONTROL Profile Merge Rules] die sowohl die Echtzeit- als auch die Batch-Segmentbewertung unterstützen, kombinieren die Echtzeit-Besucheraktivität mit zuvor qualifizierten Eigenschaften.

## Berichtslatenz für Profilzusammenführungsregeln {#reporting-latency}

Die Segmentbewertung in Echtzeit spiegelt sich sofort in den [!UICONTROL Profile Merge Rules] Berichten wider.

Die Auswertung von Stapelsegmenten kann bis zu 24 Stunden in Anspruch nehmen, um sie in den Berichten zu [Profilzusammenführungsregeln](profile-link-metrics.md)wiederzugeben.

## Geräteübergreifende Optionen {#auth-options}

Mit [!UICONTROL Cross-Device Options] dieser Option können Sie authentifizierte und nicht authentifizierte Benutzer auswählen und ihr geräteübergreifendes Profil für die Segmentierung nutzen. Mit diesen Optionen können Sie bestimmte Benutzer auf einem freigegebenen Gerät identifizieren und erreichen. Weitere Informationen zu anonymen und authentifizierten Benutzern finden Sie unter [Besucherauthentifizierungsstatus in Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktuelle authentifizierte Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, Daten zu lesen und in das authentifizierte Profil zu schreiben, wenn sich ein Besucher bei Ihrer Site angemeldet hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Zuletzt authentifizierte Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, Daten aus dem authentifizierten Profil des Benutzers zu lesen, der sich zuletzt auf dem Gerät angemeldet hat. </p> <p>Wenn diese Option aktiviert ist, schreibt <span class="keyword"> Audience Manager</span> keine neuen Eigenschaftendaten in das authentifizierte Profil, wenn der Benutzer anonym ist. Bei der Authentifizierung werden neue Eigenschaftendaten in das authentifizierte Profil des Benutzers geschrieben. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Alle geräteübergreifenden Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Weist Audience Manager an, Daten aus allen geräteübergreifenden Profilen unabhängig vom Authentifizierungsstatus zu lesen. Diese Option steht nur für Audience Manager-Kunden zur Verfügung, die das Add-On für benutzerspezifische Ziele erworben haben.</p> </td>
  </tr>
 </tbody>
</table>

## Geräteübergreifende Profiloptionen {#profile-options}

Im [!UICONTROL Cross-Device Profile Options] finden Sie alle geräteübergreifenden Datenquellen. Diese Optionen verwenden die Namen, die Sie beim Erstellen einer geräteübergreifenden Datenquelle angegeben haben (siehe [Erstellen einer geräteübergreifenden Datenquelle](merge-rules-start.md#create-data-source)). Sie können bis zu 3 geräteübergreifende Datenquellen auswählen, die mit jeder Profilregel verwendet werden sollen. Die [!UICONTROL Authenticated Profile Options] sind verfügbar, wenn Sie wählen **[!UICONTROL Current Authenticated Profiles]** oder **[!UICONTROL Last Authenticated Profiles]**.

## Geräteoptionen {#device-options}

Mit der [!UICONTROL Device Options] Option können Sie den von einem *`device profile`* Benutzer verwendeten Typ auswählen [!UICONTROL Profile Merge Rule]. Ein Geräteprofil basiert auf Eigenschaften, die bei anonymer Browseraktivität gesammelt wurden. Mindestens eine Regel zum Profilzusammenführen enthält eine authentifizierte Option und eine Geräteoption.

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
   <td colname="col1"> <p> <b><span class="uicontrol"> Gerätediagramm für Profillink</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, die Profile vom aktuellen Gerät und bis zu 100 anderen Geräten zu lesen, von denen der Benutzer authentifiziert hat. Dieses Gerätediagramm basiert auf Ihren eigenen Erstanbieterdaten in <span class="keyword"> Audience Manager</span>. Es ist ideal für Kunden, die über eine hohe Authentifizierungsstufe in ihren digitalen Eigenschaften verfügen. Das <span class="wintitle"> Gerätediagramm "Profillink</span> "wird in Echtzeit aktualisiert. Diese Option ist verfügbar, wenn Sie " <b><span class="uicontrol"> Aktuelles authentifiziertes Profil</span></b> "oder " <b><span class="uicontrol"> Zuletzt authentifiziertes Profil</span></b>"auswählen. Bei Verwendung dieser Option können Sie nur ein einziges authentifiziertes Profil auswählen (<span class="keyword"> Audience Manager</span> graut die anderen automatisch aus). Siehe auch <a href="profile-link-use-case.md"> Profillinkgerät - Anwendungsfälle</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op-Gerätediagramm</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, die Profile vom aktuellen Gerät und bis zu 100 anderen Geräten mithilfe der Links zu lesen, die von der <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud-Gerätekooperation</a>bereitgestellt werden. </p> <p>Die <span class="keyword">-Device Co-op</span> ist eine digitale Kooperation, bei der teilnehmende Kunden Informationen zu Geräteverknüpfungen freigeben. Die <span class="keyword"> Gerätekooperation</span> verarbeitet diese Daten in einem <span class="term"> Gerätediagramm</span>. Ein Gerätediagramm verbindet Geräte mit Formulargerät-Clustern. Diese Links basieren auf <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> probabilistischen und deterministischen Daten</a>. Die Cluster stellen eine Gruppe von Geräten dar, die von einer unbekannten Person verwendet werden. Die <span class="keyword">Device Co-op</span> gibt diese Cluster für die Mitglieder frei, wodurch diese ihren Kunden wertvolle und konsistente Erfahrungen über mehrere Geräte hinweg bieten können. </p> <p> Weitere Informationen zur <span class="wintitle"> Gerätekooperation</span>finden Sie unter: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> Übersicht über die Gerätekooperation</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> Voraussetzungen für eine Mitgliedschaft</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> Gerätediagramm: Interne Prozesse und Output</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager und externe Gerätediagramme</a> (PDF-Download). </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Gerätediagrammoptionen</b> von Drittanbietern (Person und Haushalt) </p> </td>
   <td colname="col2"> <p>Mit diesen Optionen können Sie Zusammenführungsregeln basierend auf der Gerätediagrammtechnologie eines Drittanbieters erstellen. Ein Gerätediagramm eines Drittanbieters bietet Folgendes: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Wahrscheinliche und/oder deterministische Daten. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Daten auf der Ebene der Person oder des Haushalts. </li> 
     </ul> </p> <p>Um diese Optionen verwenden zu können, müssen Sie Kunde eines Gerätediagramms sein, das bereits mit <span class="keyword"> Audience Manager</span>integriert ist. Wenden Sie sich an Ihren Kundenbetreuer, um weitere Informationen zu erhalten oder um zu beginnen. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORE_LIKE_THIS]
>
>* [Häufig gestellte Fragen zu Regeln zur Profilzusammenführung](../../faq/faq-profile-merge.md)

