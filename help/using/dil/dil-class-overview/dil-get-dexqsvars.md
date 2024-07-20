---
description: Ruft einen bestimmten Wert von einem Anzeigen-Server ab.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 7%

---

# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>Ab Juli 2023 hat Adobe die Entwicklung der Erweiterung [!DNL Data Integration Library (DIL)] und der Erweiterung [!DNL DIL] eingestellt.
>
>Bestehende Kunden können weiterhin ihre [!DNL DIL] -Implementierung verwenden. Adobe wird jedoch nicht mehr [!DNL DIL] als bisher entwickeln. Kunden wird empfohlen, das [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) für ihre langfristige Datenerfassungsstrategie zu bewerten.
>
>Kunden, die nach Juli 2023 neue Datenerfassungs-Integrationen implementieren möchten, sollten stattdessen das [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) verwenden.

Ruft einen bestimmten Wert von einem Anzeigen-Server ab.

**Funktionssignatur:** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parameter**

| Name | Typ | Beschreibung |
|---|---|---|
| `variableName` | Zeichenfolge | Der Name der Variablen, für die Sie einen Wert abrufen möchten. |
| `partner` | Zeichenfolge | Der Name des zu suchenden Partners. |
| `containerNSID` | Ganzzahl | Der [!DNL NSID] des Containers, nach dem Sie suchen. Die Standardeinstellung ist `0`. |

**Antwort**

Gibt den Variablenwert für eine [!UICONTROL DIL] -Instanz zurück.

**Beispielcode**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
