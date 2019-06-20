---
description: Der eingehende Datenerfassungsprozess in Echtzeit verwendet eine Reihe von HTTP-Anforderungen vom Browser eines Benutzers, um Daten an Audience Manager weiterzugeben.
seo-description: Der eingehende Datenerfassungsprozess in Echtzeit verwendet eine Reihe von HTTP-Anforderungen vom Browser eines Benutzers, um Daten an Audience Manager weiterzugeben.
seo-title: Erfassung von Inbound-Daten in Echtzeit
solution: Audience Manager
title: Erfassung von Inbound-Daten in Echtzeit
uuid: 43 cb 0 ebc -6 c 33-4391-bbfb -6 b 203 d 63 c 69 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Erfassung von Inbound-Daten in Echtzeit {#real-time-inbound-data-ingestion}

Der Echtzeit-Datenerfassungsprozess nutzt eine Reihe von `HTTP` Anforderungen aus dem Browser eines Benutzers, um Daten an Audience Manager weiterzugeben.

<!-- c_rt_inbound_real_time.xml -->

Eingehende Daten sollten als Schlüssel-Wert-Paare mit dem Namen Signal formatiert werden. Typically, each signal is mapped to a segment created or managed through the user interface or [!DNL API].

## URL-Zeichenfolgenparameter und -syntax {#url-string-syntax}

Die [!DNL URL] für eine eingehende Datenübertragung sollte die unten beschriebenen Variablen enthalten. Denken Sie daran, [Eigenschaften](../../../features/traits/create-onboarded-rule-based-traits.md) und [eine Ordnerstruktur](../../../features/traits/trait-storage.md#create-trait-storage-folder) in der [!DNL Audience Manager] Benutzeroberfläche zu erstellen, bevor Sie Echtzeit-Datenübertragungen einrichten.

>[!NOTE]
>
>Ersetzen Sie kursiv gesteuerte Inhalte durch tatsächliche Parameterwerte.

| Parameter | Beschreibung |
|---|---|
| `<KEY>` | Eine eindeutige Kennung in einem Schlüssel-Wert-Paar (z. B. Geschlecht, Farbe, Preis). |
| `<VAL>` | Eine Variable, die zu dem vom Schlüssel definierten Datensatz gehört (z. B. Geschlecht = männlich, color = green, price = 100) |

### URL-Syntax

Bei einem eingehenden Erfassungsprozess in Echtzeit verwendet eine ordnungsgemäß formatierte [!DNL URL] Zeichenfolge die folgende Syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
