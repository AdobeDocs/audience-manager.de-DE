---
description: Mit den Optionen für Profilzusammenführungsregeln können Sie den Zielgruppenfokus auf bestimmte Zielgruppen basierend auf geschäftlichen Anforderungen oder Zielen erweitern oder verschärfen. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden und wie Zusammenführungsregeln für das Targeting von Einzelpersonen, Haushalten und Geräten erstellt werden.
seo-description: Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting.
seo-title: General Use Cases for Profile Merge Rules
solution: Audience Manager
title: Allgemeine Anwendungsfälle für Profilzusammenführungsregeln
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 1%

---

# Allgemeine Anwendungsfälle für Profilzusammenführungsregeln {#general-use-cases-for-profile-merge-rules}

Mit [!UICONTROL Profile Merge Rules] Optionen können Sie die Zielgruppe entsprechend den Geschäftsanforderungen oder -zielen auf bestimmte Zielgruppen ausdehnen oder einschränken. In diesen allgemeinen Anwendungsfällen wird untersucht, wie die verfügbaren Optionen verwendet werden und wie Zusammenführungsregeln für das Targeting von Einzelpersonen, Haushalten und Geräten erstellt werden. [!UICONTROL Profile Merge Rules] arbeiten mit Echtzeit- und Batch-Zielen.

>[!TIP]
>
>Definitionen und Beschreibungen dieser [!UICONTROL Merge Rule] finden Sie unter [Optionen für Profilzusammenführungsregeln definiert](merge-rule-definitions.md).

## Geräte-Targeting {#device-personalization}

Dieses Szenario gilt für Marketing-Fachleute, die ein einzelnes Geräteprofil für ein in Audience Manager definiertes Zielgruppensegment auswerten möchten, um dem Gerät ein konsistentes Erlebnis mithilfe von Zielgruppenbestimmungsplattformen bereitzustellen, die Geräte-IDs unterstützen (DSP, Personalisierungsplattformen auf der Site und andere gerätebasierte Zielgruppenbestimmungsplattformen), wobei die Benutzerauthentifizierung nicht berücksichtigt wird.

Um eine Regel zu erstellen, die nur auf Geräteprofile abzielt, wählen Sie **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** aus.

![nur für Geräte](assets/device-only.png)

Angenommen, John besitzt drei Smartphones. Zwei von ihnen sind iPhone 7s auf Data Plan A, und einer von ihnen ist ein Samsung auf Data Plan B. Ohne Berücksichtigung seines authentifizierten Status auf einem der drei Geräte möchte Johns Mobilnetzbetreiber ihm ein Upgrade für den Datenplan anbieten, aber nur für iPhone 7-Geräte, die auf Data Plan A laufen.

Bei Verwendung der **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**-Regel qualifizieren sich sowohl [!DNL Device 1] als auch [!DNL Device 3] für das Segment, während Gerät 2 ignoriert wird.

![nur für Geräte](assets/device-management.png)

## Freigegebenes Geräte-Targeting {#target-shared-devices}

Nehmen wir an, John und seine Frau Jane benutzen denselben Laptop, um einen Online-Shop zu besuchen und verschiedene Artikel zu bestellen.

John verwendet sein eigenes Konto, um Reisetickets und Sonderangebote zu buchen, während Jane ihr eigenes Konto verwendet, um für Musik und Filme einzukaufen.

Das Marketing-Team des Stores kann die Regel **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** verwenden, um John und Jane mit bestimmten Angeboten anzusprechen, die ausschließlich auf ihrer authentifizierten Aktivität basieren.

![current-no-device](assets/current-no-device.png)

Durch die Verwendung dieser Regel ignoriert Audience Manager das Geräteprofil vollständig, qualifiziert Johns CRM-ID für das Segment und nicht Janes CRM-ID.

![shared-device-targeting](assets/shared-device-targeting.png)

## Online-/Offline-Targeting {#device-household-targeting}

Dieser Anwendungsfall umfasst das Identitätsmanagement von Haushalten. Ein Unternehmen kann mithilfe der **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]**-Regel ein einzelnes Geräteprofil mit dem letzten Profil zusammenführen, das sich auf diesem Gerät authentifiziert hat.

![last-device-profile](assets/last-device-profile.png)

Betrachten wir ein Segment, das aus Haushalten mit einem Einkommen von mehr als 100.000 US-Dollar pro Jahr besteht und mindestens ein Gerät enthält, das ein [!DNL iPhone 7] auf [!DNL Data Plan B] ist. Wir haben zwei Haushaltsprofile (geräteübergreifende Profile), die jeweils mit zwei verschiedenen Geräteprofilen verbunden sind. Die für die Qualifizierung für das Segment erforderlichen Eigenschaften sind über die Geräte- und geräteübergreifenden Profile verteilt.

Audience Manager führt jedes Geräte- und geräteübergreifende Profilpaar zusammen, um zu sehen, ob der zusammengeführte Satz von Eigenschaften für das Segment geeignet ist. Da der Audience Manager jedes Profil auswertet, das bei der Zusammenführung enthalten war, können sowohl ein Geräteprofil als auch ein Haushaltsprofil segmentiert werden.

Durch die Verknüpfung zwischen dem Gerät und dem Haushaltsprofil kann der Audience Manager [!DNL Household 2] für das Segment qualifizieren, aber nicht [!DNL Household 1]. Ab [!DNL Household 2] qualifiziert sich nur [!DNL Device 3] für das Segment. Diese [!UICONTROL Profile Merge Rule] hat es dem Marketing-Experten ermöglicht, eine konsistente Marketing-Botschaft an ein einzelnes Gerät ([!DNL Device 3]) und den Haushalt ([!DNL Household 2]) zu senden.

![Haushaltsführung](assets/household-management.png)

## Targeting für personenbasierte Ziele {#all-cross-device}

>[!IMPORTANT]
>
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Verwendung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um Rechtsberatung zu erhalten.

Dieses Targeting-Szenario steht nur Kunden zur Verfügung, die das Add-on [!DNL People-Based Destinations] erworben haben. Diese Regel ermöglicht es Marketing-Experten, Kunden basierend auf ihren eigenen, authentifizierten Daten zu erreichen.

Angenommen, ein Online-Händler möchte bestehende Kunden über soziale Plattformen erreichen und ihnen personalisierte Angebote auf Grundlage ihrer vorherigen Bestellungen zeigen. Mit [!UICONTROL People-Based Destinations] können sie Hash-E-Mail-Adressen aus ihren eigenen [!DNL CRM] in den Audience Manager aufnehmen, Segmente aus den Offline-Daten erstellen und diese Segmente an die sozialen Plattformen senden, auf denen sie werben möchten, und dabei diese Hash-Kennung verwenden, wodurch ihre Werbeausgaben optimiert werden.

Weitere Informationen zu dieser Option finden Sie [Personenbasierte Ziele](../destinations/people-based-destinations-overview.md).

![Alle geräteübergreifenden](assets/all-cross-device.png)

## Gerätediagramm-Optionen {#device-graph-options}

Die Auswahl einer [!UICONTROL device graph] Option für eine [!UICONTROL Profile Merge] hängt von Bedingungen ab, die für Ihre digitalen Eigenschaften und Geschäftsziele eindeutig sind. Diese allgemeinen Richtlinien können Ihnen dabei helfen zu verstehen, wann ein Diagrammtyp im Vergleich zu einem anderen verwendet werden sollte. Beachten Sie, dass Sie eine vertragliche Beziehung mit einem externen Gerätediagramm haben müssen, um diese Optionen verwenden zu können. Die folgende Tabelle enthält allgemeine Anleitungen dazu, wann eine Option für das Gerätediagramm ausgewählt werden sollte. Für bestimmte Anwendungsfälle finden Sie [Anwendungsfälle für Profilverknüpfungsgerätediagramme](profile-link-use-case.md) und [Anwendungsfälle für externe Gerätediagramme](external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Diagrammtyp des Geräts </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> des Profilverknüpfungsgeräts</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Profilzusammenführung </span> Regeln, die mit der Option <span class="wintitle"> Profillink erstellt </span>, ideal für: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Digitale Eigenschaften mit einem hohen Maß an Kundenauthentifizierung. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Fokussierte Kampagnen mit geringer Reichweite. Das Gerätediagramm <span class="wintitle"> Profillink</span> wird nur auf deterministischen Daten erstellt. Dieser Pool von Geräteprofilen ist im Verhältnis zum Pool nicht authentifizierter Benutzer und Geräte immer kleiner. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Anwendungsfälle, bei denen sich Kundinnen und Kunden in einem authentifizierten Zustand befinden müssen, um sich für die Segmentierung zu qualifizieren. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Diagrammoptionen für externe Geräte </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Profilzusammenführung</span> Regeln, die mit einem beliebigen externen Gerätediagramm erstellt wurden, das in <span class="keyword"> Audience Manager integriert </span>, eignen sich ideal für: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Digitale Eigenschaften mit einer niedrigen Ebene der Kundenauthentifizierung. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Umfassende, weit reichende Markenkampagnen. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Anwendungsfälle, bei denen sich Kundinnen und Kunden nicht im authentifizierten Zustand befinden müssen, um sich für die Segmentierung zu qualifizieren. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Sehen Sie sich das folgende Video an, um einen Überblick über mögliche Anwendungsfälle für [!UICONTROL Profile Merge Rules] zu erhalten.

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Anwendungsfälle für das Profil-Link-Gerätediagramm](profile-link-use-case.md)
>* [Anwendungsfälle für externe Gerätediagramme](external-graph-use-cases.md)
>* [Häufig gestellte Fragen zu Profilzusammenführungsregeln](../../faq/faq-profile-merge.md)
