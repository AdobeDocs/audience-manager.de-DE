---
description: Audience Manager verwendet verteilte, ausgereifte Computertopologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: Grundlagen zum Edge Data Center
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Grundlagen zum Edge Data Center{#understanding-the-edge-data-center}

Audience Manager verwendet verteilte, ausgereifte Computertopologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.

## Grundlagen zum Edge-Rechenzentrum {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge-Computing bietet eine verbesserte Leistung als Reaktion auf eine diffuse, internetweite Nachfrage, da der &quot;Edge&quot;selbst eine globale Grenze darstellt. Das bedeutet, dass [!DNL Audience Manager] die Verarbeitung dynamisch den Nachfragequellen am nächsten platziert und Daten über den kürzestmöglichen Pfad zurückgibt. Edge-Computing hilft bei der Aufrechterhaltung der Site-Performance, wodurch wiederum das Benutzererlebnis auf Ihrer Website erhalten bleibt. Das Edge-Rechenzentrum ist ein wichtiges Gateway zum Verschieben von Daten in und aus [!DNL Audience Manager].

Das Edge-Rechenzentrum [!DNL Audience Manager] umfasst:

* **Core-Server:** Dies sind die wichtigsten [!DNL Audience Manager] Systeme. Sie aktualisieren und stellen Daten für die Edge-Server bereit.

* **Edge-Server:** Normalerweise handelt es sich hierbei um Anwendungs- und/oder Webserver. Sie sitzen an der Grenze zwischen [!DNL Audience Manager] und dem Internet. Edge-Server, wie z. B. die [!DNL DCS]- oder Akamai-Systeme, verarbeiten normalerweise Daten und Anforderungen, die in und aus [!DNL Audience Manager] fließen.

* **Lastenausgleich:** Verwalten Sie unausgewogene Computer-/Verarbeitungsanforderungen, die mit Internetanwendungen verbunden sind. Diese Ausgleichssysteme verhindern, dass Servercluster überlastet werden, während andere inaktiv bleiben.

Die folgende Abbildung zeigt die Audience Manager Edge-Rechenzentrumsumgebung.

![](assets/edge_data_center.png)

## Geografische Verteilung und Lastenausgleich {#geo-dist-balance}

Siehe Abschnitt [!DNL DCS] in [Datenerfassungskomponenten](../../reference/system-components/components-data-collection.md).
