---
description: Audience Manager und der Adobe Experience Platform Identity Service rufen Daten von der Domain demdex.net auf und empfangen diese. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Domain eines Drittanbieters arbeitet, aber dem ist nicht so. In diesem Abschnitt werden die Elemente in einem demdex.net-Aufruf beschrieben.
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Aufrufe an die Demdex-Domain
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 4%

---

# Aufrufe an die [!DNL Demdex] Domain {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] und der [!DNL Adobe Experience Platform Identity Service] rufen an und empfangen Daten von der `demdex.net` Domain. Dies mag so aussehen, als würde [!DNL Adobe] mit einer ungewöhnlichen Domain eines Drittanbieters arbeiten, aber dem ist nicht so. In diesem Abschnitt werden die Elemente in einem `demdex.net` beschrieben.

| Aufrufelement | Beschreibung |
|---|---|
| `demdex.net` | Dies ist eine ältere von [!DNL Adobe] verwaltete Domain. Es spiegelt den ursprünglichen Namen von [!DNL Audience Manager] ([!DNL Demdex]) vor der Akquise wider. [!DNL Adobe] hat [!DNL Demdex] 2011 übernommen und das Unternehmen in [!DNL Audience Manager] umbenannt. Es ist schwierig, diese Domain zu ändern, da sie eng mit [!DNL Audience Manager], der [!DNL Adobe Experience Cloud ID Service] und unserer installierten Benutzerbasis verknüpft ist. Möglicherweise werden andere Präfixe an ältere `demdex.net`-Aufrufe angehängt (z. B. `dcs.demdex.net`, `fast.demdex.net` usw.). Unabhängig vom Präfix ist ein Aufruf von `something.demdex.net` immer ein Aufruf an [!DNL Adobe] und nicht an eine unbekannte oder verdächtige Drittanbieterdomäne. |
| `dpm` | [!DNL DPM] ist eine Abkürzung für [!DNL Data Provider Match]. Es teilt internen, [!DNL Adobe] Systemen mit, dass ein Aufruf von [!DNL Audience Manager] oder der [!DNL Adobe Experience Cloud ID Service] Kundendaten zur Synchronisierung oder zur Anforderung einer ID weitergibt. Dies ist der häufigste `demdex.net`, den Sie von [!DNL Audience Manager] oder der [!DNL Adobe Experience Cloud ID Service] aus sehen. Grundlagen <br><br>[!DNL DPM] Aufrufe: <ul><li>[!DNL Audience Manager]: Ein [!DNL DPM] Aufruf von [!DNL Audience Manager] sendet Daten an die [!DNL Data Collection Servers] und [!DNL Profile Cache Servers]. Siehe [Datenerfassungskomponenten](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Ein [!DNL DPM] Aufruf des [!DNL Adobe Experience Cloud ID Service] ist eine Anfrage nach einer Besucher-ID. Siehe [Cookies und der Adobe Experience Platform Identity &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=de) und [Wie der Adobe Experience Platform Identity Service IDs anfordert und festlegt](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html?lang=de).</li></ul><br>Hinweis: [!DNL Adobe Experience Cloud ID Service] Kunden können das [!DNL DPM] Präfix im Domain-Namen ändern. Siehe [audienceManager Server und audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html?lang=de). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=de)
>* [Audience Manager-Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html?lang=de)
