---
description: Mit den Optionen für Profilzusammenführungsrichtlinien können Sie den Zielgruppenfokus auf bestimmte Zielgruppen basierend auf Geschäftsanforderungen oder Zielen erweitern oder einschränken. In diesen allgemeinen Anwendungsfällen wird untersucht, wie Sie verfügbare Optionen verwenden und Zusammenführungsregeln für individuelles, häusliches und geräteübergreifendes Targeting erstellen können.
seo-description: Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting.
seo-title: General Use Cases for Profile Merge Rules
solution: Audience Manager
title: Allgemeine Anwendungsfälle für Profilzusammenführungsrichtlinien
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 2%

---

# Allgemeine Anwendungsfälle für Profilzusammenführungsrichtlinien {#general-use-cases-for-profile-merge-rules}

[!UICONTROL Profile Merge Rules] Mit diesen Optionen können Sie den Fokus der Zielgruppe auf bestimmte Zielgruppen entsprechend den geschäftlichen Anforderungen oder Zielen erweitern oder einschränken. In diesen allgemeinen Anwendungsfällen wird untersucht, wie Sie verfügbare Optionen verwenden und Zusammenführungsregeln für individuelles, häusliches und geräteübergreifendes Targeting erstellen können. [!UICONTROL Profile Merge Rules] mit Echtzeit- und Batch-Zielen arbeiten.

>[!TIP]
>
>Definitionen und Beschreibungen dieser [!UICONTROL Merge Rule] Einstellungen, siehe [Definierte Optionen für Profilzusammenführungsregeln](merge-rule-definitions.md).

## Geräte-Targeting {#device-personalization}

Dieses Szenario gilt für Marketingexperten, die ein einzelnes Geräteprofil für ein in Audience Manager definiertes Zielgruppensegment auswerten möchten, um dem Gerät ein konsistentes Erlebnis mit Zielplattformen zu bieten, die Geräte-IDs unterstützen (DSP, On-site-Personalisierungsplattformen und andere gerätebasierte Targeting-Plattformen), wobei die Benutzerauthentifizierung nicht berücksichtigt wird.

Um eine Regel zu erstellen, die nur für Geräteprofile bestimmt ist, wählen Sie **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![device-only](assets/device-only.png)

Angenommen, John besitzt drei Smartphones. Zwei davon sind iPhone 7s im Datenplan A, und eines davon ist Samsung im Datenplan B. Da er seinen Authentifizierungsstatus auf keinem der drei Geräte berücksichtigt, möchte John&#39;s Mobilfunkanbieter ihm ein Upgrade des Datenplans anbieten, sondern nur für iPhone 7-Geräte, die auf Datenplan A laufen.

Durch Verwendung der Variablen **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** Regel, [!DNL Device 1] und [!DNL Device 3] beide sind für das Segment qualifiziert, während Gerät 2 ignoriert wird.

![device-only](assets/device-management.png)

## Freigegebenes Geräte-Targeting {#target-shared-devices}

Nehmen wir an, John und seine Frau Jane, verwenden denselben Laptop, um einen Onlineshop zu besuchen und verschiedene Artikel zu bestellen.

John nutzt sein eigenes Konto, um Reisetickets und Sonderangebote zu buchen, während Jane ihr eigenes Konto für Musik und Filme nutzt.

Das Marketing-Team des Stores kann die **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** Regel verwenden, um John und Jane mit bestimmten Angeboten auszuwählen, die ausschließlich auf ihrer authentifizierten Aktivität basieren.

![current-no-device](assets/current-no-device.png)

Durch die Verwendung dieser Regel ignoriert Audience Manager das Geräteprofil vollständig, qualifiziert die CRM-ID von John für das Segment und qualifiziert nicht die CRM-ID von Jane.

![shared-device-targeting](assets/shared-device-targeting.png)

## Online-/Offline-Targeting {#device-household-targeting}

Dieser Anwendungsfall umfasst das Identitätsmanagement von Haushalten. Ein Unternehmen kann mithilfe der **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]** Regel.

![last-device-profile](assets/last-device-profile.png)

Betrachten wir ein Segment aus Haushalten mit einem Einkommen von über 100.000 US-Dollar pro Jahr, das mindestens ein Gerät enthält, das ein [!DNL iPhone 7] on [!DNL Data Plan B]. Wir haben zwei Haushaltsprofile (geräteübergreifende Profile), die jeweils mit zwei verschiedenen Geräteprofilen verbunden sind. Die Eigenschaften, die für die Qualifizierung für das Segment erforderlich sind, werden über die Geräte- und geräteübergreifenden Profile verteilt.

Audience Manager führt jedes Geräte- und geräteübergreifende Profilpaar zusammen, um zu sehen, ob der zusammengeführte Satz von Eigenschaften für das Segment qualifiziert ist. Da Audience Manager jedes Profil auswertet, das in der Zusammenführung enthalten war, können sowohl ein Geräteprofil als auch ein Haushaltsprofil segmentiert werden.

Die Verknüpfung zwischen Gerät und Haushaltsprofil ermöglicht es dem Audience Manager, [!DNL Household 2] für das Segment, jedoch nicht [!DNL Household 1]. Von [!DNL Household 2], nur [!DNL Device 3] qualifiziert sich für das Segment. Diese [!UICONTROL Profile Merge Rule] Marketing-Experten können einem einzelnen Gerät eine konsistente Marketing-Botschaft senden ([!DNL Device 3]) und dem weiteren Haushalt ([!DNL Household 2]).

![Haushaltsführung](assets/household-management.png)

## Targeting für personenbasierte Ziele {#all-cross-device}

>[!IMPORTANT]
>
>Dieser Artikel enthält die Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um rechtliche Hinweise zu erhalten.

Dieses Targeting-Szenario ist nur für Kunden verfügbar, die die [!DNL People-Based Destinations] -Add-on. Diese Regel ermöglicht es Marketingexperten, Kunden basierend auf ihren eigenen, authentifizierten Daten zu erreichen.

Nehmen wir an, ein Online-Einzelhändler möchte bestehende Kunden über soziale Plattformen erreichen und ihnen personalisierte Angebote basierend auf ihren bisherigen Bestellungen zeigen. Mit [!UICONTROL People-Based Destinations], können sie Hash-E-Mail-Adressen von ihren eigenen erfassen [!DNL CRM] Erstellen Sie in Audience Manager Segmente aus den Offline-Daten und senden Sie diese Segmente an die Social-Plattformen, für die sie werben möchten. Verwenden Sie hierzu die Hash-Kennung und optimieren Sie ihre Werbeausgaben.

Weitere Informationen zu dieser Option finden Sie unter [Benutzerbasierte Ziele](../destinations/people-based-destinations-overview.md).

![geräteübergreifend](assets/all-cross-device.png)

## Gerätediagrammoptionen {#device-graph-options}

Auswählen einer [!UICONTROL device graph] -Option für eine [!UICONTROL Profile Merge] -Regel hängt von Bedingungen ab, die für Ihre digitalen Eigenschaften und Geschäftsziele eindeutig sind. Diese allgemeinen Richtlinien helfen Ihnen dabei zu verstehen, wann ein Diagrammtyp im Vergleich zu einem anderen verwendet werden soll. Beachten Sie, dass Sie über eine vertragliche Beziehung zu einem externen Gerätediagramm verfügen müssen, um diese Optionen verwenden zu können. In der folgenden Tabelle finden Sie allgemeine Hinweise dazu, wann eine Gerätediagrammoption ausgewählt werden soll. Spezifische Anwendungsfälle finden Sie unter [Anwendungsfälle für das Profil-Link-Gerätediagramm](profile-link-use-case.md) und [Anwendungsfälle für externe Gerätediagramme](external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gerätediagramm-Typ </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Gerätediagramm für Profilverknüpfung</span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Profilzusammenführung</span> -Regeln, die mit der <span class="wintitle"> Profillink</span> -Option eignet sich ideal für: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Digitale Eigenschaften mit einer allgemeinen Kundenauthentifizierung. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Gezielte Kampagnen mit geringer Reichweite. Die <span class="wintitle"> Profillink</span> Gerätediagramm basiert nur auf deterministischen Daten. Dieser Pool von Geräteprofilen ist immer kleiner im Verhältnis zum Pool nicht authentifizierter Benutzer und Geräte. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Anwendungsfälle, in denen Kunden sich in einem authentifizierten Status befinden müssen, um für die Segmentierung qualifiziert zu sein. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Grafikoptionen für externe Geräte </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> Profilzusammenführung</span> Regeln, die mit einem beliebigen externen Gerätediagramm integriert wurden in <span class="keyword"> Audience Manager</span> sind ideal für: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Digitale Eigenschaften mit geringer Kundenauthentifizierung. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Umfassende Markenkampagnen mit hoher Reichweite. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Anwendungsfälle, in denen Kunden nicht authentifiziert sein müssen, um für die Segmentierung qualifiziert zu sein. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Im folgenden Video erhalten Sie einen Überblick über mögliche Anwendungsfälle für [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Anwendungsfälle für das Profil-Link-Gerätediagramm](profile-link-use-case.md)
>* [Anwendungsfälle für externe Gerätediagramme](external-graph-use-cases.md)
>* [Häufig gestellte Fragen zu Profilzusammenführungsregeln](../../faq/faq-profile-merge.md)

