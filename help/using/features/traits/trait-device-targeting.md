---
description: Beschreibt die gebräuchlichen Schlüssel-Wert-Paare auf Plattformebene, die Sie verwenden können, um Benutzer mit gerätebezogenen Variablen über alle Eigenschaften in Ihrem Audience Manager-Konto hinweg anzusprechen.
seo-description: Beschreibt die gebräuchlichen Schlüssel-Wert-Paare auf Plattformebene, die Sie verwenden können, um Benutzer mit gerätebezogenen Variablen über alle Eigenschaften in Ihrem Audience Manager-Konto hinweg anzusprechen.
seo-title: Geräte-Targeting mit Schlüsseln auf Plattformebene
solution: Audience Manager
title: Geräte-Targeting mit Schlüsseln auf Plattformebene
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: 'Eigenschaften '
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---

# Geräte-Targeting mit Schlüsseln auf Plattformebene {#device-targeting-with-platform-level-keys}

Beschreibt die gebräuchlichen Schlüssel-Wert-Paare auf Plattformebene, die Sie verwenden können, um Benutzer mit gerätebezogenen Variablen über alle Eigenschaften in Ihrem Audience Manager-Konto hinweg anzusprechen.

## Zweck der Variablen auf Plattformebene {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Variablen auf Plattformebene ermöglichen es Ihnen, von einer bestimmten Site übergebene Daten für das Targeting über alle Eigenschaften Ihres [!DNL Audience Manager]-Kontos hinweg zur Verfügung zu stellen. Diese Variablen werden durch [Schlüssel-Wert-Paare](../../reference/key-value-pairs-explained.md) gebildet, wobei dem Schlüssel `d_` das Präfix  vorangestellt wird, wie unten dargestellt.

## Von User Agent definierte Schlüssel auf Plattformebene {#keys-user-agent}

Die [!UICONTROL Data Collection Servers] extrahieren die Werte für diese Schlüssel aus der [Benutzeragenten-Kopfzeile](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP` -Anforderungen. Die Werte stellen Informationen auf Geräteebene aus der [!UICONTROL Device Atlas]-Datenbank dar. Die Signale in der folgenden Tabelle sind verfügbar, wie aus dem Beispiel des Benutzeragenten extrahiert. [Laden Sie eine Liste der gängigsten Schlüssel](assets/device_keys.csv) herunter, je nach  [!UICONTROL Device Atlas] Messungen.

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
>Selbst wenn ein oder mehrere Signale nicht aus dem Benutzeragenten-Header abgerufen werden können, werden die anderen Signale weiterhin an [!UICONTROL Data Collection Servers] weitergeleitet.

>[!MORELIKETHIS]
>
>* [Anforderungen an Präfixe für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)

