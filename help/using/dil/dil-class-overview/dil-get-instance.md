---
description: Ruft eine Partner-spezifische DIL-Instanz ab.
keywords: Audience Manager-API;AAM-API;Audience Manager-API;AAM-API
seo-description: Ruft eine Partner-spezifische DIL-Instanz ab.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL-Implementierung
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%

---

# getDil{#getdil}

Ruft eine Partner-spezifische DIL-Instanz ab.

**Funktionssignatur:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parameter

| Name | Typ | Beschreibung |
|---|---|---|
| `partner` | Zeichenfolge | Der Partnername, nach dem gesucht werden soll. |
| `containerNSID` | Ganzzahl | Die Standardeinstellung ist `0`. Die NSID des Containers, nach dem Sie suchen. Optional. |

## Antwort

Eine erfolgreiche Partner- und Container-NSID-Übereinstimmung gibt eine Partner-spezifische [!UICONTROL DIL]-Instanz zurück. Wenn keine Übereinstimmung vorliegt, gibt die API einen Fehler mit der Meldung &quot;`The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;zurück (gibt diesen nicht aus).

## Beispielcode

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
