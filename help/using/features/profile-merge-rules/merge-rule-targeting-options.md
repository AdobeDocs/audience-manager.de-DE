---
description: Mit den Optionen für Regeln zur Profilzusammenführung können Sie den Fokus auf bestimmte Zielgruppen je nach Geschäftsanforderungen oder Zielen erweitern oder verschärfen. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden können, und es werden Regeln zum Zusammenführen von Targeting für einzelne Geräte, Haushalte und Geräte erstellt.
seo-description: Mit den Optionen für Regeln zur Profilzusammenführung können Sie den Fokus auf bestimmte Zielgruppen je nach Geschäftsanforderungen oder Zielen erweitern oder verschärfen. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden können, und es werden Regeln zum Zusammenführen von Targeting für einzelne Geräte, Haushalte und Geräte erstellt.
seo-title: Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung
solution: Audience Manager
title: Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: a4f0b9d2252fd85322d00f965ff35a9fed04d3f8

---


# Allgemeine Anwendungsfälle für Regeln zur Profilzusammenführung {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] Mit diesen Optionen können Sie den Fokus der Zielgruppe auf bestimmte Zielgruppen basierend auf geschäftlichen Anforderungen oder Zielen erweitern oder verschärfen. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden können, und es werden Regeln zum Zusammenführen von Targeting für einzelne Geräte, Haushalte und Geräte erstellt. [!UICONTROL Profile Merge Rules] mit Echtzeit- und Stapelzielen arbeiten.

>[!TIP]
>
>Definitionen und Beschreibungen dieser [!UICONTROL Merge Rule] Einstellungen finden Sie unter Optionen für [Profilzusammenführungsregeln definiert](merge-rule-definitions.md).

## Geräte-Targeting {#device-personalization}

Dieses Szenario gilt für Marketingexperten, die ein einzelnes Geräteprofil für ein Zielgruppensegment auswerten möchten, das in Audience Manager definiert ist, um dem Gerät ein konsistentes Erlebnis mit Targeting-Plattformen zu bieten, die Geräte-IDs (DSPs, On-Site-Personalisierungsplattformen und andere gerätebasierte Targeting-Plattformen) unterstützen, wobei die Benutzerauthentifizierung nicht berücksichtigt wird.

Um eine Regel zu erstellen, die nur auf Geräteprofile abzielt, wählen Sie **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![device-only](assets/device-only.png)

Nehmen wir an, John besitzt drei Smartphones. Zwei davon sind iPhone 7s auf Data Plan A, und einer davon ist ein Samsung auf Data Plan B. John's Mobilnetzbetreiber möchte ihm auf keinem der drei Geräte ein Upgrade seines Datenplans anbieten, jedoch nur für iPhone 7-Geräte, die auf Data Plan A ausgeführt werden.

Durch die Verwendung der **[!UICONTROL No Cross-Device Profile]** +- **[!UICONTROL Device Profile]** Regel [!DNL Device 1] und [!DNL Device 3] beide sind für das Segment qualifiziert, während Device 2 ignoriert wird.

![device-only](assets/device-management.png)

## Freigegebenes Geräte-Targeting {#target-shared-devices}

Nehmen wir an, John und seine Frau Jane, benutzen den gleichen Laptop, um einen Online-Shop zu besuchen und verschiedene Artikel zu bestellen.

John nutzt sein eigenes Konto, um Reisetickets und Sonderangebote zu buchen, während Jane ihr eigenes Konto für Musik und Filme nutzt.

Das Marketingteam des Stores kann mithilfe der **[!UICONTROL Current Authenticated Profiles]** +- **[!UICONTROL No Device Profile]** Regel John und Jane mit spezifischen Angeboten ausrichten, die ausschließlich auf ihrer authentifizierten Aktivität basieren.

![current-no-device](assets/current-no-device.png)

Durch die Verwendung dieser Regel ignoriert Audience Manager das Geräteprofil vollständig und qualifiziert die CRM-ID von John für das Segment und nicht die CRM-ID von Jane.

![shared-device-targeting](assets/shared-device-targeting.png)

## Online-/Offline-Targeting {#device-household-targeting}

Dieser Anwendungsfall umfasst das Identitätsmanagement von Haushalten. Ein Unternehmen kann ein einzelnes Geräteprofil mit dem letzten auf diesem Gerät authentifizierten Profil zusammenführen, indem es die Regel **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** verwendet.

![last-device-profile](assets/last-device-profile.png)

Betrachten wir ein Segment, das aus Haushalten mit einem Einkommen von über 100.000 US-Dollar pro Jahr besteht und mindestens ein Gerät enthält, das ein [!DNL iPhone 7] on ist [!DNL Data Plan B]. Wir haben zwei Profile für den Haushalt (geräteübergreifende Profile), die jeweils an zwei verschiedene Geräteprofile angeschlossen sind. Die Eigenschaften, die für die Berechtigung für das Segment erforderlich sind, werden über die Geräte- und geräteübergreifenden Profile verteilt.

Audience Manager führt alle Geräte- und geräteübergreifenden Profilpaare zusammen, um zu sehen, ob der zusammengeführte Eigenschaftensatz für das Segment geeignet ist. Da Audience Manager jedes in der Zusammenführung enthaltene Profil auswertet, können sowohl ein Geräteprofil als auch ein Haushaltsprofil segmentiert werden.

Durch die Verknüpfung zwischen dem Gerät und dem Profil für den Haushalt kann sich Audience Manager [!DNL Household 2] für das Segment qualifizieren, jedoch nicht [!DNL Household 1]. Von [!DNL Household 2]hier aus qualifiziert sich nur [!DNL Device 3] das Segment. Dadurch [!UICONTROL Profile Merge Rule] konnte der Marketingspezialist eine einheitliche Marketingbotschaft an ein einzelnes Gerät ([!DNL Device 3]) und den weiteren Haushalt ([!DNL Household 2]) senden.

![Haushaltsführung](assets/household-management.png)

## Personales Targeting {#all-cross-device}

Dieses Targeting-Szenario steht nur Kunden zur Verfügung, die das [!DNL People-Based Destinations] Add-on gekauft haben. Diese Regel ermöglicht es Marketingexperten, Kunden anhand ihrer eigenen, authentifizierten Daten zu erreichen.

Nehmen wir an, ein Online-Händler möchte über soziale Plattformen bestehende Kunden erreichen und ihnen personalisierte Angebote auf Basis ihrer bisherigen Bestellungen zeigen. Damit können sie [!UICONTROL People-Based Destinations]Hash-E-Mail-Adressen von sich aus [!DNL CRM] zu Audience Manager erfassen, Segmente aus den Offlinedaten erstellen und diese Segmente an die sozialen Plattformen senden, für die sie werben möchten, und ihre Werbeausgaben optimieren.

Weitere Informationen zu dieser Option finden Sie unter [Benutzerbasierte Ziele](../destinations/people-based-destinations-overview.md).

![all-cross-device](assets/all-cross-device.png)

## Gerätediagrammoptionen {#device-graph-options}

Die Auswahl einer [!UICONTROL device graph] Option für eine [!UICONTROL Profile Merge] Regel hängt von Bedingungen ab, die für Ihre digitalen Eigenschaften und Geschäftsziele spezifisch sind. Diese allgemeinen Richtlinien helfen Ihnen dabei, zu verstehen, wann ein Diagrammtyp im Vergleich zu einem anderen verwendet werden soll. Beachten Sie, dass Sie Mitglied der [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) sein oder eine vertragliche Beziehung zu einem externen Gerätediagramm haben müssen, um diese Optionen nutzen zu können. Die nachstehende Tabelle gibt einen Überblick darüber, wann eine Gerätediagrammoption gewählt werden soll. Für spezifische Anwendungsfälle siehe [Profillink-Gerätediagramm Verwendungsfälle](profile-link-use-case.md) und [Anwendungsfälle](external-graph-use-cases.md)für externe Gerätediagramme.

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Geräteschreibungsart </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Gerätediagramm für Profillink</span> </p> </td> 
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

Sehen Sie sich das unten stehende Video an, um einen Überblick über mögliche Anwendungsfälle für [!UICONTROL Profile Merge Rules]zu erhalten.

>[!VIDEO](https://video.tv.adobe.com/v/28975/?captions=ger)

>[!MORE_LIKE_THIS]
>
>* [Anwendungsfälle des Profillink-Gerätediagramms](profile-link-use-case.md)
>* [Anwendungsbeispiele für Diagramme externer Geräte](external-graph-use-cases.md)
>* [Häufig gestellte Fragen zu Regeln zur Profilzusammenführung](../../faq/faq-profile-merge.md)

