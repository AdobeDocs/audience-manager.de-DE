---
description: Mit den Optionen für Profil Merge Rules können Sie die Audience je nach Geschäftsanforderungen oder Geschäftszielen auf bestimmte Audiencen ausweiten oder verschärfen. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden können, und es werden Regeln zum Zusammenführen von Targeting für einzelne Geräte, Haushalte und Geräte erstellt.
seo-description: Mit den Optionen für Profil Merge Rules können Sie die Audience je nach Geschäftsanforderungen oder Geschäftszielen auf bestimmte Audiencen ausweiten oder verschärfen. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden können, und es werden Regeln zum Zusammenführen von Targeting für einzelne Geräte, Haushalte und Geräte erstellt.
seo-title: Allgemeine Anwendungsfälle für Profil-Zusammenführungsregeln
solution: Audience Manager
title: Allgemeine Anwendungsfälle für Profil-Zusammenführungsregeln
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Allgemeine Anwendungsfälle für Profil-Zusammenführungsregeln {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] Mit diesen Optionen können Sie die Audience je nach Geschäftsanforderungen oder Geschäftszielen auf bestimmte Audiencen ausweiten oder verstärken. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden können, und es werden Regeln zum Zusammenführen von Targeting für einzelne Geräte, Haushalte und Geräte erstellt. [!UICONTROL Profile Merge Rules] mit Echtzeit- und Stapelzielen arbeiten.

>[!TIP]
>
>Definitionen und Beschreibungen dieser [!UICONTROL Merge Rule] Einstellungen finden Sie unter Optionen für die [Profil-Zusammenführung definiert](merge-rule-definitions.md).

## Geräte-Targeting {#device-personalization}

Dieses Szenario gilt für Marketingexperten, die ein einzelnes Gerätesegment für ein in Audience Manager definiertes Audiencen-Profil auswerten möchten, um eine konsistente Geräteerfahrung mit Targeting-Plattformen zu erzielen, die Geräte-IDs (DSPs, Personalisierungsplattformen vor Ort und andere gerätebasierte Targeting-Plattformen) unterstützen, wobei die Benutzerauthentifizierung nicht berücksichtigt wird.

Um eine Regel zu erstellen, die nur Profil des Geräts Zielgruppe, wählen Sie **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![device-only](assets/device-only.png)

Nehmen wir an, John besitzt drei Smartphones. Zwei davon sind iPhone 7s auf Data Plan A, und einer von ihnen ist ein Samsung auf Data Plan B. John&#39;s Mobilnetzbetreiber, der seinen Authentifizierungsstatus auf keinem der drei Geräte berücksichtigt, möchte ihm ein Upgrade auf den Datenplan anbieten, jedoch nur für iPhone 7-Geräte, die auf Datenplan A ausgeführt werden.

Durch die Verwendung der **[!UICONTROL No Cross-Device Profile]** +- **[!UICONTROL Device Profile]** Regel [!DNL Device 1] und [!DNL Device 3] beide sind für das Segment qualifiziert, während Device 2 ignoriert wird.

![device-only](assets/device-management.png)

## Freigegebenes Geräte-Targeting {#target-shared-devices}

Nehmen wir an, John und seine Frau Jane, verwenden Sie denselben Laptop, um einen Online-Shop zu besuchen und verschiedene Artikel zu bestellen.

John nutzt sein eigenes Konto, um Reisetickets und Sonderangebote zu buchen, während Jane ihr eigenes Konto für Musik und Filme nutzt.

Das Marketing-Team des Geschäfts kann die **[!UICONTROL Current Authenticated Profiles]** +- **[!UICONTROL No Device Profile]** Regel verwenden, um John und Jane mit bestimmten Geschäften zu Zielgruppe, die ausschließlich auf ihrer authentifizierten Aktivität basieren.

![current-no-device](assets/current-no-device.png)

Durch die Verwendung dieser Regel ignoriert Audience Manager vollständig das Profil des Geräts, indem John die CRM-ID für das Segment qualifiziert und Janes CRM-ID nicht qualifiziert wird.

![shared-device-targeting](assets/shared-device-targeting.png)

## Online-/Offline-Targeting {#device-household-targeting}

Dieser Anwendungsfall umfasst das Identitätsmanagement von Haushalten. Eine Firma kann ein einzelnes Profil mit dem letzten Profil zusammenführen, das auf diesem Gerät authentifiziert wurde, indem sie die Regel **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** verwendet.

![last-device-Profil](assets/last-device-profile.png)

Betrachten wir ein Segment, das aus Haushalten mit einem Einkommen von über 100.000 US-Dollar pro Jahr besteht und mindestens ein Gerät enthält, das ein [!DNL iPhone 7] on ist [!DNL Data Plan B]. Wir haben zwei Profil (geräteübergreifende Profil), die jeweils an zwei verschiedene Geräte-Profil angeschlossen sind. Die für die Segmentqualifizierung erforderlichen Eigenschaften werden über Geräte- und geräteübergreifende Profil verteilt.

Audience Manager führt alle Geräte- und geräteübergreifenden Profil-Paare zusammen, um festzustellen, ob der zusammengeführte Eigenschaftensatz für das Segment geeignet ist. Da Audience Manager jedes Profil auswertet, das in der Zusammenführung enthalten war, können sowohl ein Geräte-Profil als auch ein Profil für den Haushalt segmentiert werden.

Die Verbindung zwischen dem Profil und dem Haushaltsgerät ermöglicht es Audience Manager, sich [!DNL Household 2] für das Segment zu qualifizieren, jedoch nicht [!DNL Household 1]. Von [!DNL Household 2]hier aus qualifiziert sich nur [!DNL Device 3] das Segment. Dadurch [!UICONTROL Profile Merge Rule] konnte der Marketingspezialist eine einheitliche Marketingbotschaft an ein einzelnes Gerät ([!DNL Device 3]) und den weiteren Haushalt ([!DNL Household 2]) senden.

![Haushaltsführung](assets/household-management.png)

## Targeting für benutzerspezifische Ziele {#all-cross-device}

>[!IMPORTANT]
>
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Dieses Targeting-Szenario steht nur Kunden zur Verfügung, die das [!DNL People-Based Destinations] Add-on gekauft haben. Diese Regel ermöglicht es Marketingexperten, Kunden anhand ihrer eigenen, authentifizierten Daten zu erreichen.

Nehmen wir einmal an, ein Online-Händler möchte über soziale Plattformen zu bestehenden Kunden gelangen und ihnen personalisierte Angebot auf Basis ihrer bisherigen Bestellungen zeigen. Mit [!UICONTROL People-Based Destinations]dieser Funktion können sie Hash-E-Mail-Adressen von sich aus [!DNL CRM] in Audience Manager erfassen, Segmente aus den Offlinedaten erstellen und diese Segmente an die Social-Plattformen senden, für die sie werben möchten, indem sie diese Hash-ID verwenden und ihre Werbeausgaben optimieren.

Weitere Informationen zu dieser Option finden Sie unter [Benutzerbasierte Ziele](../destinations/people-based-destinations-overview.md).

![all-cross-device](assets/all-cross-device.png)

## Gerätediagrammoptionen {#device-graph-options}

Die Auswahl einer [!UICONTROL device graph] Option für eine [!UICONTROL Profile Merge] Regel hängt von Bedingungen ab, die für Ihre digitalen Eigenschaften und Geschäftsziele spezifisch sind. Diese allgemeinen Richtlinien helfen Ihnen dabei, zu verstehen, wann ein Diagrammtyp im Vergleich zu einem anderen verwendet werden soll. Beachten Sie, dass Sie Mitglied der [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) sein oder eine vertragliche Beziehung zu einem externen Gerätediagramm haben müssen, um diese Optionen nutzen zu können. Die nachstehende Tabelle gibt einen Überblick darüber, wann eine Gerätediagrammoption gewählt werden soll. Für spezifische Anwendungsfälle siehe Anwendungsfälle [und Anwendungsfälle für](profile-link-use-case.md) Profil-Link-Gerätediagramme [](external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Geräteschreibungsart </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Gerätediagramm für Profil-Link</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Profil Merge</span> -Regeln, die mit der Option <span class="wintitle"> Profil Link</span> erstellt wurden, eignen sich ideal für: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Digitale Eigenschaften mit einer hohen Kundenauthentifizierung. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Fokussierte Kampagnen mit geringer Reichweite. Das Gerätediagramm <span class="wintitle"> Profil Link</span> basiert ausschließlich auf deterministischen Daten. Dieser Pool an Profilen ist immer kleiner im Verhältnis zum Pool nicht authentifizierter Benutzer und Geräte. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Anwendungsfälle, in denen Kunden sich in einem authentifizierten Zustand befinden müssen, um sich für die Segmentierung zu qualifizieren. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Optionen für externe Gerätediagramme </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Profil Merge</span> -Regeln, die mit der <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud-Gerätekooperation</a> oder einem externen Gerätediagramm in <span class="keyword"> Audience Manager</span> erstellt wurden, eignen sich ideal für: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Digitale Eigenschaften mit niedriger Kundenauthentifizierung. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Umfassende Kampagnen mit hoher Reichweite. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Anwendungsfälle, bei denen Kunden sich nicht in einem authentifizierten Zustand befinden müssen, um sich für die Segmentierung zu qualifizieren. </li> 
     </ul> </p> <p> <p>Tipp: Die <span class="keyword"> Gerätekooperation</span> ist die beste Option, wenn Sie ein <span class="keyword"> Experience Cloud</span> -Kunde mit niedriger Authentifizierung und keiner Beziehung zu einem Device Graph Provider sind. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

Sehen Sie sich das unten stehende Video an, um einen Überblick über mögliche Anwendungsfälle für [!UICONTROL Profile Merge Rules]zu erhalten.

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Anwendungsfälle für Profil Link Device Graph](profile-link-use-case.md)
>* [Anwendungsbeispiele für Diagramme externer Geräte](external-graph-use-cases.md)
>* [Häufig gestellte Fragen zu Profil-Zusammenführungsregeln](../../faq/faq-profile-merge.md)

