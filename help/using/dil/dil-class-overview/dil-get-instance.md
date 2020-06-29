---
description: Ruft eine Partner-spezifische DIL-Instanz ab.
keywords: audience manager api;aam api;audience manager apis;aam apis
seo-description: Ruft eine Partner-spezifische DIL-Instanz ab.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 13%

---


# getDil{#getdil}

Ruft eine Partner-spezifische DIL-Instanz ab.

**Funktionssignatur:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parameter

| Name | Typ | Beschreibung |
|---|---|---|
| `partner` | Zeichenfolge | Der zu suchende Name des Partners. |
| `containerNSID` | Ganzzahl | Die Standardeinstellung ist `0`. Die NSID des Containers, nach dem Sie suchen. Optional. |

## Antwort

Eine erfolgreiche Partner- und Container-NSID-Übereinstimmung gibt eine Partner-spezifische [!UICONTROL DIL] Instanz zurück. Wenn keine Übereinstimmung vorliegt, gibt die API einen Fehler mit der Meldung `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Beispielcode

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
