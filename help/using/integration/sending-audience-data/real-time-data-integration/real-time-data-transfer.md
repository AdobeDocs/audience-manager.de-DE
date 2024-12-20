---
description: Der Echtzeit-Erfassungsvorgang eingehender Daten nutzt eine Reihe von HTTP-Anfragen vom Browser eines Benutzers, um Daten an einen Audience Manager zu übergeben.
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: Erfassung eingehender Daten in Echtzeit
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 1%

---

# Erfassung eingehender Daten in Echtzeit {#real-time-inbound-data-ingestion}

Der Echtzeit-Erfassungsvorgang eingehender Daten nutzt eine Reihe von `HTTP`-Anfragen vom Browser eines Benutzers, um Daten an einen Audience Manager zu übergeben.

<!-- c_rt_inbound_real_time.xml -->

Eingehende Daten sollten als Schlüssel-Wert-Paare formatiert werden, die als Signale bezeichnet werden. Normalerweise wird jedes Signal einem Segment zugeordnet, das über die Benutzeroberfläche oder [!DNL API] erstellt oder verwaltet wird.

## URL-Zeichenfolgenparameter und Syntax {#url-string-syntax}

Die [!DNL URL] für eine eingehende Datenübertragung sollte die unten beschriebenen Variablen enthalten. Denken Sie daran[ in der [!DNL Audience Manager]-Benutzeroberfläche Eigenschaften ](../../../features/traits/create-onboarded-rule-based-traits.md) eine [Ordnerstruktur](../../../features/traits/trait-storage.md#create-trait-storage-folder) zu erstellen, bevor Sie Echtzeit-Datenübertragungen einrichten.

>[!NOTE]
>
>Ersetzen kursiv formatierter Inhalte durch tatsächliche Parameterwerte.

| Parameter | Beschreibung |
|---|---|
| `<KEY>` | Eine eindeutige Kennung in einem Schlüssel-Wert-Paar (z. B. Geschlecht, Farbe, Preis). |
| `<VAL>` | Eine Variable, die zu dem durch den Schlüssel definierten Datensatz gehört (z. B. gender=male, color=green, price=100) |

### URL-Syntax

Während der Aufnahme eingehender Daten in Echtzeit verwendet eine ordnungsgemäß formatierte [!DNL URL]-Zeichenfolge die folgende Syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
