---
description: Häufig gestellte Fragen zur Funktion "Zielgruppe Lab" .
seo-description: Häufig gestellte Fragen zur Funktion "Zielgruppe Lab" .
seo-title: Häufig gestellte Fragen zu Audience Lab
solution: Audience Manager
title: Häufig gestellte Fragen zu Audience Lab
topic: DIL-API
uuid: b 1 daf 99 d-af 60-4 f 65-987 d -794 a 6 d 45 d 566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab FAQ{#audience-lab-faq}

Häufig gestellte Fragen zur Funktion "Zielgruppe Lab" .

<!-- 

audience-lab-faq.xml

 -->

<br> 

**Verfügen die in den Testgruppen erstellten Testsegmente über verschiedene Segment-IDs? How do I map the IDs to different destinations?**

Ja, die Testsegmente verfügen über verschiedene Segment-IDs. For destinations with [!UICONTROL Auto-fill Destination Mapping] or segments sent to [!DNL Google], [!UICONTROL Audience Lab] will handle the mapping values just like the destinations normally would.

<br> 

**Kann dieselbe Konversionseigenschaft mit mehreren Testgruppen verknüpft werden?**

Ja, dies ist zulässig. Angenommen, ein Test verwendet ein männliches Segment, das mit Umrechnung X verknüpft ist, und einen Test mit einem weiblichen Segment, das mit Umrechnung X verknüpft ist. Es ist nicht wichtig, dass beide Tests zu Konversionen führen, da sie zwei verschiedene Zielgruppen testen.

<br> 

**Angenommen, eine Testgruppe verwendet ein authentifiziertes Profil für die Aufteilung des Testsegments. The authenticated profile is linked to 4[Audience Manager UUIDs](../reference/ids-in-aam.md). When the visitor exhibits a conversion trait from one of the four UUIDs, does[!UICONTROL Audience Lab]count this as one or four conversions?**

In this case, [!UICONTROL Audience Lab] only counts one conversion.

<br> 

**Was ist, wenn der Besucher aus dem oben stehenden Fall die Konversionseigenschaft aus einer der vier mit ihrem authentifizierten Profil verknüpften uuids zusammenstellt und dann die Konversionseigenschaft aus zwei weiteren uuids bereitstellt, die mit dem authentifizierten Profil verknüpft sind? Does this case count as one or three conversions?**

[!UICONTROL Audience Lab] Gezählt werden in diesem Fall drei Konversionen, eines für jedes Gerät, das die Authentifizierungseigenschaft ausgab.

<br> 

**Kann ein Benutzer[!UICONTROL Segment: Read-Only]Zugriff haben, aber[!UICONTROL Audience Lab]auch Segmenterstellungszugriff testen?**

See [Create Segment Test Group](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) for information on how to use [!UICONTROL Audience Lab] with [!UICONTROL RBAC] privileges.

**Kann[!UICONTROL Audience Lab]ich zusammen mit den[!UICONTROL Profile Link Device Graph]externen Gerätediagrammen ([Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html), Tapad Device Graph, Liveramp Device Graph) verwenden?**

For now, [!UICONTROL Audience Lab] can only split out segment populations by the devices connected to a qualifying device, when using the [!UICONTROL Profile Link Device Graph]. We are working on adding support in [!UICONTROL Audience Lab] for the other device graphs and will let you know when we do so.
