---
description: Beschreibt die gebräuchlichen Schlüssel-Wert-Paare auf Plattformebene, die Sie verwenden können, um Benutzer mit gerätebezogenen Variablen über alle Eigenschaften in Ihrem Audience Manager-Konto hinweg anzusprechen.
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: Geräte-Targeting mit Schlüsseln auf Plattformebene
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 5%

---

# Geräte-Targeting mit Schlüsseln auf Plattformebene {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google hat die Funktionalität von [!DNL Google Chrome] und alle [!DNL Chromium]-basierte Browser verwenden, um die über die `User-Agent` -Kopfzeile.
>Ab März 2023 unterstützt Audience Manager diese Aktualisierungen durch Nutzung von [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en). So verwenden Sie weiterhin Eigenschaftsinformationen, die über das `User-Agent` -Kopfzeile verwenden, müssen Sie [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) und aktivieren [Hohe Entropy-Benutzeragenten-Client-Hinweise](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en).
>Diese Aktualisierungen werden nicht von [DIL](../../../using/dil/dil-overview.md), sodass Audience Manager, die [!DNL DIL] kann Eigenschaftsinformationen nicht über die `User-Agent` -Kopfzeile.

Beschreibt die gebräuchlichen Schlüssel-Wert-Paare auf Plattformebene, die Sie verwenden können, um Benutzer mit gerätebezogenen Variablen über alle Eigenschaften in Ihrem Audience Manager-Konto hinweg anzusprechen.

## Zweck der Variablen auf Plattformebene {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Mit Variablen auf Plattformebene können Sie Daten aus einer bestimmten Site aufnehmen und für das Targeting über alle Eigenschaften in Ihrer [!DNL Audience Manager] -Konto. Diese Variablen werden durch [Schlüssel-Wert-Paare](../../reference/key-value-pairs-explained.md) mit dem vorangestellten -Schlüssel `d_` wie unten dargestellt.

## Von User Agent definierte Schlüssel auf Plattformebene {#keys-user-agent}

Die [!UICONTROL Data Collection Servers] extrahieren Sie die Werte für diese Schlüssel aus der [Benutzeragenten-Kopfzeile](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP` -Anfragen. Die Werte stellen Informationen auf Geräteebene aus der [!UICONTROL Device Atlas] Datenbank. Die Signale in der folgenden Tabelle sind verfügbar, wie aus dem Beispiel des Benutzeragenten extrahiert. [Liste der häufigsten Schlüssel herunterladen](assets/device_keys.csv)gemäß [!UICONTROL Device Atlas] Messungen.

| [!DNL Signal] | [!DNL Type] | [!DNL Example] |
|---|---|---|
| `d_device_vendor` | [!DNL VENDOR] | [!DNL apple] |
| `d_device_hardware_type` | [!DNL HARDWARE] | [!DNL mobile phone] |
| `d_device_os_version` | [!DNL OS VERSION] | [!DNL 5_0] |
| `d_device_os_name` | [!DNL OS NAME] | [!DNL ios] |
| `d_device_model` | [!DNL MODEL] | [!DNL iphone] |
| `d_device_marketing_name` | [!DNL MARKETING NAME] | [!DNL iphone] |
| `d_device_manufacturer` | [!DNL MANUFACTURER] | [!DNL apple] |

```
 Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

>[!NOTE]
>
>Selbst wenn ein oder mehrere Signale nicht aus dem Benutzeragenten-Header abgerufen werden können, werden die anderen Signale weiterhin an die [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Anforderungen an Präfixe für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)

