---
description: Der Prozess der Echtzeit-Dateneingabe nutzt eine Reihe von HTTP-Anforderungen aus dem Browser eines Benutzers, um Daten an Audience Manager zu übermitteln.
seo-description: Der Prozess der Echtzeit-Dateneingabe nutzt eine Reihe von HTTP-Anforderungen aus dem Browser eines Benutzers, um Daten an Audience Manager zu übermitteln.
seo-title: Dateneinbettung in Echtzeit
solution: Audience Manager
title: Dateneinbettung in Echtzeit
uuid: 43cb0ebc-6c36-4391-bfb-6b203d63c69a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Dateneinbettung in Echtzeit {#real-time-inbound-data-ingestion}

Der Prozess der Dateneingabe in Echtzeit verwendet eine Reihe von `HTTP` Anforderungen aus dem Browser eines Benutzers, um Daten an Audience Manager zu übermitteln.

<!-- c_rt_inbound_real_time.xml -->

Eingehende Daten sollten als Schlüssel-Wert-Paare, so genannte Signale, formatiert werden. Normalerweise wird jedes Signal einem Segment zugeordnet, das über die Benutzeroberfläche oder [!DNL API]die Benutzeroberfläche erstellt oder verwaltet wird.

## URL-Zeichenfolgenparameter und -Syntax {#url-string-syntax}

Die Variablen [!DNL URL] für eine eingehende Datenübertragung sollten die unten beschriebenen Variablen enthalten. Denken Sie daran, Eigenschaften[ und eine ](../../../features/traits/create-onboarded-rule-based-traits.md)Ordnerstruktur[ in der ](../../../features/traits/trait-storage.md#create-trait-storage-folder) Benutzeroberfläche zu [!DNL Audience Manager]erstellen, bevor Sie Datenübertragungen in Echtzeit einrichten.

>[!NOTE]
>
>Ersetzen Sie kursiv gedruckten Inhalt durch tatsächliche Parameterwerte.

| Parameter | Beschreibung |
|---|---|
| `<KEY>` | Eine eindeutige Kennung in einem Schlüssel-Wert-Paar (z. B. Geschlecht, Farbe, Preis). |
| `<VAL>` | Eine Variable, die zu dem vom Schlüssel definierten Datensatz gehört (z. B. gender=male, color=green, price=100) |

### URL-Syntax

Während eines Echtzeit-Inbound-Datenerfassungsprozesses verwendet eine ordnungsgemäß formatierte [!DNL URL] Zeichenfolge die folgende Syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
