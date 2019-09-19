---
description: Ruft eine Partner-spezifische DIL-Instanz ab.
keywords: Audience Manager API;aam API;Audience Manager-API;aam-API
seo-description: Ruft eine Partner-spezifische DIL-Instanz ab.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# getDil{#getdil}

Ruft eine Partner-spezifische DIL-Instanz ab.

**** Funktionssignatur: `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parameter

| Name | Typ | Beschreibung |
|---|---|---|
| `partner` | Zeichenfolge | Der zu suchende Name des Partners. |
| `containerNSID` | Ganzzahl | Die Standardeinstellung ist `0`. Die NSID des Containers, nach dem Sie suchen. Optional. |

## Antwort

Eine erfolgreiche Partner- und Container-NSID-Übereinstimmung gibt eine Partner-spezifische [!UICONTROL DIL] Instanz zurück. Wenn keine Übereinstimmung vorliegt, gibt die API einen Fehler mit der Meldung `The DIL instance with partner <name> and containerNSID <ID> was not found.`"

## Beispielcode

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
