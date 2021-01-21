---
description: Audience Manager und der Adobe Experience Platform-Identitätsdienst rufen Daten von der Domäne demdex.net an und empfangen diese. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber das ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex.net-Aufrufs beschrieben.
seo-description: Audience Manager und der Adobe Experience Platform-Identitätsdienst rufen Daten von der Domäne demdex.net an und empfangen diese. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber das ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex.net-Aufrufs beschrieben.
seo-title: Grundlegendes zu Aufrufen an die Domäne „demdex.net“
solution: Audience Manager
title: Grundlegendes zu Aufrufen an die Domäne „demdex.net“
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 7286af6dd85a0464ccf52a88139d07cb151783e6
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 15%

---


# Aufrufe der [!DNL Demdex]-Domäne {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] und die  [!DNL Adobe Experience Platform Identity Service] Aufrufe an und empfangen Daten von der  `demdex.net` Domäne. Dies mag so aussehen, als würde [!DNL Adobe] mit einer ungewöhnlichen Drittanbieterdomäne arbeiten, aber das ist nicht der Fall. In diesem Abschnitt werden die Elemente eines `demdex.net`-Aufrufs beschrieben.

| Call-Element | Beschreibung |
|---|---|
| `demdex.net` | Dies ist eine Legacy-Domäne, die von [!DNL Adobe] gesteuert wird. Es spiegelt den ursprünglichen Namen vor der Akquise von [!DNL Audience Manager] ([!DNL Demdex]) wider. [!DNL Adobe] hat [!DNL Demdex] 2011 übernommen und das Unternehmen in [!DNL Audience Manager] umbenannt. Es ist schwierig, diese Domäne zu ändern, da sie tief mit [!DNL Audience Manager], der [!DNL Adobe Experience Cloud ID Service] und unserer installierten Benutzerbasis verknüpft ist. Andere Präfixe, die an Legacy-Aufrufe von `demdex.net` angehängt sind (z. B. `dcs.demdex.net`, `fast.demdex.net` usw.), werden möglicherweise angezeigt. Unabhängig vom Präfix ist ein Aufruf von `something.demdex.net` immer ein Aufruf von [!DNL Adobe] und nicht eine unbekannte oder verdächtige Drittanbieterdomäne. |
| `dpm` | [!DNL DPM] ist eine Abkürzung für  [!DNL Data Provider Match]. Es teilt internen Systemen mit, dass ein Aufruf von [!DNL Audience Manager] oder [!DNL Adobe Experience Cloud ID Service] Kundendaten zur Synchronisierung weitergibt oder eine ID anfordert. [!DNL Adobe] Dies ist der häufigste `demdex.net`-Aufruf, den Sie von [!DNL Audience Manager] oder dem [!DNL Adobe Experience Cloud ID Service] sehen werden. <br><br>[!DNL DPM] Aufruf - Grundlagen <ul><li>[!DNL Audience Manager]: Ein  [!DNL DPM] Aufruf von  [!DNL Audience Manager] sendet Daten an das  [!DNL Data Collection Servers] und  [!DNL Profile Cache Servers]. Siehe [Datenerfassungskomponenten](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Ein  [!DNL DPM] Aufruf der  [!DNL Adobe Experience Cloud ID Service] ist eine Anforderung einer Besucher-ID. Siehe [Cookies und den Adobe Experience Platform-Identitätsdienst](https://docs.adobe.com/content/help/de-DE/id-service/using/intro/cookies.html) und [Anfordern und Festlegen von IDs](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html) durch den Adobe Experience Platform-Identitätsdienst.</li></ul><br>Hinweis:  [!DNL Adobe Experience Cloud ID Service] Kunden können das  [!DNL DPM] Präfix im Domänennamen ändern. Siehe [audienceManager Server und audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookies in Audience Manager](https://docs.adobe.com/content/help/de-DE/core-services/interface/ec-cookies/cookies-am.html)

