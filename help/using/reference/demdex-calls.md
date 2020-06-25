---
description: Audience Manager und der Identitätsdienst der Adobe Experience Platform rufen Daten von der Domäne demdex.net an und empfangen diese. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber das ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex.net-Aufrufs beschrieben.
seo-description: Audience Manager und der Identitätsdienst der Adobe Experience Platform rufen Daten von der Domäne demdex.net an und empfangen diese. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber das ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex.net-Aufrufs beschrieben.
seo-title: 'Aufrufe an die Domäne „demdex.net“ '
solution: Audience Manager
title: 'Aufrufe an die Domäne „demdex.net“ '
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 4%

---


# Understanding Calls to the [!DNL Demdex] Domain {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] und die [!DNL Adobe Experience Platform Identity Service] Aufrufe an und empfangen Daten von der `demdex.net` Domäne. Dies mag so aussehen, als [!DNL Adobe] arbeite man mit einer ungewöhnlichen Drittanbieterdomäne, aber das ist nicht der Fall. In diesem Abschnitt werden die Elemente in einem `demdex.net` Aufruf beschrieben.

| Call-Element | Beschreibung |
|---|---|
| `demdex.net` | Dies ist eine Legacy-Domäne, die von [!DNL Adobe]gesteuert wird. Es spiegelt den ursprünglichen Namen vor der Akquise von [!DNL Audience Manager] ([!DNL Demdex]) wider. [!DNL Adobe] 2011 erworben [!DNL Demdex] und die Firma als [!DNL Audience Manager]. Es ist schwierig, diese Domäne zu ändern, weil sie tief mit [!DNL Audience Manager], der [!DNL Adobe Experience Cloud ID Service]und unserer installierten Benutzerbasis verbunden ist. Möglicherweise werden weitere Präfixe an Legacy- `demdex.net` Aufrufen angehängt (z. B. `dcs.demdex.net`, `fast.demdex.net`usw.). Unabhängig vom Präfix `something.demdex.net` ist ein Aufruf an immer ein Aufruf an [!DNL Adobe] und nicht an eine unbekannte oder verdächtige Drittanbieterdomäne. |
| `dpm` | [!DNL DPM] ist eine Abkürzung für [!DNL Data Provider Match]. Es teilt internen [!DNL Adobe] Systemen mit, dass ein Aufruf von [!DNL Audience Manager] oder der [!DNL Adobe Experience Cloud ID Service] die Kundendaten zur Synchronisierung weiterleitet oder eine ID anfordert. Dies ist der häufigste `demdex.net` Aufruf, den Sie von [!DNL Audience Manager] oder von der [!DNL Adobe Experience Cloud ID Service]. <br><br>[!DNL DPM] Aufruf - Grundlagen <ul><li>[!DNL Audience Manager]: Ein [!DNL DPM] Aufruf von [!DNL Audience Manager] sendet Daten an das [!DNL Data Collection Servers] und [!DNL Profile Cache Servers]. Siehe [Datenerfassungskomponenten](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Ein [!DNL DPM] Aufruf der [!DNL Adobe Experience Cloud ID Service] ist eine Anforderung einer Besucher-ID. Siehe [Cookies und den Identitätsdienst](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html) für Adobe Experience Platformen und [Anleitung zum Anfordern und Festlegen von IDs]durch den Identitätsdienst für Adobe Experience Platformen (https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html).</li></ul><br>Hinweis: [!DNL Adobe Experience Cloud ID Service] Kunden können das [!DNL DPM] Präfix im Domänennamen ändern. Siehe [audienceManager Server und audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Identitätsdienst für Adobe Experience Platformen](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookies in Audience Manager](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)

