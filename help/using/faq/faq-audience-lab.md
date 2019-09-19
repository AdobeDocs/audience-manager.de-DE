---
description: Häufig gestellte Fragen zur Funktion "Audience Lab"
seo-description: Häufig gestellte Fragen zur Funktion "Audience Lab"
seo-title: Häufig gestellte Fragen zu Audience Lab
solution: Audience Manager
title: Häufig gestellte Fragen zu Audience Lab
topic: DIL-API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Häufig gestellte Fragen zu Audience Lab{#audience-lab-faq}

Häufig gestellte Fragen zur Funktion "Audience Lab"

<!-- 

audience-lab-faq.xml

 -->

<br> 

**Haben die in den Testgruppen erstellten Testsegmente unterschiedliche Segment-IDs? Wie ordnen Sie die IDs verschiedenen Zielen zu?**

Ja, die Testsegmente haben unterschiedliche Segment-IDs. Bei Zielen mit [!UICONTROL Auto-fill Destination Mapping] oder Segmenten, die an gesendet werden, [!DNL Google] [!UICONTROL Audience Lab]werden die Zuordnungswerte wie bei den Zielen normalerweise verarbeitet.

<br> 

**Kann dieselbe Konversionseigenschaft mit mehreren Testgruppen verknüpft werden?**

Ja, das ist erlaubt. Man denke an einen Fall eines Tests mit einem männlichen Segment, das mit Konversion X verbunden ist, und einen Test mit einem weiblichen Segment, das mit Konversion X verbunden ist. Es spielt keine Rolle, dass beide Tests Konversionen fördern, da sie zwei verschiedene Zielgruppen testen.

<br> 

**Angenommen, eine Testgruppe verwendet ein authentifiziertes Profil für die Teilung des Testsegments. Das authentifizierte Profil ist mit 4[Audience Manager-UUIDs](../reference/ids-in-aam.md)verknüpft. Wenn der Besucher eine Konversionseigenschaft aus einer der vier UUIDs aufweist, zählt[!UICONTROL Audience Lab]dies als eine oder vier Konversionen?**

In diesem Fall zählt [!UICONTROL Audience Lab] nur eine Konversion.

<br> 

**Was ist, wenn der Besucher aus dem oben stehenden Fall zuerst die Konversionseigenschaft einer der vier UUUIDs, die mit ihrem authentifizierten Profil verknüpft sind, anzeigt und dann auch die Konversionseigenschaft zweier anderer UUIDs, die mit dem authentifizierten Profil verknüpft sind, zeigt? Zählt dieser Fall als eine oder drei Konversionen?**

In diesem Fall werden drei Konvertierungen [!UICONTROL Audience Lab] gezählt, eine für jedes Gerät, das die Authentifizierungsmerkmale gezeigt hat.

<br> 

**Kann ein Benutzer[!UICONTROL Segment: Read-Only]Zugriff auf die Segmenterstellung haben und gleichzeitig Zugriff auf die[!UICONTROL Audience Lab]Segmenterstellung haben?**

Informationen zur Verwendung [ mit ](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) Berechtigungen finden Sie unter Segmenttestgruppe[!UICONTROL Audience Lab] [!UICONTROL RBAC]erstellen.

**Kann ich[!UICONTROL Audience Lab]in Verbindung mit den Diagrammen[!UICONTROL Profile Link Device Graph]und externen Geräten ([Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html), Bandgerät Graph, Liveramp Device Graph) verwenden?**

Derzeit [!UICONTROL Audience Lab] können Segmentpopulationen nur durch die Geräte, die an ein qualifizierendes Gerät angeschlossen sind, aufgeteilt werden, wenn die [!UICONTROL Profile Link Device Graph]Variable verwendet wird. Wir arbeiten daran, Unterstützung [!UICONTROL Audience Lab] für die anderen Gerätediagramme hinzuzufügen und werden Sie darüber informieren, wenn wir dies tun.
