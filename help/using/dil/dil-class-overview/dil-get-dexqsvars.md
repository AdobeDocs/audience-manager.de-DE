---
description: Ruft einen bestimmten Wert von einem Anzeigen-Server ab.
seo-description: Ruft einen bestimmten Wert von einem Anzeigen-Server ab.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL-Implementierung
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 17%

---

# dexGetQSVars{#dexgetqsvars}

Ruft einen bestimmten Wert von einem Anzeigen-Server ab.

**Funktionssignatur:** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `variableName` | Zeichenfolge | Der Name der Variablen, für die Sie einen Wert abrufen möchten. |
| `partner` | Zeichenfolge | Der Partnername, nach dem gesucht werden soll. |
| `containerNSID` | Ganzzahl | Die [!DNL NSID] des Containers, nach dem Sie suchen. Die Standardeinstellung ist `0`. |

**Antwort**

Gibt den Variablenwert für eine [!UICONTROL DIL]-Instanz zurück.

**Beispielcode**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
