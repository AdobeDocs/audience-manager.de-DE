---
description: Häufige API-Fragen und -Probleme
seo-description: Häufige API-Fragen und -Probleme
seo-title: API-FAQs
solution: Audience Manager
title: API-FAQs
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---


# API-FAQs{#api-faq}

Häufige API-Fragen und -Probleme

<!-- 

faq_api.xml

 -->

Die Dokumentation zur [REST-API](../api/rest-api-main/rest-api-main.md) enthält Details zu bestimmten Methoden und Codebeispielen.

<br> 

**Warum werden[!UICONTROL DIL]Ereignis-Aufrufe mit[!UICONTROL GET]und[!UICONTROL POST]Methoden durchgeführt?**

[!UICONTROL DIL] übergibt Daten basierend auf der Länge der Abfrage-Zeichenfolge des Ereignis-Aufrufs [!DNL Audience Manager] mit einer `GET` oder `POST` -Methode an. Dieses Verhalten ist standardmäßig in `GET` und `POST` Methoden integriert. Es ist nicht spezifisch für [!DNL Audience Manager].

* [!UICONTROL DIL] führt Ereignis-Aufrufe mit `GET` ein, wenn eine URL maximal 2048 Zeichen enthält. Ein `GET` Ereignis-Aufruf enthält Daten in der URL als Abfrage-Zeichenfolgenparameter, die als Schlüssel-Wert-Paare übergeben werden.

* [!UICONTROL DIL] führt Ereignis-Aufrufe mit `POST` aus, wenn eine URL mehr als 2048 Zeichen enthält. Ein `POST` Ereignis-Aufruf enthält Daten im Hauptteil der Anforderung. [!UICONTROL DIL] setzt Daten in Schlüssel-Wert-Paare und gibt Informationen als Formulardaten statt in die URL-Abfrage-Zeichenfolge weiter.

Obwohl jede Methode Daten auf andere Weise weitergibt, hat dies keine Auswirkungen auf die Funktionalität. Bei beiden Methoden werden beispielsweise immer noch Daten an Ziele gesendet, ID-Synchronisierungen funktionieren normal und Sie können Eigenschaften aus Datensignalen erstellen. [!DNL Audience Manager]

<br> 

**Was erlaubt mir die[!UICONTROL REST API]s zu tun?**

Mit den [!UICONTROL REST API][!DNL Audience Manager] s können Sie programmatisch mit den meisten Funktionen und Funktionen arbeiten, die in der Benutzeroberfläche verfügbar sind.

<br> 

**Wie erhalte ich eine[!UICONTROL REST API]Client-ID und ein Geheimnis?**

Wenden Sie sich an Ihren Partner Solutions-Kundenbetreuer, um [!DNL API] Zugangsdaten zu erhalten. Unsere APIs verwenden [OAuth 2.0](https://oauth.net/2/) -Standards für die Token-Authentifizierung, -Autorisierung und -Erneuerung. Weitere Informationen finden Sie unter [OAuth-Authentifizierung](../api/rest-api-main/aam-api-getting-started.md#oauth) .
