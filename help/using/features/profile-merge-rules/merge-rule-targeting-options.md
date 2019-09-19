---
description: Mit den Optionen für Regeln zur Profilzusammenführung können Sie den Fokus auf bestimmte Zielgruppen je nach Geschäftsanforderungen oder Zielen erweitern oder verschärfen. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden können, und es werden Regeln zum Zusammenführen von Targeting für einzelne Geräte, Haushalte und Geräte erstellt. Derzeit funktionieren Regeln zum Profilzusammenführen nur mit Echtzeit-Zielen.
seo-description: Mit den Optionen für Regeln zur Profilzusammenführung können Sie den Fokus auf bestimmte Zielgruppen je nach Geschäftsanforderungen oder Zielen erweitern oder verschärfen. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden können, und es werden Regeln zum Zusammenführen von Targeting für einzelne Geräte, Haushalte und Geräte erstellt. Derzeit funktionieren Regeln zum Profilzusammenführen nur mit Echtzeit-Zielen.
seo-title: Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung
solution: Audience Manager
title: Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] Mit diesen Optionen können Sie den Fokus der Zielgruppe auf bestimmte Zielgruppen basierend auf geschäftlichen Anforderungen oder Zielen erweitern oder verschärfen. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden können, und es werden Regeln zum Zusammenführen von Targeting für einzelne Geräte, Haushalte und Geräte erstellt. Arbeiten Sie derzeit nur mit Echtzeit-Zielen [!UICONTROL Profile Merge Rules] .

![](assets/merge-rules-options.png)

>[!TIP]
>
>Definitionen und Beschreibungen dieser [!UICONTROL Merge Rule] Einstellungen finden Sie unter Optionen für [Profilzusammenführungsregeln definiert](../../features/profile-merge-rules/merge-rule-definitions.md).

## Fokussiertes Targeting {#focused-targeting}

Die Benutzerauthentifizierung für eine Website sollte einen deklarierten ID-Aufruf an auslösen [!DNL Audience Manager]. Nach diesem Ereignis werden [!DNL Audience Manager] Eigenschaftendaten in ein authentifiziertes Profil geschrieben (und daraus gelesen). Das authentifizierte Profil ermöglicht Folgendes [!DNL Audience Manager]:

* Schreiben Sie Eigenschaften in das authentifizierte Profil, das für einen bestimmten Benutzer spezifisch ist.
* Identifizieren und unterscheiden Sie zwischen mehreren Gerätebenutzern für die Segmentierung.

### Authentifizierte Benutzer erreichen

Mit den Optionen für das authentifizierte Profil können Sie Regeln erstellen, mit denen Sie Benutzer, die auf der Grundlage von Offline-Attributen bei einer Website oder App angemeldet sind, als Ziel auswählen können. Ein Finanzdienstleistungsunternehmen würde diese Option beispielsweise verwenden, um authentifizierte Benutzer mit gezielten Kreditkartenaktualisierungsangeboten oder spezialisierten Serviceangeboten auf Basis des Einkommens oder der Offline-Aktivität anzusprechen. Ein weiteres Beispiel wäre eine Fluglinie, die authentifizierte Vielflieger mit auf der Grundlage der gesammelten Meilen getätigten Geschäften anspricht.

Um eine Regel zu erstellen, die nur authentifizierte Benutzer erreicht, wählen Sie **[!UICONTROL Current Authenticated Profile]** + **[!UICONTROL No Device Profile]**. Mit dieser Option wird ein Segment ausschließlich anhand authentifizierter Profildaten bewertet. Diese Regel ignoriert Daten im anonymen Geräteprofil.

Wenn Sie auch Daten in das anonyme Geräteprofil aufnehmen möchten, verwenden Sie die **[!UICONTROL Current Authenticated Profile]** +- **[!UICONTROL Current Device Profile]** Regel.

### Benutzer auf Basis des vorherigen Authentifizierungsstatus erreichen

Diese Optionen greifen auf bestimmte Benutzer zu, wenn sie suchen, aber nicht angemeldet sind. Dies können Sie mit Optionen durchführen, die auf abgeleitetem Targeting auf Benutzerebene basieren. Inferred Targeting hilft Ihnen, Personen zu erreichen, die nicht explizit für Ihre Site authentifiziert sind, aber möglicherweise online surfen. Es funktioniert durch Lesen (aber nicht Schreiben) von Daten aus dem zuletzt authentifizierten Profil. Um das authentifizierte Profil sauber zu halten, schreibt man neue Eigenschaften-Qualifikationen in das Geräteprofil und nicht in das authentifizierte Profil. [!DNL Audience Manager] Angenommen, Sie sind ein Vermarkter, der verschiedene Angebote mit bestehenden Kunden testen möchte, die nicht bei Ihrer Site oder App angemeldet sind. Als Vermarkter können Sie diese Anzeigen mit aktuellen, nicht authentifizierten Kunden testen, um zu sehen, welche Angebote die beste Antwort erhalten.

Ein Beispiel für eine Regel, die Benutzer auf Grundlage der vorherigen Authentifizierung erreicht, ist:

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Erweitertes Targeting {#expanded-targeting}

Neben Regeln, die bestimmten Kunden helfen, benötigen Marketingexperten auch Regeln, die die Größe der für das Targeting verfügbaren Datensätze erhöhen. [!UICONTROL Profile Merge Rules] können Sie dies mit der Geräteprofiloption tun. Die Geräteoptionen erweitern den Datensatz, der für die Segmentierung geeignet ist, da sie auf Eigenschaften basieren, die realisiert wurden, während sich ein Benutzer auf einem oder mehreren Geräten in einem anonymen Status befand. Dies kann nützlich sein, wenn Sie versuchen, einen Benutzer über alle Geräte mit einem Personengerät-Diagramm oder mit allen Geräten in einem Haushalt mit einem Haushaltsgerät-Diagramm zu erreichen. Ein Anwendungsfall für diese Option könnte die Werbung für ein Familienurlaubsangebot sein. In diesem Fall möchten Sie jedes Gerät in einem Haushalt mit dem Angebot erreichen, wenn ein Benutzer auf einem Gerät Interesse an dem Angebot gezeigt hat.

Um eine Regel zu erstellen, die den Targeting-Datensatz erweitert, wählen Sie die **[!UICONTROL Last Authenticated Profiles]** +- **[!UICONTROL Device Graph]** Regel.

<!-- 

<p>Rules that use the device graph option extend your data set even further. With the device graph option, <span class="keyword"> Audience Manager</span> relies on the device profiles aggregated from the last 3 devices that a visitor used for authentication to your site. The device graph rules include: </p> 
<p> 
 <ul id="ul_3008B6AF16EC408F98EC4088111281FB"> 
  <li id="li_FA2087F1ED454CD0B9E09656B79ED23B"> <b><span class="uicontrol"> Current Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
  <li id="li_001A8DB517CB4EE394DBD530F2080FD5"> <b><span class="uicontrol"> Last Authenticated Profiles</span></b> + <b><span class="uicontrol"> Profile Merge Device Graph</span></b> or a Co-op device graph option </li> 
 </ul> </p> 
<p> 
 <note type="tip">
  Create a simple rule with 
  <b><span class="uicontrol"> No Authenticated Profile</span></b> + 
  <b><span class="uicontrol"> Current Device Profile</span></b> when you're still developing a strategy and are unsure about which options to choose or if your site doesn't use authentication. 
 </note> </p>

 -->

## Gerätediagrammoptionen {#device-graph-options}

Die Auswahl einer [!UICONTROL device graph] Option für eine [!UICONTROL Profile Merge] Regel hängt von Bedingungen ab, die für Ihre digitalen Eigenschaften und Geschäftsziele spezifisch sind. Diese allgemeinen Richtlinien helfen Ihnen dabei, zu verstehen, wann ein Diagrammtyp im Vergleich zu einem anderen verwendet werden soll. Beachten Sie, dass Sie Mitglied der [!DNL Adobe Experience Cloud Device Co-op] oder eine vertragliche Beziehung zu einem externen Gerätediagramm haben müssen, um diese Optionen nutzen zu können. Die nachstehende Tabelle gibt einen Überblick darüber, wann eine Gerätediagrammoption gewählt werden soll. Für spezifische Anwendungsfälle siehe [Profillink-Gerätediagramm Verwendungsfälle](../../features/profile-merge-rules/profile-link-use-case.md) und [Anwendungsfälle](../../features/profile-merge-rules/external-graph-use-cases.md)für externe Gerätediagramme.

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Geräteschreibungsart </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profillink</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Regeln zur Profilzusammenführung</span> , die mit der Option <span class="wintitle"> Profillink</span> erstellt wurden, eignen sich ideal für: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Digitale Eigenschaften mit einer hohen Kundenauthentifizierung. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Fokussierte Kampagnen mit geringer Reichweite. Das <span class="wintitle"> Gerätediagramm "Profillink</span> "basiert ausschließlich auf deterministischen Daten. Dieser Pool an Geräteprofilen ist immer kleiner im Verhältnis zum Pool nicht authentifizierter Benutzer und Geräte. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Anwendungsfälle, in denen Kunden sich in einem authentifizierten Zustand befinden müssen, um sich für die Segmentierung zu qualifizieren. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Optionen für externe Gerätediagramme </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Regeln zur Profilzusammenführung</span> , die mit der <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud-Gerätekooperation</a> oder einem externen Gerätediagramm, das mit <span class="keyword"> Audience Manager</span> integriert ist, erstellt wurden, eignen sich ideal für: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Digitale Eigenschaften mit niedriger Kundenauthentifizierung. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Umfassende, umfassende Markenkampagnen. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Anwendungsfälle, bei denen Kunden sich nicht in einem authentifizierten Zustand befinden müssen, um sich für die Segmentierung zu qualifizieren. </li> 
     </ul> </p> <p> <p>Tipp: Die <span class="keyword"> Gerätekooperation</span> ist die beste Option, wenn Sie ein <span class="keyword"> Experience Cloud</span> -Kunde mit niedriger Authentifizierung und keiner Beziehung zu einem Device Graph Provider sind. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Anwendungsfälle des Profillink-Gerätediagramms](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Anwendungsbeispiele für Diagramme externer Geräte](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Häufig gestellte Fragen zu Regeln zur Profilzusammenführung](../../faq/faq-profile-merge.md)

