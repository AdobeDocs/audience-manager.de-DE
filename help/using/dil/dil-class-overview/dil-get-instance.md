---
description: Ruft eine Partner-spezifische DIL-Instanz ab.
keywords: Audience Manager-API;AAM-API;Audience Manager-API;AAM-API
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%

---

# getDil{#getdil}

>[!WARNING]
>
>Ab Juli 2023 hat die Adobe die Entwicklung der [!DNL Data Integration Library (DIL)] und [!DNL DIL] -Erweiterung.
><br><br>
>Bestehende Kunden können weiterhin ihre [!DNL DIL] Implementierung. Die Adobe wird sich jedoch nicht entwickeln [!DNL DIL] über diesen Punkt hinaus. Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) für ihre langfristige Datenerfassungsstrategie.
><br><br>
>Kunden, die nach Juli 2023 neue Datenerfassungs-Integrationen implementieren möchten, sollten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) anstatt.

Ruft eine Partner-spezifische DIL-Instanz ab.

**Funktionssignatur:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parameter

| Name | Typ | Beschreibung |
|---|---|---|
| `partner` | Zeichenfolge | Der Partnername, nach dem gesucht werden soll. |
| `containerNSID` | Ganzzahl | Die Standardeinstellung ist `0`. Die NSID des Containers, nach dem Sie suchen. Optional. |

## Antwort

Eine erfolgreiche Partner- und Container-NSID-Übereinstimmung gibt eine Partner-spezifische [!UICONTROL DIL] -Instanz. Wenn keine Übereinstimmung vorliegt, gibt die API einen Fehler mit der Meldung zurück (gibt diesen nicht aus): &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Beispielcode

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
