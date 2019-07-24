---
description: Audience Manager verwendet verteilte Edge-Rechnertopologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.
seo-description: Audience Manager verwendet verteilte Edge-Rechnertopologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.
seo-title: Das Edge Data Center
solution: Audience Manager
title: Das Edge Data Center
uuid: 4177 e 666-99 f 4-453 d -94 dd -58 c 6182 c 8 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Understanding the Edge Data Center{#understanding-the-edge-data-center}

Audience Manager verwendet verteilte Edge-Rechnertopologien, um die Anforderungen an unsere Systeme durch externe Quellen zu erfüllen.

## Edge Data Center Basics {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Die Leistung von Edge-Rechnern bietet eine verbesserte Leistung als Reaktion auf eine diffuse Internetbreite, da die "edge" selbst eine globale Grenze ist. This means [!DNL Audience Manager] dynamically places processing closest to the sources of demand and returns data by the shortest possible path. Mit der Edge-Datenbank bleibt die Site-Performance erhalten, die wiederum die Benutzererfahrung auf Ihrer Website beibehält. The edge data center is a key gateway for moving data in and out of [!DNL Audience Manager].

The [!DNL Audience Manager] edge data center includes:

* **Core-Server:** Dies sind die [!DNL Audience Manager] Hauptsysteme. Sie aktualisieren und liefern Daten an die Edge-Server.

* **Edge Server:** Normalerweise sind dies Anwendungen und/oder Webserver. They sit at the boundary between [!DNL Audience Manager] and the Internet. Edge servers, such as the [!UICONTROL DCS] or Akamai systems, typically handle data and requests flowing into and out of [!DNL Audience Manager].

* **Lastenausgleich:** Ungleichmäßige Verarbeitungs-/Verarbeitungsanforderungen in Internetanwendungen verwalten. Diese Balken verhindern, dass Servercluster überlastet werden, während andere inaktiv bleiben.

Das folgende Diagramm veranschaulicht die Edge Manager-Edge-Datencenter-Umgebung.

![](assets/edge_data_center.png)

## Geographic Distribution and Load Balancing {#geo-dist-balance}

See the [!UICONTROL DCS] section in [Data Collection Components](../../reference/system-components/components-data-collection.md).
