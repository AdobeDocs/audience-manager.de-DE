---
description: Beschreibt die allgemeinen Schlüssel-Wert-Paare auf Plattformebene, mit denen Sie Benutzende mit gerätebezogenen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto auswählen können.
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: Geräte-Targeting mit Schlüsseln auf Plattformebene
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
TQID: 'https://experienceleague.adobe.com/Pv9-MWpF5uPassf9VYTGgZwQ6gmnW8p9FSYmYxOPHEg'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b89b323a-1e91-40b1-8d20-96b5b726d55a
    internal-label: Audience management
subfeature_v2:
  - id: b1ecf375-97f8-4f5a-a937-6129552209be
    internal-label: Traits
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 1%
---
# Geräte-Targeting mit Schlüsseln auf Plattformebene {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google hat die Funktionalität von [!DNL Google Chrome] und allen [!DNL Chromium] Browsern aktualisiert, um die über den `User-Agent`-Header erfassten Informationen zu minimieren.
>Ab März 2023 unterstützt Audience Manager diese Updates mithilfe von [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de). Um weiterhin die über den `User-Agent`-Header bereitgestellten Eigenschafteninformationen zu verwenden, müssen Sie [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=de) verwenden und [Benutzeragenten-Client-Hinweise mit hoher Entropie](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=de) aktivieren.
>Diese Aktualisierungen werden von [DIL](../../../using/dil/dil-overview.md) nicht unterstützt, sodass Audience Manager-Kunden, die [!DNL DIL] verwenden, keine Eigenschafteninformationen über die `User-Agent`-Kopfzeile erfassen können.

Beschreibt die allgemeinen Schlüssel-Wert-Paare auf Plattformebene, mit denen Sie Benutzende mit gerätebezogenen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto auswählen können.

## Zweck von Variablen auf Plattformebene {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Mit Variablen auf Plattformebene können Sie Daten, die von einer bestimmten Site übergeben werden, für die Zielgruppenbestimmung in allen Eigenschaften in Ihrem [!DNL Audience Manager]-Konto verfügbar machen. Diese Variablen werden durch [Schlüssel-Wert-Paare](../../reference/key-value-pairs-explained.md) gebildet, wobei der Schlüssel wie unten dargestellt durch `d_` vorangestellt wird.

## Vom Benutzeragenten definierte Schlüssel auf Plattformebene {#keys-user-agent}

Die [!UICONTROL Data Collection Servers] extrahieren die Werte für diese Schlüssel aus der [Benutzeragenten-Kopfzeile](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP`. Die Werte stellen Informationen auf Geräteebene aus der [!UICONTROL Device Atlas]-Datenbank dar. Die Signale in der folgenden Tabelle sind verfügbar, wie im Beispiel des Benutzeragenten extrahiert. [Laden Sie eine Liste der gängigsten Schlüssel &#x200B;](assets/device_keys.csv) nach [!UICONTROL Device Atlas] Messungen herunter.

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
>Selbst wenn ein oder mehrere Signale nicht aus dem User Agent-Header abgerufen werden können, werden die anderen Signale weiterhin an den [!UICONTROL Data Collection Servers] übergeben.

>[!MORELIKETHIS]
>
>* [Anforderungen an Präfixe für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)
