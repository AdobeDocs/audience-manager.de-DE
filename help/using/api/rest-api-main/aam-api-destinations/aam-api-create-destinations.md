---
description: Erstellen Sie Ziele mit diesen RESTful-API-Methoden.
seo-description: Erstellen Sie Ziele mit diesen RESTful-API-Methoden.
seo-title: Erstellen von Zielen
solution: Audience Manager
title: Erstellen von Zielen
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 9%

---


# Erstellen von Zielen {#create-destinations}

Erstellen Sie Ziele mit den folgenden [!UICONTROL RESTful API]-Methoden.

<!-- c_create_destinations.xml -->

## Unterstützte Zieltypen: Nur URL und Cookie

Mit den verfügbaren `POST`-Methoden können Sie nur [!UICONTROL URL] und [!UICONTROL cookie destinations] erstellen. Zurzeit können Sie [!UICONTROL server-to-server destinations] mit diesen [!DNL REST API]-Methoden nicht erstellen. Mit den entsprechenden Methoden `GET` können Sie jedoch Informationen zu [!UICONTROL server-to-server destinations] abrufen, die in der Benutzeroberfläche erstellt wurden.

## Erstellen eines nicht seriellen URL-Ziels {#create-nonserial-dest}

Eine `POST`-Methode, mit der Sie ein Ziel erstellen können, das Segmente akzeptiert, die aus einzelnen Schlüssel-Wert-Paaren bestehen (z. B. `gender=male` oder `gender=female`).

<!-- r_create_nonserial_destination.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`

### Beispielanforderung

Diese Anforderung erstellt ein einzelnes Ziel. Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Antwort

Eine erfolgreiche Anforderung gibt `201 created` und das Ziel zurück.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4033, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (not serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"ACTIVE", 
   "destinationType":"PUSH", 
   "createTime":1338937116000, 
   "updateTime":1338937116000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":false, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "delimiter":null,
   "mappings":null
} 
```

## Erstellen eines serialisierten URL-Ziels {#create-serial-url-dest}

Eine `POST`-Methode, mit der Sie ein Ziel erstellen können, das mehrere Werte akzeptiert, die einem einzelnen Schlüssel zugeordnet sind (z. B. `color=blue, red, green`).

<!-- r_create_serial_url_destination.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`

### Beispielanforderung

Geben Sie das sichere [!DNL URL] und das Trennzeichen für das Schlüssel-Wert-Paar an, das an das Ziel übergeben wird. Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

```
{ 
   "name":"Sample URL Destination (Serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":true,
   "urlFormatString":"https://www.adobe.com/send?data=%ALIAS%",
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
   "delimiter":","
}
```

### Antwort

Bei einem erfolgreichen Update werden Antwortcode `201 created` und das Ziel zurückgegeben.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4034, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (Serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"active", 
   "destinationType":"PUSH", 
   "createTime":1338937420000, 
   "updateTime":1338937420000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":true, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%", 
   "delimiter":"-", 
   "mappings":null 
}
```

## Cookie-Ziel erstellen: Einzelschlüssel, nicht serialisiert {#create-cookie-dest-single}

Eine `POST`-Methode, mit der Sie eine [!UICONTROL cookie destination]-Methode erstellen können, die Segmente akzeptiert, die aus einzelnen Schlüssel-Wert-Paaren bestehen (z. B. `gender=male` oder `gender=female`).

<!-- r_cookie_destination_singlekey_noserial.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`

### Beispielanforderung

Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

```
{ 
   "name":"Cookie Destination Single Key Not Serialized",
   "destinationType":"ADS",
   "adServerTypeID":1,
   "cookieName":"adobe",
   "cnameDomain":"adobe.com",
   "maxSize":"2048",
   "ttl":"0",
   "domainRestrictions":"inclusion",
   "siteIDs":[
      312
   ],
   "formatType":"single_key",
   "singleKey":"key",
   "keySeparator":"=",
   "valueSeparator":",",
   "serializationEnabled":false
}
```

### Antwort

Bei einem erfolgreichen Update werden Antwortcode `201 created` und das Ziel zurückgegeben.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4035, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Not Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338937984000, 
   "updateTime":1338937984000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"inclusion", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"key", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
      312 
   ], 
   "uparamEnabled":false
} 
```

## Cookie-Ziel erstellen: Einzelschlüssel, serialisiert {#create-cookie-dest-single-serial}

Eine `POST`-Methode, mit der Sie ein Ziel erstellen können, das mehrere Werte akzeptiert, die einem einzelnen Schlüssel zugeordnet sind (z. B. `color=blue, red, green`).

<!-- r_cookie_destination_singlekey_serial.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`

### Beispielanforderung

Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

```
{ 
   "name":"Cookie Destination Single Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
 
   ], 
   "formatType":"single_key", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Antwort

Bei einem erfolgreichen Update werden Antwortcode `201 created` und das Ziel zurückgegeben.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4036, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938329000, 
   "updateTime":1338938329000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false
}
```

## Cookie-Ziel erstellen: Multi-Key, nicht serialisiert {#create-cookie-dest-multi}

Eine `POST`-Methode, mit der Sie ein Ziel erstellen können, das Segmente akzeptiert, die mehrere Schlüssel mit unterschiedlichen Werten enthalten (z. B. `gender=male; gender=female; color=blue; color=red`).

<!-- r_create_cookie_multikey_noserial.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`

### Beispielanforderung

Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

```
{ 
   "name":"Ad Server Multi-Key Not Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
  
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":false 
}
```

### Antwort

Bei einem erfolgreichen Update werden Antwortcode `201 created` und das Ziel zurückgegeben.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4037, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Not Serialized", 
   "status":1, 
   "destinationType":"ADS", 
   "createTime":1338938666000, 
   "updateTime":1338938666000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
  
   ], 
   "uparamEnabled":false 
}
```

## Cookie-Ziel erstellen: Multi-Key, serialisiert {#create-cookie-dest-multi-serial}

Eine `POST`-Methode, mit der Sie ein Ziel erstellen können, das Segmente akzeptiert, die mehrere Schlüssel und Werte enthalten (z. B. `gender=male, female; color=blue, red, green`).

<!-- r_cookie_destination_multikey_serial.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`

### Beispielanforderung

Sofern nicht anders angegeben, sind alle Anforderungswerte erforderlich.

```
{ 
   "name":"Cookie Destination Multi-Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains",
   "siteIDs":[ 
 
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Antwort

Bei einem erfolgreichen Update werden Antwortcode `201 created` und das Ziel zurückgegeben.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4038, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938872000, 
   "updateTime":1338938872000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false 
}
```

>[!MORELIKETHIS]
>
>* [Ziele ](../../../features/destinations/destinations.md)
>* [Ziel-Serialisierung](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Schlüssel-Wert-Paare – Erklärung](../../../reference/key-value-pairs-explained.md)

