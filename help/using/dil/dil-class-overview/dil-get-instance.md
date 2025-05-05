---
description: Ruft eine partnerspezifische DIL-Instanz ab.
keywords: Audience Manager-API;AAM-API;Audience Manager-APIs;AAM-APIs
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 6%

---

# getDil{#getdil}

>[!WARNING]
>
>Ab Juli 2023 hat Adobe die Entwicklung des [!DNL Data Integration Library (DIL)] und der [!DNL DIL] eingestellt.
>
>Bestehende Kundinnen und Kunden können ihre [!DNL DIL] Implementierung weiterhin nutzen. Allerdings wird sich Adobe nicht über diesen Punkt hinaus [!DNL DIL] entwickeln. Kunden wird empfohlen, [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de) auf ihre langfristige Datenerfassungsstrategie hin zu überprüfen.
>
>Kunden, die nach Juli 2023 neue Datenerfassungsintegrationen implementieren möchten, sollten stattdessen [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de) verwenden.

Ruft eine partnerspezifische DIL-Instanz ab.

**Funktionssignatur:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parameter

| Name | Typ | Beschreibung |
|---|---|---|
| `partner` | Zeichenfolge | Der zu suchende Partnername. |
| `containerNSID` | Ganzzahl | Die Standardeinstellung ist `0`. Die NSID des gesuchten Containers. Optional. |

## Antwort

Eine erfolgreiche Partner- und Container-NSID-Übereinstimmung gibt eine partnerspezifische [!UICONTROL DIL] zurück. Wenn keine Übereinstimmung vorliegt, gibt die API einen Fehler mit der Meldung &quot;`The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot; zurück (gibt ihn nicht aus)

## Beispielcode

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
