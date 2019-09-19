---
description: Beschreibt die allgemeinen Schlüssel-Wert-Paare auf Plattformebene, die Sie verwenden können, um Benutzer mit gerätebezogenen Variablen über alle Eigenschaften in Ihrem Audience Manager-Konto hinweg anzusprechen.
seo-description: Beschreibt die allgemeinen Schlüssel-Wert-Paare auf Plattformebene, die Sie verwenden können, um Benutzer mit gerätebezogenen Variablen über alle Eigenschaften in Ihrem Audience Manager-Konto hinweg anzusprechen.
seo-title: Geräte-Targeting mit Schlüsseln auf Plattformebene
solution: Audience Manager
title: Geräte-Targeting mit Schlüsseln auf Plattformebene
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Device Targeting With Platform-level Keys {#device-targeting-with-platform-level-keys}

Beschreibt die allgemeinen Schlüssel-Wert-Paare auf Plattformebene, die Sie verwenden können, um Benutzer mit gerätebezogenen Variablen über alle Eigenschaften in Ihrem Audience Manager-Konto hinweg anzusprechen.

## Zweck der Variablen auf Plattformebene {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Mit Plattformvariablen können Sie Daten, die von einer bestimmten Site übergeben wurden, aufnehmen und für das Targeting über alle Eigenschaften in Ihrem [!DNL Audience Manager] Konto hinweg verfügbar machen. Diese Variablen werden durch [Schlüssel-Wert-Paare](../../reference/key-value-pairs-explained.md) gebildet, wobei der Schlüssel dem folgenden vorangestellt wird `d_` .

## Vom Benutzeragent definierte Schlüssel auf Plattformebene {#keys-user-agent}

Die [!UICONTROL Data Collection Servers] Werte für diese Schlüssel werden aus dem [Benutzeragenten-Header](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP` Anforderungen extrahiert. Die Werte stellen Informationen auf Geräteebene aus der [!UICONTROL Device Atlas] Datenbank dar. Die Signale in der folgenden Tabelle sind verfügbar, wie aus dem Beispiel des Benutzeragenten extrahiert. [Laden Sie eine Liste der gebräuchlichsten Schlüssel](assets/device_keys.csv)nach [!UICONTROL Device Atlas] Messungen herunter.

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
>Auch wenn ein oder mehrere Signale nicht aus dem Benutzeragenten-Header abgerufen werden können, werden die anderen Signale trotzdem an den [!UICONTROL Data Collection Servers]Empfänger weitergeleitet.

>[!MORE_LIKE_THIS]
>
>* [Voraussetzungen für das Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)

