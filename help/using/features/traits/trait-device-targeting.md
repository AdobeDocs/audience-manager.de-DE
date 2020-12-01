---
description: Beschreibt die gebräuchlichen Schlüssel-Wert-Paare auf Plattformebene, die Sie zur Zielgruppe von Benutzern mit gerätebezogenen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto verwenden können.
seo-description: Beschreibt die gebräuchlichen Schlüssel-Wert-Paare auf Plattformebene, die Sie zur Zielgruppe von Benutzern mit gerätebezogenen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto verwenden können.
seo-title: Geräte-Targeting mit Schlüsseln auf Plattformebene
solution: Audience Manager
title: Geräte-Targeting mit Schlüsseln auf Plattformebene
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 9%

---


# Geräte-Targeting mit Schlüsseln auf Plattformebene {#device-targeting-with-platform-level-keys}

Beschreibt die gebräuchlichen Schlüssel-Wert-Paare auf Plattformebene, die Sie zur Zielgruppe von Benutzern mit gerätebezogenen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto verwenden können.

## Zweck der Variablen auf Plattformebene {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Mit Plattformvariablen können Sie Daten, die von einer bestimmten Site übergeben wurden, aufnehmen und für das Targeting für alle Eigenschaften in Ihrem [!DNL Audience Manager]-Konto verfügbar machen. Diese Variablen werden durch [Schlüssel-Wert-Paare](../../reference/key-value-pairs-explained.md) gebildet, wobei der Schlüssel durch `d_` vorangestellt wird, wie unten dargestellt.

## Vom Benutzeragent {#keys-user-agent} definierte Schlüssel auf Plattformebene

Die [!UICONTROL Data Collection Servers] extrahieren Sie die Werte für diese Schlüssel aus der [Benutzeragenten-Kopfzeile](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP`-Anforderungen. Die Werte stellen Informationen auf Geräteebene aus der [!UICONTROL Device Atlas]-Datenbank dar. Die Signale in der folgenden Tabelle sind verfügbar, wie aus dem Beispiel des Benutzeragenten extrahiert. [Laden Sie eine Liste der gebräuchlichsten Schlüssel](assets/device_keys.csv) nach  [!UICONTROL Device Atlas] Messungen herunter.

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
>Auch wenn ein oder mehrere Signale nicht aus dem Benutzeragenten-Header abgerufen werden können, werden die anderen Signale weiterhin an das [!UICONTROL Data Collection Servers] weitergeleitet.

>[!MORELIKETHIS]
>
>* [Anforderungen an Präfixe für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)

