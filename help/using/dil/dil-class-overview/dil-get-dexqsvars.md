---
description: Ruft einen bestimmten Wert von einem Anzeigenserver ab.
seo-description: Ruft einen bestimmten Wert von einem Anzeigenserver ab.
seo-title: Dexgetqsvars
solution: Audience Manager
title: Dexgetqsvars
uuid: 6 d 21 c 7 a 4-43 f 8-456 b -8831-47343 dbb 047 e
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# Dexgetqsvars{#dexgetqsvars}

Ruft einen bestimmten Wert von einem Anzeigenserver ab.

**Funktionssignatur:**`dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `variableName` | Zeichenfolge | Der Name der Variablen, für die Sie einen Wert erhalten möchten. |
| `partner` | Zeichenfolge | Der zu suchende Partnername. |
| `containerNSID` | Ganzzahl | Der [!DNL NSID] Container, nach dem Sie suchen. Standardeinstellungen `0`sind. |

**Antwort**

Gibt den Variablenwert für eine [!UICONTROL DIL] Instanz zurück.

**Beispielcode**

<pre class="java"><code>var value = DIL. dexgetqsvars ('<i>variablename</i>','<i>partnername</i>',<i>containernsid</i>);</code>
</pre>
