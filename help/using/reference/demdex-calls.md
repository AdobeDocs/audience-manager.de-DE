---
description: Audience Manager und der Adobe Experience Platform Identity-Dienst rufen die Domäne demdex.net auf und empfangen Daten. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber dies ist nicht der Fall. In diesem Abschnitt werden die Elemente in einem demdex.net -Aufruf beschrieben.
seo-description: Audience Manager and the Adobe Experience Platform Identity Service make calls to and receive data from the demdex.net domain. This may seem like Adobe is working with an unusual third-party domain, but this is not the case. This section describes the elements in a demdex.net call.
seo-title: Understanding Calls to the Demdex Domain
solution: Audience Manager
title: Aufrufe an die Domäne "demdex.net"
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: Reference
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 4%

---

# Aufrufe an die Domäne [!DNL Demdex] verstehen {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] und die [!DNL Adobe Experience Platform Identity Service] führen Aufrufe an und empfangen Daten von der `demdex.net` -Domäne. Dies mag so aussehen, als ob [!DNL Adobe] mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber dies ist nicht der Fall. In diesem Abschnitt werden die Elemente in einem `demdex.net` -Aufruf beschrieben.

| Aufrufelement | Beschreibung |
|---|---|
| `demdex.net` | Dies ist eine veraltete Domäne, die von [!DNL Adobe] kontrolliert wird. Sie spiegelt den ursprünglichen Namen vor der Akquise von [!DNL Audience Manager] ([!DNL Demdex]) wider. [!DNL Adobe] hat [!DNL Demdex] 2011 übernommen und das Unternehmen in [!DNL Audience Manager] umbenannt. Es ist schwierig, diese Domäne zu ändern, da sie tief mit [!DNL Audience Manager], dem [!DNL Adobe Experience Cloud ID Service] und unserer installierten Benutzerbasis verbunden ist. Möglicherweise werden weitere Präfixe an veraltete `demdex.net` -Aufrufe angehängt (z. B. `dcs.demdex.net`, `fast.demdex.net` usw.). Unabhängig vom Präfix ist ein Aufruf von `something.demdex.net` immer ein Aufruf von [!DNL Adobe] und nicht eine unbekannte oder verdächtige Drittanbieterdomäne. |
| `dpm` | [!DNL DPM] ist eine Abkürzung für [!DNL Data Provider Match]. Er teilt internen [!DNL Adobe]-Systemen mit, dass ein Aufruf von [!DNL Audience Manager] oder [!DNL Adobe Experience Cloud ID Service] Kundendaten zur Synchronisierung oder Anforderung einer ID übergibt. Dies ist der häufigste `demdex.net` -Aufruf, den Sie von [!DNL Audience Manager] oder der [!DNL Adobe Experience Cloud ID Service] sehen werden. Grundlagen zum <br><br>[!DNL DPM]-Aufruf: <ul><li>[!DNL Audience Manager]: Ein [!DNL DPM] -Aufruf von [!DNL Audience Manager] sendet Daten an die [!DNL Data Collection Servers] und [!DNL Profile Cache Servers]. Siehe [Datenerfassungskomponenten](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Ein [!DNL DPM] -Aufruf der [!DNL Adobe Experience Cloud ID Service] ist eine Anforderung einer Besucher-ID. Siehe [Cookies und der Adobe Experience Platform Identity-Dienst](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html) und [Anfordern und Festlegen von IDs durch den Adobe Experience Platform Identity-Dienst](https://experienceleague.adobe.com/docs/id-service/using/intro/id-request.html).</li></ul><br>Hinweis: [!DNL Adobe Experience Cloud ID Service] -Kunden können das Präfix [!DNL DPM] im Domänennamen ändern. Siehe [audienceManager Server und audienceManagerServerSecure](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity-Dienst](https://experienceleague.adobe.com/docs/id-service/using/home.html)
>* [Audience Manager-Cookies](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html)
