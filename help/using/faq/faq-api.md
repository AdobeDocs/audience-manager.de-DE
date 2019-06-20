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


# Häufig gestellte Fragen zu API{#api-faq}

Allgemeine API-Fragen und Probleme.

<!-- 

faq_api.xml

 -->

Die [REST-API](../api/rest-api-main/rest-api-main.md) -Dokumentation enthält Details zu spezifischen Methoden und Codebeispielen.

<br> 

**Warum[!UICONTROL DIL]werden Ereignisaufrufe und[!UICONTROL GET][!UICONTROL POST]-methoden vorgenommen?**

[!UICONTROL DIL] gibt Daten an eine [!DNL Audience Manager]`GET` oder `POST` eine Methode basierend auf der Länge der Abfragezeichenfolge des Ereignisaufrufs weiter. Dieses Verhalten ist standardmäßig `GET``POST` in der Standardeinstellung integriert. Es ist nicht spezifisch für [!DNL Audience Manager].

* [!UICONTROL DIL] führt Ereignisaufrufe durch, wenn `GET` eine URL 2048 Zeichen oder weniger enthält. Ein `GET` Ereignisaufruf enthält Daten in der URL als Abfragezeichenfolgenparameter, die als Schlüssel-Wert-Paare übergeben werden.

* [!UICONTROL DIL] führt Ereignisaufrufe durch, wenn `POST` eine URL mehr als 2048 Zeichen enthält. Ein `POST` Ereignisaufruf enthält Daten im Textkörper der Anforderung. [!UICONTROL DIL] Daten in Schlüssel-Wert-Paare platziert und Informationen als Formulardaten übergibt und nicht in der URL-Abfragezeichenfolge.

Obwohl jede Methode Daten auf eine andere Weise weiterleitet, wirkt sich dies nicht auf Funktionalität aus. Bei beiden Methoden werden beispielsweise [!DNL Audience Manager] weiterhin Daten an die Ziele gesendet, ID-Synchronisierungen funktionieren normal und Sie können Eigenschaften aus Datensignalen erstellen.

<br> 

**Was kann[!UICONTROL REST API]ich tun?**

Mit den [!UICONTROL REST API]s können Sie programmgesteuert mit den meisten [!DNL Audience Manager] Funktionen und Funktionen arbeiten, die in der Benutzeroberfläche verfügbar sind.

<br> 

**Wie erhalte ich eine[!UICONTROL REST API]Client-ID und einen geheimen Schlüssel?**

Wenden Sie sich an Ihren Partner-Lösungsvertreter, um [!DNL API] Zugriffsberechtigungen zu erhalten. Unsere apis verwenden [oauth 2.0](https://oauth.net/2/) -Standards für die Token-Authentifizierung, Autorisierung und Verlängerung. Weitere Informationen finden Sie unter [oauth-Authentifizierung](../api/rest-api-main/aam-api-getting-started.md#oauth) .
