---
description: Audience Manager und der Adobe Experience Platform Identity-Dienst führen Aufrufe an und empfangen Daten von der Domäne demdex.net. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber dies ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex.net-Aufrufs beschrieben.
seo-description: Audience Manager und der Adobe Experience Platform Identity-Dienst führen Aufrufe an und empfangen Daten von der Domäne demdex.net. Dies mag so aussehen, als ob Adobe mit einer ungewöhnlichen Drittanbieterdomäne arbeitet, aber dies ist nicht der Fall. In diesem Abschnitt werden die Elemente eines demdex.net-Aufrufs beschrieben.
seo-title: Grundlegendes zu Aufrufen an die Domäne „demdex.net“
solution: Audience Manager
title: Grundlegendes zu Aufrufen an die Domäne „demdex.net“
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
feature: 'Referenz '
exl-id: dcd5ed86-4ff1-4f63-9c9f-edf11c229a30
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 15%

---

# Aufrufe an die Domäne [!DNL Demdex] verstehen {#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] und die  [!DNL Adobe Experience Platform Identity Service] Aufrufe an und empfangen Daten von der  `demdex.net` Domäne. [!DNL Adobe] funktioniert möglicherweise mit einer ungewöhnlichen Drittanbieterdomäne, dies ist jedoch nicht der Fall. In diesem Abschnitt werden die Elemente in einem `demdex.net`-Aufruf beschrieben.

| Aufrufelement | Beschreibung |
|---|---|
| `demdex.net` | Dies ist eine veraltete Domäne, die von [!DNL Adobe] gesteuert wird. Sie spiegelt den ursprünglichen Namen vor der Akquise von [!DNL Audience Manager] ([!DNL Demdex]) wider. [!DNL Adobe] hat [!DNL Demdex] 2011 übernommen und das Unternehmen in [!DNL Audience Manager] umbenannt. Es ist schwierig, diese Domäne zu ändern, da sie tief mit [!DNL Audience Manager], [!DNL Adobe Experience Cloud ID Service] und unserer installierten Benutzerbasis verbunden ist. Möglicherweise werden weitere Präfixe an veraltete `demdex.net`-Aufrufe angehängt (z. B. `dcs.demdex.net`, `fast.demdex.net` usw.). Unabhängig vom Präfix ist ein Aufruf von `something.demdex.net` immer ein Aufruf von [!DNL Adobe] und nicht eine unbekannte oder verdächtige Drittanbieterdomäne. |
| `dpm` | [!DNL DPM] ist eine Abkürzung für  [!DNL Data Provider Match]. Es teilt internen Systemen mit, dass [!DNL Adobe]-Aufrufe von [!DNL Audience Manager] oder [!DNL Adobe Experience Cloud ID Service] Kundendaten zur Synchronisierung oder Anforderung einer ID übergeben. Dies ist der häufigste `demdex.net` -Aufruf, den Sie von [!DNL Audience Manager] oder [!DNL Adobe Experience Cloud ID Service] sehen werden. <br><br>[!DNL DPM] Aufrufgrundlagen: <ul><li>[!DNL Audience Manager]: Ein  [!DNL DPM] Aufruf von  [!DNL Audience Manager] sendet Daten an  [!DNL Data Collection Servers] und  [!DNL Profile Cache Servers]. Siehe [Datenerfassungskomponenten](../reference/system-components/components-data-collection.md).</li><li>[!DNL Adobe Experience Cloud ID Service]: Ein  [!DNL DPM] Aufruf der  [!DNL Adobe Experience Cloud ID Service] ist eine Anforderung einer Besucher-ID. Siehe [Cookies und der Adobe Experience Platform Identity-Dienst](https://docs.adobe.com/content/help/de-DE/id-service/using/intro/cookies.html) und [Anfordern und Festlegen von IDs durch den Adobe Experience Platform Identity-Dienst](https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html).</li></ul><br>Hinweis:  [!DNL Adobe Experience Cloud ID Service] -Kunden können das  [!DNL DPM] Präfix im Domänennamen ändern. Siehe [audienceManager Server und audienceManagerServerSecure](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html). |

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookies in Audience Manager](https://docs.adobe.com/content/help/de-DE/core-services/interface/ec-cookies/cookies-am.html)

