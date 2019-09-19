---
description: Ruft einen bestimmten Wert von einem Anzeigen-Server ab.
seo-description: Ruft einen bestimmten Wert von einem Anzeigen-Server ab.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# dexGetQSVars{#dexgetqsvars}

Ruft einen bestimmten Wert von einem Anzeigen-Server ab.

**** Funktionssignatur: `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `variableName` | Zeichenfolge | Der Name der Variablen, für die Sie einen Wert abrufen möchten. |
| `partner` | Zeichenfolge | Der zu suchende Name des Partners. |
| `containerNSID` | Ganzzahl | Der Behälter, [!DNL NSID] nach dem Sie suchen. Die Standardeinstellung ist `0`. |

**Antwort**

Gibt den Variablenwert für eine [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
