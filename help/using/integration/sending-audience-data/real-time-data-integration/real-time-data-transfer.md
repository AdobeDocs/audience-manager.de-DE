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


# Real-Time Inbound Data Ingestion {#real-time-inbound-data-ingestion}

The real-time inbound data ingestion process uses a series of `HTTP` requests from a user's browser to pass in data to Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Eingehende Daten sollten als Schlüssel-Wert-Paare mit dem Namen Signal formatiert werden. Typically, each signal is mapped to a segment created or managed through the user interface or [!DNL API].

## URL String Parameters and Syntax {#url-string-syntax}

The [!DNL URL] for an inbound data transfer should contain the variables described below. Remember to [create traits](../../../features/traits/create-onboarded-rule-based-traits.md) and a [folder structure](../../../features/traits/trait-storage.md#create-trait-storage-folder) in the [!DNL Audience Manager] UI before setting up real-time data transfers.

>[!NOTE]
>
>Ersetzen Sie kursiv gesteuerte Inhalte durch tatsächliche Parameterwerte.

| Parameter | Beschreibung |
|---|---|
| `<KEY>` | Eine eindeutige Kennung in einem Schlüssel-Wert-Paar (z. B. Geschlecht, Farbe, Preis). |
| `<VAL>` | Eine Variable, die zu dem vom Schlüssel definierten Datensatz gehört (z. B. Geschlecht = männlich, color = green, price = 100) |

### URL-Syntax

During a real-time inbound data ingestion process, a properly formatted [!DNL URL] string uses the following syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
