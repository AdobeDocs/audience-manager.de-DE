---
description: Häufige API-Fragen und -Probleme
seo-description: Häufige API-Fragen und -Probleme
seo-title: API-FAQs
solution: Audience Manager
title: API-FAQs
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API-FAQs{#api-faq}

Häufige API-Fragen und -Probleme

<!-- 

faq_api.xml

 -->

Die Dokumentation zur [REST-API](../api/rest-api-main/rest-api-main.md) enthält Details zu bestimmten Methoden und Codebeispielen.

<br> 

**Warum werden[!UICONTROL DIL]Ereignisaufrufe mit[!UICONTROL GET]und[!UICONTROL POST]Methoden durchgeführt?**

[!UICONTROL DIL] übergibt Daten basierend auf der Länge der Abfragezeichenfolge des Ereignisaufrufs [!DNL Audience Manager] mit einer `GET` oder `POST` -Methode an. Dieses Verhalten ist standardmäßig in `GET` und `POST` Methoden integriert. Es ist nicht spezifisch für [!DNL Audience Manager].

* [!UICONTROL DIL] Ereignisaufrufe mit `GET` URLs mit maximal 2048 Zeichen. Ein `GET` Ereignisaufruf enthält Daten in der URL als Abfragezeichenfolgenparameter, die als Schlüssel-Wert-Paare übergeben werden.

* [!UICONTROL DIL] führt Ereignisaufrufe aus, `POST` wenn eine URL mehr als 2048 Zeichen enthält. Ein `POST` Ereignisaufruf enthält Daten im Hauptteil der Anforderung. [!UICONTROL DIL] Daten werden in Schlüssel-Wert-Paare eingesetzt und Informationen werden als Formulardaten und nicht in die URL-Abfragezeichenfolge übergeben.

Obwohl jede Methode Daten auf andere Weise weitergibt, hat dies keine Auswirkungen auf die Funktionalität. Bei beiden Methoden werden beispielsweise immer noch Daten an Ziele gesendet, ID-Synchronisierungen funktionieren normal und Sie können Eigenschaften aus Datensignalen erstellen. [!DNL Audience Manager]

<br> 

**Was erlaubt mir die[!UICONTROL REST API]s zu tun?**

Mit den [!UICONTROL REST API][!DNL Audience Manager] s können Sie programmatisch mit den meisten Funktionen und Funktionen arbeiten, die in der Benutzeroberfläche verfügbar sind.

<br> 

**Wie erhalte ich eine[!UICONTROL REST API]Client-ID und ein Geheimnis?**

Wenden Sie sich an Ihren Partner Solutions-Kundenbetreuer, um [!DNL API] Zugangsdaten zu erhalten. Unsere APIs verwenden [OAuth 2.0](https://oauth.net/2/) -Standards für die Token-Authentifizierung, -Autorisierung und -Erneuerung. Weitere Informationen finden Sie unter [OAuth-Authentifizierung](../api/rest-api-main/aam-api-getting-started.md#oauth) .
