---
description: Ruft eine Partnerspezifische DIL-Instanz ab.
keywords: audience manager api;aam api;audience manager apis;aam apis
seo-description: Ruft eine Partnerspezifische DIL-Instanz ab.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 17%

---


# getDil{#getdil}

Ruft eine Partnerspezifische DIL-Instanz ab.

**Funktionssignatur:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parameter

| Name | Typ | Beschreibung |
|---|---|---|
| `partner` | Zeichenfolge | Der zu suchende Name des Partners. |
| `containerNSID` | Ganzzahl | Die Standardeinstellung ist `0`. Die NSID des Containers, nach dem Sie suchen. Optional. |

## Antwort

Bei einer erfolgreichen Partner- und Container-NSID-Übereinstimmung wird eine Partnerinstanz [!UICONTROL DIL] zurückgegeben. Wenn keine Übereinstimmung vorliegt, gibt die API einen Fehler mit der Meldung &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;zurück (gibt diesen nicht aus).

## Beispielcode

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
