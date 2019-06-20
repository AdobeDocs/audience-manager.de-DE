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


# Häufig gestellte Fragen zu Audience Lab{#audience-lab-faq}

Häufig gestellte Fragen zur Funktion &quot;Zielgruppe Lab&quot; .

<!-- 

audience-lab-faq.xml

 -->

<br> 

**Verfügen die in den Testgruppen erstellten Testsegmente über verschiedene Segment-IDs? Wie kann ich die IDs unterschiedlichen Zielen zuordnen?**

Ja, die Testsegmente verfügen über verschiedene Segment-IDs. Bei Zielen mit [!UICONTROL Auto-fill Destination Mapping] oder Segmenten, an die [!DNL Google][!UICONTROL Audience Lab] gesendet wird, werden die Zuordnungswerte genau wie die Ziele behandelt.

<br> 

**Kann dieselbe Konversionseigenschaft mit mehreren Testgruppen verknüpft werden?**

Ja, dies ist zulässig. Angenommen, ein Test verwendet ein männliches Segment, das mit Umrechnung X verknüpft ist, und einen Test mit einem weiblichen Segment, das mit Umrechnung X verknüpft ist. Es ist nicht wichtig, dass beide Tests zu Konversionen führen, da sie zwei verschiedene Zielgruppen testen.

<br> 

**Angenommen, eine Testgruppe verwendet ein authentifiziertes Profil für die Aufteilung des Testsegments. Das authentifizierte Profil ist mit 4[Audience Manager-uuids verknüpft](../reference/ids-in-aam.md). Wenn der Besucher eine Konversionseigenschaft aus einer der vier uuids bereitstellt,[!UICONTROL Audience Lab]zählt dies als eine oder vier Konversionen?**

In diesem Fall [!UICONTROL Audience Lab] zählt nur eine Konversion.

<br> 

**Was ist, wenn der Besucher aus dem oben stehenden Fall die Konversionseigenschaft aus einer der vier mit ihrem authentifizierten Profil verknüpften uuids zusammenstellt und dann die Konversionseigenschaft aus zwei weiteren uuids bereitstellt, die mit dem authentifizierten Profil verknüpft sind? Zählt dies als eine oder drei Konversionen?**

[!UICONTROL Audience Lab] Gezählt werden in diesem Fall drei Konversionen, eines für jedes Gerät, das die Authentifizierungseigenschaft ausgab.

<br> 

**Kann ein Benutzer[!UICONTROL Segment: Read-Only]Zugriff haben, aber[!UICONTROL Audience Lab]auch Segmenterstellungszugriff testen?**

Informationen [zur Verwendung](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) [!UICONTROL Audience Lab] mit [!UICONTROL RBAC] Berechtigungen finden Sie unter Segment-Testgruppe erstellen.

**Kann[!UICONTROL Audience Lab]ich zusammen mit den[!UICONTROL Profile Link Device Graph]externen Gerätediagrammen ([Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html), Tapad Device Graph, Liveramp Device Graph) verwenden?**

Zur Zeit [!UICONTROL Audience Lab] können Sie Segmente nur durch die Geräte teilen, die mit einem qualifizierenden Gerät verbunden sind, bei Verwendung des [!UICONTROL Profile Link Device Graph]. Wir arbeiten daran, Unterstützung für [!UICONTROL Audience Lab] die anderen Gerätediagramme hinzuzufügen, und teilen Ihnen mit, wann wir dies tun.
