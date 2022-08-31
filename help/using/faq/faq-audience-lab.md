---
description: Häufig gestellte Fragen zur Audience Lab-Funktion.
seo-description: Frequently asked questions about the Audience Lab feature.
seo-title: Audience Lab FAQ
solution: Audience Manager
title: Häufig gestellte Fragen zu Audience Lab
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
feature: Audience Lab
exl-id: 25bdabb5-2ba8-45d2-81ca-05c0590d7d96
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 94%

---

# Häufig gestellte Fragen zu Audience Lab{#audience-lab-faq}

Häufig gestellte Fragen zur Audience Lab-Funktion.

<br>

**Haben die in den Testgruppen erstellten Testsegmente unterschiedliche Segment-IDs? Wie ordne ich die IDs verschiedenen Zielen zu?**

Ja, die Testsegmente haben unterschiedliche Segment-IDs. Bei Zielen mit [!UICONTROL Auto-fill Destination Mapping] oder Segmenten, die an [!DNL Google] gesendet werden, behandelt [!UICONTROL Audience Lab] die Zuordnungswerte genauso wie die Ziele.

<br> 

**Kann dieselbe Konversionseigenschaft mit mehreren Testgruppen verknüpft werden?**

Ja, das ist zulässig. Stellen Sie sich einen Fall vor, bei dem ein Test ein männliches Segment verwendet, das der Konversion X zugeordnet ist, und ein Test ein weibliches Segment, das der Konversion X zugeordnet ist. Es spielt keine Rolle, dass beide Tests Konversionen vorantreiben, da sie zwei unterschiedliche Zielgruppen testen.

<br> 

**Angenommen, eine Testgruppe verwendet ein authentifiziertes Profil für die Testsegmentaufteilung. Das authentifizierte Profil ist mit 4 [Audience Manager-UUIDs](../reference/ids-in-aam.md) verknüpft. Wenn der Besucher eine Konversionseigenschaft aus einer der vier UUIDs aufweist, zählt [!UICONTROL Audience Lab] dies dann als eine oder vier Konversionen?**

In diesem Fall zählt [!UICONTROL Audience Lab] nur eine Konversion.

<br> 

**Was passiert, wenn der Besucher aus dem obigen Fall zuerst die Konversionseigenschaft einer der vier mit seinem authentifizierten Profil verknüpften UUIDs und dann auch die Konversionseigenschaft von zwei anderen mit dem authentifizierten Profil verknüpften UUIDs aufweist? Zählt dieser Fall als eine oder drei Konversionen?**

In diesem Fall zählt [!UICONTROL Audience Lab] drei Konversionen, eine für jedes Gerät, das die Authentifizierungseigenschaft gezeigt hat.

<br> 

**Kann ein Benutzer [!UICONTROL Segment: Read-Only] Zugriff, aber gleichzeitig auch Zugriff zur Erstellung von Testsegmenten in [!UICONTROL Audience Lab] haben?**

Weitere Informationen zur Nutzung von [!UICONTROL Audience Lab] mit [!UICONTROL RBAC]-Rechten finden Sie unter [Erstellen von Segmenttestgruppen](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups).

**Kann ich [!UICONTROL Audience Lab] in Verbindung mit [!UICONTROL Profile Link Device Graph] und externe Gerätediagramme ( Tapad Device Graph, Liveramp Device Graph)?**

Derzeit kann [!UICONTROL Audience Lab] bei Verwendung von [!UICONTROL Profile Link Device Graph] nur Segmentpopulationen nach Geräten aufteilen, die mit einem qualifizierenden Gerät verbunden sind. Wir arbeiten daran, die anderen Gerätediagramme in [!UICONTROL Audience Lab] zu unterstützen, und werden Sie darüber informieren, sobald dies der Fall ist.
