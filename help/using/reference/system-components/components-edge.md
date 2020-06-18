---
description: Audience Manager nutzt verteilte, modernste Computing-Topologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.
seo-description: Audience Manager nutzt verteilte, modernste Computing-Topologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.
seo-title: Das Edge Data Center
solution: Audience Manager
title: Das Edge Data Center
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---


# Das Edge Data Center{#understanding-the-edge-data-center}

Audience Manager nutzt verteilte, modernste Computing-Topologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.

## Grundlagen zum Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge-Computing bietet eine verbesserte Leistung als Reaktion auf eine diffuse, internetweite Nachfrage, da die &quot;Kante&quot;selbst eine globale Grenze ist. Dies bedeutet, dass die Verarbeitung dynamisch den Quellen der Nachfrage am nächsten [!DNL Audience Manager] liegt und Daten so schnell wie möglich zurückgegeben werden. Edge-Computing hilft bei der Aufrechterhaltung der Site-Performance, wodurch wiederum das Benutzererlebnis auf Ihrer Website erhalten bleibt. Das Edge-Rechenzentrum ist ein wichtiges Gateway zum Verschieben von Daten in und aus [!DNL Audience Manager]Daten.

Das [!DNL Audience Manager] Edge-Rechenzentrum umfasst:

* **Hauptserver:** Das sind die wichtigsten [!DNL Audience Manager] Systeme. Sie aktualisieren und stellen Daten für die Edge-Server bereit.

* **Edge-Server:** Normalerweise handelt es sich dabei um Anwendungs- und/oder Webserver. Sie sitzen an der Grenze zwischen [!DNL Audience Manager] dem Internet. Edge-Server, wie z. B. die [!DNL DCS] Akamai-Systeme, behandeln in der Regel Daten und Anforderungen, die in die und aus der Datenbank fließen [!DNL Audience Manager].

* **Lastenausgleich:** Verwalten Sie uneinheitliche Computing-/Verarbeitungsanforderungen, die mit Internetanwendungen verbunden sind. Diese Ausgleiche verhindern, dass Cluster von Servern überladen werden, während andere untätig bleiben.

Die folgende Abbildung zeigt die Umgebung des Rechenzentrums am Audience Manager.

![](assets/edge_data_center.png)

## Geografische Verteilung und Lastenausgleich {#geo-dist-balance}

Siehe [!DNL DCS] Abschnitt zu [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md).
