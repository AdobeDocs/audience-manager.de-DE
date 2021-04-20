---
description: Der Echtzeit-Inbound-Datenerfassungsprozess nutzt eine Reihe von HTTP-Anfragen vom Browser des Benutzers, um Daten an den Audience Manager zu übermitteln.
seo-description: Der Echtzeit-Inbound-Datenerfassungsprozess nutzt eine Reihe von HTTP-Anfragen vom Browser des Benutzers, um Daten an den Audience Manager zu übermitteln.
seo-title: Erfassung eingehender Daten in Echtzeit
solution: Audience Manager
title: Erfassung eingehender Daten in Echtzeit
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 8%

---

# Erfassung eingehender Daten in Echtzeit {#real-time-inbound-data-ingestion}

Der Prozess zur Erfassung von Eingangsdaten in Echtzeit verwendet eine Reihe von `HTTP`-Anforderungen eines Benutzerbrowsers, um Daten an den Audience Manager zu übermitteln.

<!-- c_rt_inbound_real_time.xml -->

Eingehende Daten sollten als Schlüssel-Wert-Paare, so genannte Signale, formatiert werden. Normalerweise wird jedes Signal einem Segment zugeordnet, das über die Benutzeroberfläche oder [!DNL API] erstellt oder verwaltet wird.

## URL-Zeichenfolgenparameter und Syntax {#url-string-syntax}

Die Variablen [!DNL URL] für eine eingehende Datenübertragung sollten die unten beschriebenen Variablen enthalten. Denken Sie daran, in der Benutzeroberfläche [!DNL Audience Manager] Eigenschaften ](../../../features/traits/create-onboarded-rule-based-traits.md) und eine [Ordnerstruktur](../../../features/traits/trait-storage.md#create-trait-storage-folder) zu erstellen, bevor Sie Datenübertragungen in Echtzeit einrichten.[

>[!NOTE]
>
>Ersetzen Sie kursiv gedruckten Inhalt durch tatsächliche Parameterwerte.

| Parameter | Beschreibung |
|---|---|
| `<KEY>` | Eine eindeutige Kennung in einem Schlüssel-Wert-Paar (z. B. Geschlecht, Farbe, Preis). |
| `<VAL>` | Eine Variable, die zu dem vom Schlüssel definierten Datensatz gehört (z. B. gender=male, color=green, price=100) |

### URL-Syntax

Während eines Echtzeit-Inbound-Datenerfassungsprozesses verwendet eine korrekt formatierte [!DNL URL]-Zeichenfolge die folgende Syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
