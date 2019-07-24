---
description: Allgemeine API-Fragen und Probleme.
seo-description: Allgemeine API-Fragen und Probleme.
seo-title: Häufig gestellte Fragen zu API
solution: Audience Manager
title: Häufig gestellte Fragen zu API
uuid: 8222 ebf 0-b 50 e -4 f 48-8021-dbfca 2828 b 7 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API FAQ{#api-faq}

Allgemeine API-Fragen und Probleme.

<!-- 

faq_api.xml

 -->

The [REST API](../api/rest-api-main/rest-api-main.md) documentation contains details about specific methods and code samples.

<br> 

**Warum[!UICONTROL DIL]werden Ereignisaufrufe und[!UICONTROL GET][!UICONTROL POST]-methoden vorgenommen?**

[!UICONTROL DIL] gibt Daten an eine [!DNL Audience Manager]`GET` oder `POST` eine Methode basierend auf der Länge der Abfragezeichenfolge des Ereignisaufrufs weiter. This behavior is built in to `GET` and `POST` methods by default. It is not specific to [!DNL Audience Manager].

* [!UICONTROL DIL] führt Ereignisaufrufe durch, wenn `GET` eine URL 2048 Zeichen oder weniger enthält. A `GET` event call includes data in the URL as query string parameters, which are passed in as key-value pairs.

* [!UICONTROL DIL] führt Ereignisaufrufe durch, wenn `POST` eine URL mehr als 2048 Zeichen enthält. A `POST` event call includes data in the body of the request. [!UICONTROL DIL] Daten in Schlüssel-Wert-Paare platziert und Informationen als Formulardaten übergibt und nicht in der URL-Abfragezeichenfolge.

Obwohl jede Methode Daten auf eine andere Weise weiterleitet, wirkt sich dies nicht auf Funktionalität aus. For example, with either method, [!DNL Audience Manager] still sends data to destinations, ID syncs works normally, and you can create traits from data signals.

<br> 

**Was kann[!UICONTROL REST API]ich tun?**

The [!UICONTROL REST API]s let you work programmatically with most [!DNL Audience Manager] features and functions that are available in the user interface.

<br> 

**Wie erhalte ich eine[!UICONTROL REST API]Client-ID und einen geheimen Schlüssel?**

Contact your Partner Solutions representative to obtain [!DNL API] access credentials. Our APIs use [OAuth 2.0](https://oauth.net/2/) standards for token authentication, authorization, and renewal. See [OAuth Authentication](../api/rest-api-main/aam-api-getting-started.md#oauth) for more information.
