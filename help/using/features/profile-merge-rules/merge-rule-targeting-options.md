---
description: Mit den Optionen für die Profilzusammenführung können Sie die Zielgruppen-Konzentration auf bestimmte Zielgruppen auf Grundlage von Geschäftsanforderungen oder Zielen erweitern oder optimieren. Diese allgemeinen Anwendungsfälle untersuchen, wie Sie verfügbare Optionen verwenden und Zusammenführungsregeln für Einzelpersonen, Haushalte und geräteübergreifende Targeting erstellen. Derzeit funktionieren Regeln für die Profilzusammenführung nur mit Echtzeitzielen.
seo-description: Mit den Optionen für die Profilzusammenführung können Sie die Zielgruppen-Konzentration auf bestimmte Zielgruppen auf Grundlage von Geschäftsanforderungen oder Zielen erweitern oder optimieren. Diese allgemeinen Anwendungsfälle untersuchen, wie Sie verfügbare Optionen verwenden und Zusammenführungsregeln für Einzelpersonen, Haushalte und geräteübergreifende Targeting erstellen. Derzeit funktionieren Regeln für die Profilzusammenführung nur mit Echtzeitzielen.
seo-title: Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung
solution: Audience Manager
title: Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung
uuid: c 9 eb 41 c 8-fe 19-45 f 8-9 ff 1-552 c 11 ef 08 da
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] Mithilfe von Optionen können Sie die Zielgruppen-Konzentration auf bestimmte Zielgruppen auf Grundlage von Geschäftlichen Anforderungen oder Zielen erweitern oder optimieren. Diese allgemeinen Anwendungsfälle untersuchen, wie Sie verfügbare Optionen verwenden und Zusammenführungsregeln für Einzelpersonen, Haushalte und geräteübergreifende Targeting erstellen. [!UICONTROL Profile Merge Rules] Arbeiten Sie derzeit nur mit Echtzeit-Zielen.

![](assets/merge-rules-options.png)

>[!TIP]
>
>Definitionen und Beschreibungen dieser [!UICONTROL Merge Rule] Einstellungen finden Sie unter Regeloptionen [für die Profilzusammenführung definiert](../../features/profile-merge-rules/merge-rule-definitions.md).

## Fokussierung {#focused-targeting}

User authentication to a website should trigger a declared ID call to [!DNL Audience Manager]. [!DNL Audience Manager] Schreibt nach diesem Ereignis Eigenschaftsdaten an ein authentifiziertes Profil (und liest daraus). Die authentifizierten Profile [!DNL Audience Manager]lassen Folgendes zu:

* Schreibt Eigenschaften in das authentifizierte Profil für einen bestimmten Benutzer.
* Identifizieren und unterscheiden Sie mehrere Gerätebenutzer zur Segmentierung.

### Authentifizierte Benutzer erreichen

Mit den authentifizierten Profiloptionen werden Regeln erstellt, mit denen Sie Benutzer als Ziel auswählen können, die auf einer Website oder einer App basierend auf Offline-Attributen angemeldet sind. Ein Finanzdienstleistungsunternehmen würde diese Option zum Beispiel verwenden, um authentifizierte Benutzer mit gezielten Kreditkartenangeboten oder speziellen Serviceangeboten auf Basis von Einkommen oder Offline-Aktivität abzuzielen. Ein weiteres Beispiel wäre eine Fluglinie für authentifizierte häufige Flackern mit Angeboten, die auf gesponserten Kilometern basieren.

Um eine Regel zu erstellen, die nur authentifizierte Benutzer erreicht, wählen Sie **[!UICONTROL Current Authenticated Profile]** &quot; + **[!UICONTROL No Device Profile]**«. Diese Option wertet ein Segment aus, das nur authentifizierte Profildaten verwendet. Diese Regel ignoriert Daten im anonymen Geräteprofil.

Um auch Daten im Profil für anonyme Geräte einzuschließen, verwenden Sie die **[!UICONTROL Current Authenticated Profile]****[!UICONTROL Current Device Profile]** Regel +.

### Erreichen Sie Benutzer anhand des vorherigen Authentifizierungsstatus.

Diese Optionen erreichen bestimmte Benutzer, wenn sie browsen, aber nicht angemeldet sind. Dies ist mit Optionen möglich, die auf einem abwärts gerichteten Targeting auf Benutzerebene basieren. Mit dem eingehenden Targeting können Sie Personen erreichen, die nicht explizit für Ihre Site authentifiziert sind, aber online browsen. Dies funktioniert durch Lesen (aber nicht schreiben) von Daten aus dem zuletzt authentifizierten Profil. Und damit das authentifizierte Profil sauber bleibt, [!DNL Audience Manager] schreibt es neue Eigenschaften für Eigenschaften in das Geräteprofil anstelle des authentifizierten Profils. Angenommen Sie sind ein Marketingmitarbeiter, der verschiedene Angebote mit vorhandenen Kunden testen möchte, die nicht bei Ihrer Website oder App angemeldet sind. Als Vermarkter können Sie diese Anzeigen mit aktuellen, nicht authentifizierten Kunden testen, um zu sehen, welche Angebote die meisten Antworten erhalten.

Ein Beispiel für eine Regel, die Benutzer anhand der Authentifizierung erreicht, lautet:

* **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Current Device Profile]**

## Erweitertes Targeting {#expanded-targeting}

Neben Regeln, die bestimmte Kunden erreichen, benötigen Marketingexperten außerdem Regeln, die die Größe der für das Targeting verfügbaren Datensätze erhöhen. [!UICONTROL Profile Merge Rules] Hiermit können Sie die Option für das Geräteprofil aktivieren. Die Geräteoptionen erweitern den Datensatz, der für die Segmentierung zulässig ist, da sie auf Eigenschaften gezogen werden, während sich ein Benutzer auf einem oder mehreren Geräten in einem anonymen Status befand. Dies kann nützlich sein, wenn Sie versuchen, einen Benutzer auf allen ihren Geräten mithilfe eines Gerätegerätdiagramms oder aller Geräte in einem Haushalt mit einem Haushaltsgerätediagramm zu erreichen. Ein Verwendungsfall für diese Option könnte die Werbung eines Familienurlaubsangebots enthalten. In diesem Fall möchten Sie jedes Gerät in einem Haushalt mit dem Angebot erreichen, wenn ein Benutzer auf jedem Gerät Interesse an dem Angebot gezeigt hat.

Um eine Regel zu erstellen, die den Targeting-Datensatz erweitert, wählen Sie die **[!UICONTROL Last Authenticated Profiles]** Regel + **[!UICONTROL Device Graph]** aus.

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

Die Auswahl einer [!UICONTROL device graph] Option für eine [!UICONTROL Profile Merge] Regel hängt von Ihren digitalen Eigenschaften und Geschäftszielen ab. Diese allgemeinen Richtlinien können Ihnen dabei helfen, zu verstehen, wann eine Art Diagrammtyp und eine andere verwendet werden. Hinweis: Sie müssen Mitglied der Seite [!DNL Adobe Experience Cloud Device Co-op] sein oder über eine vertragliche Beziehung mit einem externen Gerätediagramm verfügen, um diese Optionen zu verwenden. In der folgenden Tabelle finden Sie allgemeine Hinweise zur Auswahl einer Option für Gerätediagramme. Spezifische Anwendungsfälle finden Sie unter [Anwendungsbeispiele](../../features/profile-merge-rules/profile-link-use-case.md) für Gerätediagramme und Anwendungsfälle [für externe Gerätediagramme](../../features/profile-merge-rules/external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gerätediagrammtyp </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profillink</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Mit</span> der Option <span class="wintitle"> Profillink</span> erstellte Regeln für Profilzusammenführung eignen sich ideal für: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Digitale Eigenschaften mit einer hohen Kundenauthentifizierung. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Gezielte, niedrige Kampagnen. Das <span class="wintitle"> Device Link</span> Device Graph basiert nur auf deterministischen Daten. Dieser Pool von Geräteprofilen ist relativ zum Pool von nicht authentifizierten Benutzern und Geräten immer kleiner. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Anwendungsfälle, in denen Kunden sich in einem authentifizierten Zustand befinden müssen, um die Segmentierung zu ermöglichen. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Externe Gerätediagrammoptionen </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Mit</span> Experience <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Cloud Device Co-op</a> erstellte Regeln für die Profilzusammenführung oder ein beliebiges externes Gerätediagramm, das in <span class="keyword"> Audience Manager integriert ist,</span> eignen sich ideal für: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Digitale Eigenschaften mit einer niedrigen Kundenauthentifizierung. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Umfassende Markenkampagnen mit hoher Reichweite. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Anwendungsfälle, in denen Kunden sich nicht in einem authentifizierten Status befinden müssen, um die Segmentierung zu qualifizieren. </li> 
     </ul> </p> <p> <p>Tipp: <span class="keyword"> Die Gerätekooperation</span> ist Ihre beste Option, wenn Sie <span class="keyword"> ein Experience Cloud</span> -Kunde mit niedriger Authentifizierung und keine Beziehung mit einem Gerätediagrammanbieter sind. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Anwendungsbeispiele für Gerätediagramm-Diagramm](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Anwendungsbeispiele für Diagramme externer Geräte](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Häufig gestellte Fragen zur Profilzusammenführung](../../faq/faq-profile-merge.md)

