---
description: Ruft eine partnerspezifische DIL-Instanz ab.
keywords: Audience Manager API; aam-API; Audience Manager apis; aam-apis
seo-description: Ruft eine partnerspezifische DIL-Instanz ab.
seo-title: Getdil
solution: Audience Manager
title: Getdil
uuid: 7 b 95 f 9 bf -14 c 0-4 c 74-b 6 b 9-d 6 b 38513 d 487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Getdil{#getdil}

Ruft eine partnerspezifische DIL-Instanz ab.

**Funktionssignatur:**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parameter

| Name | Typ | Beschreibung |
|---|---|---|
| `partner` | Zeichenfolge | Der zu suchende Partnername. |
| `containerNSID` | Ganzzahl | Standardeinstellungen `0`sind. Die NSID des Containers, nach dem Sie suchen. Optional. |

## Antwort

Eine erfolgreiche Partner- und Container-NSID-Übereinstimmung gibt eine partnerspezifische [!UICONTROL DIL] Instanz zurück. Wenn keine Übereinstimmung vorhanden ist, gibt die API einen Fehler mit der Meldung " `The DIL instance with partner <name> and containerNSID <ID> was not found.`«

## Beispielcode

<pre class="java"><code>DIL. getdil ('<i>partner</i>', <i>containernsid</i>); 
DIL. getdil ('<i>partner</i>');</code></pre>
