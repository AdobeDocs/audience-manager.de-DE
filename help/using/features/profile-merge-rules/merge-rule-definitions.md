---
description: Mit den Optionen für Zusammenführungsregeln können Sie den Datentyp steuern, den Audience Manager für die Segmentierung verwendet. Eine Zusammenführungsregel kann Geräteprofile enthalten, die vom Profillink-Gerätediagramm, der Adobe Experience Cloud-Gerätekooperation und/oder anderen, mit Audience Manager integrierten Gerätediagrammanbietern von Drittanbietern zugeordnet werden. Sie können maximal 4 Profilzusammenführungsrichtlinien erstellen.
seo-description: Mit den Optionen für Zusammenführungsregeln können Sie den Datentyp steuern, den Audience Manager für die Segmentierung verwendet. Eine Zusammenführungsregel kann Geräteprofile enthalten, die vom Profillink-Gerätediagramm, der Adobe Experience Cloud-Gerätekooperation und/oder anderen, mit Audience Manager integrierten Gerätediagrammanbietern von Drittanbietern zugeordnet werden. Sie können maximal 4 Profilzusammenführungsrichtlinien erstellen.
seo-title: Für Profilzusammenführungsrichtlinien definierte Optionen
solution: Audience Manager
title: Für Profilzusammenführungsrichtlinien definierte Optionen
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profilzusammenführung
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 6%

---

# [!UICONTROL Profile Merge Rules] Definierte Optionen  {#profile-merge-rule-options-defined}

Mit den [!UICONTROL profile merge rule] -Optionen können Sie den Datentyp steuern, den [!DNL Audience Manager] für die Segmentierung verwendet. Ein [!UICONTROL profile merge rule] kann Geräteprofile enthalten, die vom [!UICONTROL Profile Link]-Gerätediagramm, dem [!UICONTROL Adobe Experience Cloud Device Co-op] und/oder anderen, mit [!DNL Audience Manager] integrierten Gerätediagramm-Anbietern von Drittanbietern zugeordnet werden. Sie können maximal 4 [!UICONTROL Profile Merge Rules] erstellen. Das vierte [!UICONTROL Profile Merge Rule] steht ausschließlich Kunden zur Verfügung, die das [!UICONTROL People-Based Destinations]-Add-on erworben haben.

Sie erstellen ein [!UICONTROL Profile Merge Rule], indem Sie eine Auswahl aus den unten beschriebenen Optionen treffen, in [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Optionsübersicht {#overview}

[!UICONTROL Profile Merge Rules] ermöglichen eine Reihe von Regelkombinationen, die jeweils auf bestimmte Anwendungsfälle ausgerichtet sind. Die nachstehende Tabelle beschreibt ausführlich, wann die einzelnen Regelkombinationen zu verwenden sind.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Verfügbarkeit | Testtyp | [!UICONTROL Audience Lab] Support | Nutzungsszenarios |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Alle Kunden | Echtzeit und Batch | Ja | [Geräte-Targeting](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (umfasst  [!UICONTROL Co-op Device Graph]) | Alle Kunden | Echtzeit und Batch | Nein | [Erweitertes Geräte-Targeting](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Alle Kunden | Nur in Echtzeit | Nein | [Freigegebenes Geräte-Targeting](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Alle Kunden | Echtzeit und Batch | Ja | [Online-/Offline-Targeting](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Alle Kunden | Echtzeit und Batch | Ja | [Geräteübergreifendes Targeting](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (umfasst  [!UICONTROL Co-op Device Graph]) | Alle Kunden | Echtzeit und Batch | Nein | [Erweitertes geräteübergreifendes Targeting](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | nicht angegeben | Ausschließlich Kunden mit [People-Based Destinations](../destinations/people-based-destinations-overview.md) | Nur Batch | Nein | [Targeting für personenbasierte Ziele](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Auswertung  {#segment-evaluation}

Abhängig von Ihrer [!UICONTROL Profile Merge Rules]-Konfiguration kann [!DNL Audience Manager] die [!UICONTROL segment]-Bewertung in Echtzeit, im Batch-Modus oder beidem durchführen.

* Für die Echtzeitauswertung von [!UICONTROL segment] ist [!DNL DCS] erforderlich, damit Besucher in Echtzeit auf Ihre digitalen Eigenschaften zugreifen können, um sich für die [!UICONTROL segment] zu qualifizieren.
* Die Batch-Auswertung [!UICONTROL segment] wird mit dem zuvor qualifizierten [!UICONTROL traits] durchgeführt.
* [!UICONTROL Profile Merge Rules] die sowohl die Echtzeit- als auch die Batch- [!UICONTROL segment] Auswertung unterstützen, kombinieren die Echtzeit-Besucheraktivität mit der zuvor qualifizierten  [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Berichtslatenz  {#reporting-latency}

Die Echtzeitauswertung von [!UICONTROL segment] spiegelt sich sofort in den [!UICONTROL Profile Merge Rules] -Berichten wider.

Die Batch-Auswertung [!UICONTROL segment] kann bis zu 24 Stunden dauern, bis sie in den [Berichten zu Profilzusammenführungsregeln](profile-link-metrics.md) angezeigt wird.

## [!UICONTROL Cross-Device Options] {#auth-options}

Mit [!UICONTROL Cross-Device Options] können Sie authentifizierte und nicht authentifizierte Benutzer auswählen und ihr geräteübergreifendes Profil für die Segmentierung nutzen. Mithilfe dieser Optionen können Sie bestimmte Benutzer auf einem gemeinsam genutzten Gerät identifizieren und erreichen. Weitere Informationen zu anonymen und authentifizierten Benutzern finden Sie unter [Besucherauthentifizierungsstatus in Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, Daten aus dem authentifizierten Profil des Benutzers zu lesen, der sich zuletzt auf dem Gerät angemeldet hat. </p> <p>Wenn ausgewählt, schreibt <span class="keyword"> Audience Manager</span> keine neuen Eigenschaftsdaten in das authentifizierte Profil, wenn der Benutzer anonym ist. Bei der Authentifizierung werden neue Eigenschaftsdaten in das authentifizierte Profil des Benutzers geschrieben. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Alle geräteübergreifenden Profile</span></b> </p> </td> 
   <td colname="col2"> <p>Weist Audience Manager an, Daten aus allen geräteübergreifenden Profilen zu lesen, unabhängig vom Authentifizierungsstatus. Diese Option steht nur Audience Manager zur Verfügung, die das Add-on "People-Based Destinations"erworben haben.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

Die [!UICONTROL Cross-Device Profile Options] listet Ihre [!UICONTROL cross-device data sources] auf. Diese Optionen verwenden die Namen, die Sie beim Erstellen von [!UICONTROL cross-device] [!UICONTROL data source] angegeben haben (siehe [Erstellen einer geräteübergreifenden Datenquelle](merge-rules-start.md#create-data-source)). Sie können bis zu 3 [!UICONTROL cross-device data sources] auswählen, um diese für jede Profilregel zu verwenden. Die [!UICONTROL Authenticated Profile Options] sind verfügbar, wenn Sie **[!UICONTROL Current Authenticated Profiles]** oder **[!UICONTROL Last Authenticated Profiles]** auswählen.

## [!UICONTROL Device Options] {#device-options}

Mit [!UICONTROL Device Options] können Sie den Typ von *`device profile`* auswählen, der von einem [!UICONTROL Profile Merge Rule] verwendet wird. Ein Geräteprofil wird aus [!UICONTROL traits] erstellt, das aus der anonymen Browsing-Aktivität erfasst wird. Mindestens ein [!UICONTROL profile merge rule] enthält ein [!UICONTROL authenticated option] und ein [!UICONTROL device option].

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
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, die im anonymen Profil enthaltenen Eigenschaften nicht zur Segmentierung zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Geräteprofil</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, das anonyme Geräteprofil für die Segmentierung zu verwenden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gerätediagramm für Profilverknüpfung</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, die Profile vom aktuellen Gerät und bis zu 100 weitere Geräte zu lesen, von denen sich der Benutzer authentifiziert hat. Dieses Gerätediagramm basiert auf Ihren eigenen Erstanbieterdaten in <span class="keyword"> Audience Manager</span>. Es ist ideal für Kunden, die über ihre digitalen Eigenschaften hinweg über einen hohen Authentifizierungsgrad verfügen. Das Gerätediagramm <span class="wintitle"> Profil-Link</span> wird in Echtzeit aktualisiert. Diese Option ist verfügbar, wenn Sie <b><span class="uicontrol"> Aktuelles authentifiziertes Profil</span></b> oder <b><span class="uicontrol"> Letztes authentifiziertes Profil</span></b> auswählen. Wenn Sie diese Option verwenden, können Sie nur ein einziges authentifiziertes Profil auswählen (<span class="keyword"> Audience Manager</span> graut die anderen automatisch aus). Siehe auch <a href="profile-link-use-case.md"> Anwendungsfälle für Profillink-Gerätediagramme</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op-Gerätediagramm</span></b> </p> </td> 
   <td colname="col2"> <p>Weist <span class="keyword"> Audience Manager</span> an, die Profile vom aktuellen Gerät und bis zu 100 weitere Geräte unter Verwendung der Links zu lesen, die von der <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op</a> bereitgestellt werden. </p> <p>Die <span class="keyword">-Device Co-op</span> ist eine digitale Kooperation, bei der teilnehmende Kunden Informationen zu Geräteverknüpfungen freigeben. Die <span class="keyword"> Device Co-op</span> verarbeitet diese Daten in einem <span class="term"> Gerätediagramm</span>. Ein Gerätediagramm verknüpft Geräte mit Geräteclustern. Diese Links werden aus <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> probabilistischen und deterministischen Daten</a> erstellt. Die Cluster stellen eine Gruppe von Geräten dar, die von einer unbekannten Person verwendet werden. Die <span class="keyword">Device Co-op</span> gibt diese Cluster für die Mitglieder frei, wodurch diese ihren Kunden wertvolle und konsistente Erfahrungen über mehrere Geräte hinweg bieten können. </p> <p> Weitere Informationen zur <span class="wintitle"> Device Co-op</span> finden Sie unter: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Übersicht über die Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Voraussetzungen für eine Mitgliedschaft</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Gerätediagramm: Interne Prozesse und Ausgabe</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Gerätediagrammoptionen von Drittanbietern</b>  (Person und Haushalt) </p> </td>
   <td colname="col2"> <p>Mit diesen Optionen können Sie Zusammenführungsregeln basierend auf der Gerätediagrammtechnologie erstellen, die von einem Drittanbieter bereitgestellt wird. Ein Gerätediagramm von Drittanbietern bietet Folgendes: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Probabilistische und/oder deterministische Daten. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Daten auf Personen- oder Haushaltsebene. </li> 
     </ul> </p> <p>Um diese Optionen verwenden zu können, müssen Sie Kunde eines Gerätediagramms sein, der bereits mit <span class="keyword"> Audience Manager</span> integriert ist. Wenden Sie sich an Ihren Kundenbetreuer, um weitere Informationen zu erhalten oder zu beginnen. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Zielgruppensegmente, die basierend auf außerhalb von [!DNL Audience Manager] definierten Zusammenführungsregeln automatisch aus anderen [!DNL Experience Cloud]-Lösungen erstellt wurden, werden mit einem [!UICONTROL External Merge Policy] markiert. Siehe beispielsweise [Zielgruppenfreigabe zwischen Audience Manager und Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Häufig gestellte Fragen zu Profilzusammenführungsregeln](../../faq/faq-profile-merge.md)

