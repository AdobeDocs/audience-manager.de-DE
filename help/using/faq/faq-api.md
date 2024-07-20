---
description: Häufige Fragen und Probleme im Zusammenhang mit APIs.
seo-description: Common API questions and issues.
seo-title: API FAQ
solution: Audience Manager
title: Häufig gestellte Fragen zu APIs
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
exl-id: 9a51220e-3f53-4911-876b-16e968d44d0f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 100%

---

# Häufig gestellte Fragen zu APIs{#api-faq}

Häufige Fragen und Probleme im Zusammenhang mit APIs.

<!-- 

faq_api.xml

 -->

Die Dokumentation zur [REST-API](../api/rest-api-main/rest-api-main.md) enthält Details zu bestimmten Methoden und Code-Beispiele.

<br>

**Warum führt [!UICONTROL DIL] Ereignisaufrufe mit den [!UICONTROL GET]- und [!UICONTROL POST]-Methoden aus?**

[!UICONTROL DIL] übergibt Daten an [!DNL Audience Manager] mithilfe einer `GET`- oder `POST`-Methode basierend auf der Länge der Abfragezeichenfolge des Ereignisaufrufs. Dieses Verhalten ist standardmäßig in `GET`- und `POST`-Methoden integriert. Es ist nicht spezifisch für [!DNL Audience Manager].

* [!UICONTROL DIL] führt Ereignisaufrufe mit `GET` aus, wenn eine URL maximal 2048 Zeichen enthält. Ein Ereignisaufruf mit `GET` enthält Daten in der URL als Abfragezeichenfolgenparameter, die als Schlüssel-Wert-Paare übergeben werden.

* [!UICONTROL DIL] führt Ereignisaufrufe mit `POST` aus, wenn eine URL mehr als 2048 Zeichen enthält. Ein Ereignisaufruf mit `POST` enthält Daten im Hauptteil der Anfrage. [!UICONTROL DIL] fügt Daten in Schlüssel-Wert-Paare ein und übergibt Informationen als Formulardaten und nicht in der URL-Abfragezeichenfolge.

Obwohl jede Methode Daten auf unterschiedliche Weise übergibt, hat dies keine Auswirkungen auf die Funktionalität. Beispielsweise sendet [!DNL Audience Manager] bei beiden Methoden weiterhin Daten an Ziele, die ID-Synchronisierung funktioniert normal und Sie können Eigenschaften aus Datensignalen erstellen.

<br>

**Was erlaubt mir die [!UICONTROL REST API]s?**

Mit den [!UICONTROL REST API]s können Sie programmatisch mit den meisten Funktionen und Funktionen von [!DNL Audience Manager] arbeiten, die in der Benutzeroberfläche verfügbar sind.

<br>

**Wie erhalte ich eine [!UICONTROL REST API]-Client-ID und ein Geheimnis?**

Wenden Sie sich an Ihren Partner Solutions-Support-Mitarbeiter, um Zugangsdaten für [!DNL API] zu erhalten. Unsere APIs verwenden [OAuth 2.0](https://oauth.net/2/)-Standards für die Token-Authentifizierung, -Autorisierung und -Erneuerung. Weitere Informationen finden Sie unter [OAuth-Authentifizierung](../api/rest-api-main/aam-api-getting-started.md#oauth).
