---
description: Mit den Optionen für Profil Merge Rules können Sie die Audience je nach Geschäftsanforderungen oder Geschäftszielen auf bestimmte Audiencen ausweiten oder verschärfen. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden können, und es werden Regeln zum Zusammenführen von Targeting für einzelne Geräte, Haushalte und Geräte erstellt.
seo-description: Mit den Optionen für Profil Merge Rules können Sie die Audience je nach Geschäftsanforderungen oder Geschäftszielen auf bestimmte Audiencen ausweiten oder verschärfen. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden können, und es werden Regeln zum Zusammenführen von Targeting für einzelne Geräte, Haushalte und Geräte erstellt.
seo-title: Allgemeine Anwendungsfälle für Profilzusammenführungsrichtlinien
solution: Audience Manager
title: Allgemeine Anwendungsfälle für Profilzusammenführungsrichtlinien
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profil-Zusammenführung
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '999'
ht-degree: 4%

---

# Allgemeine Anwendungsfälle für Profilzusammenführungsrichtlinien {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] Mit diesen Optionen können Sie die Audience je nach Geschäftsanforderungen oder Geschäftszielen auf bestimmte Audiencen ausweiten oder verstärken. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden können, und es werden Regeln zum Zusammenführen von Targeting für einzelne Geräte, Haushalte und Geräte erstellt. [!UICONTROL Profile Merge Rules] mit Echtzeit- und Stapelzielen arbeiten.

>[!TIP]
>
>Definitionen und Beschreibungen dieser [!UICONTROL Merge Rule]-Einstellungen finden Sie unter [Profil Merge Rule Options Defined](merge-rule-definitions.md).

## Geräte-Targeting {#device-personalization}

Dieses Szenario gilt für Marketingexperten, die ein einzelnes Gerätesegment für ein in Audience Manager definiertes Audiencen-Profil auswerten möchten, um eine konsistente Darstellung für das  mithilfe von Targeting-Plattformen bereitzustellen, die Geräte-IDs (DSP, Onsite-Personalisierungsplattformen und andere gerätebasierte Targeting-Plattformen) unterstützen, wobei die Benutzerauthentifizierung nicht berücksichtigt wird.

Um eine Regel zu erstellen, die nur Profil des Geräts Zielgruppe, wählen Sie **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![device-only](assets/device-only.png)

Nehmen wir an, John besitzt drei Smartphones. Zwei davon sind iPhone 7s auf Data Plan A, und einer von ihnen ist ein Samsung auf Data Plan B. John&#39;s Mobilnetzbetreiber, der seinen Authentifizierungsstatus auf keinem der drei Geräte berücksichtigt, möchte ihm ein Upgrade auf den Datenplan anbieten, jedoch nur für iPhone 7-Geräte, die auf Datenplan A ausgeführt werden.

Durch die Verwendung der Regel **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** sind [!DNL Device 1] und [!DNL Device 3] für das Segment qualifiziert, während Gerät 2 ignoriert wird.

![device-only](assets/device-management.png)

## Freigegebenes Geräte-Targeting {#target-shared-devices}

Nehmen wir an, John und seine Frau Jane, benutzen den gleichen Laptop, um einen Online-Shop zu besuchen und verschiedene Artikel zu bestellen.

John nutzt sein eigenes Konto, um Reisetickets und Sonderangebote zu buchen, während Jane ihr eigenes Konto für Musik und Filme nutzt.

Das Marketingteam des Stores kann die **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]**-Regel verwenden, um John und Jane mit bestimmten Geschäften zu Zielgruppe, die ausschließlich auf ihrer authentifizierten Aktivität basieren.

![current-no-device](assets/current-no-device.png)

Durch die Verwendung dieser Regel ignoriert Audience Manager das Profil des Geräts vollständig und qualifiziert die CRM-ID von John für das Segment und nicht die CRM-ID von Jane.

![shared-device-targeting](assets/shared-device-targeting.png)

## Online-/Offline-Targeting {#device-household-targeting}

Dieser Anwendungsfall umfasst das Identitätsmanagement von Haushalten. Eine Firma kann ein einzelnes Profil mit dem letzten Profil zusammenführen, das auf diesem Gerät authentifiziert wurde, indem die **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]**-Regel verwendet wird.

![last-device-Profil](assets/last-device-profile.png)

Betrachten wir ein Segment, das aus Haushalten mit einem Einkommen von mehr als 100.000 US-Dollar pro Jahr besteht und mindestens ein Gerät enthält, das ein [!DNL iPhone 7] bei [!DNL Data Plan B] ist. Wir haben zwei Profil (geräteübergreifende Profil), die jeweils an zwei verschiedene Geräte-Profil angeschlossen sind. Die für die Segmentqualifizierung erforderlichen Eigenschaften werden über Geräte- und geräteübergreifende Profil verteilt.

Audience Manager führt alle Geräte- und geräteübergreifenden Profil-Paare zusammen, um festzustellen, ob der zusammengeführte Eigenschaftensatz für das Segment geeignet ist. Da Audience Manager jedes Profil auswertet, das in der Zusammenführung enthalten war, können sowohl ein Geräte-Profil als auch ein Profil für den Haushalt segmentiert werden.

Die Verknüpfung zwischen dem Profil &quot;device&quot;und dem Haushaltssegment ermöglicht es dem Audience Manager, [!DNL Household 2] für das Segment zu qualifizieren, jedoch nicht [!DNL Household 1]. Von [!DNL Household 2] qualifiziert sich nur [!DNL Device 3] für das Segment. Durch dieses [!UICONTROL Profile Merge Rule]-Ereignis kann der Marketingspezialist eine konsistente Marketingbotschaft an ein einzelnes Gerät ([!DNL Device 3]) und den weiteren Haushalt ([!DNL Household 2]) senden.

![Haushaltsführung](assets/household-management.png)

## Targeting für benutzerspezifische Ziele {#all-cross-device}

>[!IMPORTANT]
>
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Dieses Targeting-Szenario steht nur Kunden zur Verfügung, die das [!DNL People-Based Destinations]-Add-on gekauft haben. Diese Regel ermöglicht es Marketingexperten, Kunden anhand ihrer eigenen, authentifizierten Daten zu erreichen.

Nehmen wir einmal an, ein Online-Händler möchte über soziale Plattformen zu bestehenden Kunden gelangen und ihnen personalisierte Angebot auf Basis ihrer bisherigen Bestellungen zeigen. Mit [!UICONTROL People-Based Destinations] können sie Hash-E-Mail-Adressen von ihren eigenen [!DNL CRM]-Adressen in Audience Manager aufnehmen, Segmente aus den Offlinedaten erstellen und diese Segmente an die Social-Plattformen senden, für die sie Werbung machen möchten, indem sie diesen Hash-Bezeichner verwenden und ihre Werbeausgaben optimieren.

Weitere Informationen zu dieser Option finden Sie unter [Benutzerbasierte Ziele](../destinations/people-based-destinations-overview.md).

![all-cross-device](assets/all-cross-device.png)

## Gerätediagrammoptionen {#device-graph-options}

Die Auswahl einer [!UICONTROL device graph]-Option für eine [!UICONTROL Profile Merge]-Regel hängt von Bedingungen ab, die für Ihre digitalen Eigenschaften und Geschäftsziele eindeutig sind. Diese allgemeinen Richtlinien helfen Ihnen dabei, zu verstehen, wann ein Diagrammtyp im Vergleich zu einem anderen verwendet werden soll. Beachten Sie, dass Sie Mitglied der [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/de-DE/device-co-op/using/home.html) sein müssen oder eine vertragliche Beziehung zu einem externen Gerätediagramm haben müssen, um diese Optionen nutzen zu können. Die nachstehende Tabelle gibt einen Überblick darüber, wann eine Gerätediagrammoption gewählt werden soll. Für spezifische Anwendungsfälle siehe [Anwendungsfälle für Profil-Link-Gerätediagramme](profile-link-use-case.md) und [Anwendungsfälle für externe Gerätediagramme](external-graph-use-cases.md).

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
   <td colname="col2"> <p><span class="wintitle"> Profil </span> Mergerules, die mit der  <span class="wintitle"> Profil </span> Linkoption erstellt wurden, eignen sich ideal für: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Digitale Eigenschaften mit einer hohen Kundenauthentifizierung. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Fokussierte Kampagnen mit geringer Reichweite. Das Gerätediagramm <span class="wintitle"> Profil Link</span> basiert ausschließlich auf deterministischen Daten. Dieser Pool an Profilen ist immer kleiner im Verhältnis zum Pool nicht authentifizierter Benutzer und Geräte. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Anwendungsfälle, in denen Kunden sich in einem authentifizierten Zustand befinden müssen, um sich für die Segmentierung zu qualifizieren. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Optionen für externe Gerätediagramme </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Profil </span> Mergerules, die mit dem  <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co </a> oder einem externen Gerätediagramm mit  <span class="keyword"> Audience </span> Manager erstellt wurden, eignen sich ideal für: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Digitale Eigenschaften mit niedriger Kundenauthentifizierung. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Umfassende Kampagnen mit hoher Reichweite. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Anwendungsfälle, bei denen Kunden sich nicht in einem authentifizierten Zustand befinden müssen, um sich für die Segmentierung zu qualifizieren. </li> 
     </ul> </p> <p> <p>Tipp: Die <span class="keyword"> Device Co-op</span> ist Ihre beste Option, wenn Sie ein <span class="keyword">-Experience Cloud</span> mit niedriger Authentifizierung sind und keine Beziehung zu einem Device Graph Provider haben. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

Sehen Sie sich das unten stehende Video an, um einen Überblick über mögliche Anwendungsfälle für [!UICONTROL Profile Merge Rules] zu erhalten.

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Anwendungsfälle für das Profil-Link-Gerätediagramm](profile-link-use-case.md)
>* [Anwendungsfälle für externe Gerätediagramme](external-graph-use-cases.md)
>* [Häufig gestellte Fragen zu Profil-Zusammenführungsregeln](../../faq/faq-profile-merge.md)

