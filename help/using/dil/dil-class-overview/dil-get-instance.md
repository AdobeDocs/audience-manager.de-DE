---
description: Ruft eine partnerspezifische DIL-Instanz ab.
keywords: Audience Manager API; aam-API; Audience Manager apis; aam-apis
seo-description: Ruft eine partnerspezifische DIL-Instanz ab.
seo-title: Getdil
solution: Audience Manager
title: Getdil
uuid: 7 b 95 f 9 bf -14 c 0-4 c 74-b 6 b 9-d 6 b 38513 d 487
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# getDil{#getdil}

Ruft eine partnerspezifische DIL-Instanz ab.

**Funktionssignatur:**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parameter

| Name | Typ | Beschreibung |
|---|---|---|
| `partner` | Zeichenfolge | Der zu suchende Partnername. |
| `containerNSID` | Ganzzahl | Defaults is `0`. Die NSID des Containers, nach dem Sie suchen. Optional. |

## Antwort

A successful partner and container NSID match returns a partner-specific [!UICONTROL DIL] instance. If there is no match, the API returns (does not throw) an error with the message, &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Beispielcode

<pre class="java"><code>DIL. getdil ('<i>partner</i>', <i>containernsid</i>); 
DIL. getdil ('<i>partner</i>');</code>
</pre>
