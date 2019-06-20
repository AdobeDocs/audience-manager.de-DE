---
description: Erstellen Sie Ziele mit diesen restful-API-Methoden.
seo-description: Erstellen Sie Ziele mit diesen restful-API-Methoden.
seo-title: Ziele erstellen
solution: Audience Manager
title: Ziele erstellen
uuid: 12 f 04151-ad 0 e -4 cb 6-8 f 3 b-b 5 c 427 dc 2 cef
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ziele erstellen {#create-destinations}

Erstellen Sie Ziele mit diesen [!UICONTROL RESTful API] Methoden.

<!-- c_create_destinations.xml -->

## Unterstützte Zieltypen: Nur URL und Cookie

Mit den verfügbaren `POST` Methoden [!UICONTROL URL][!UICONTROL cookie destinations] können Sie erstellen. Derzeit können Sie nicht [!UICONTROL server-to-server destinations] mit diesen [!DNL REST API] Methoden erstellen. Mit den zugehörigen Zielmethoden `GET` können Sie jedoch Informationen über [!UICONTROL server-to-server destinations] die in der Benutzeroberfläche erstellten Informationen abrufen.

>[!MORE_ LIKE_ THIS]
>
>* [Ziele](../../../features/destinations/destinations.md#destination-api-methods)
>* [Zielreihenbildung](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Wichtige Wertpaare](../../../reference/key-value-pairs-explained.md)


## Nicht-Serial URL-Ziel erstellen {#create-nonserial-dest}

`POST` Eine Methode, mit der Sie ein Ziel erstellen können, das Segmente akzeptiert, die aus einzelnen Schlüsselwertpaaren bestehen (z. B. `gender=male` oder `gender=female`).

<!-- r_create_nonserial_destination.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`

### Beispielanforderung

Diese Anforderung erstellt ein einzelnes Ziel. Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Antwort

Eine erfolgreiche Anforderung gibt zurück `201 created` und das Ziel.

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

>[!MORE_ LIKE_ THIS]
>
>* [Zielreihenbildung](../../../features/destinations/key-value-pairs.md#destination-serialized)


## Ein serialisiertes URL-Ziel erstellen {#create-serial-url-dest}

`POST` Eine Methode, mit der Sie ein Ziel erstellen können, das mehrere Werte akzeptiert, die mit einem einzelnen Schlüssel verknüpft sind (z. `color=blue, red, green`B.).

<!-- r_create_serial_url_destination.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`

### Beispielanforderung

Geben Sie das sichere [!DNL URL] und Trennzeichen für das Schlüssel-Wert-Paar an, das an das Ziel weitergegeben wird. Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

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

Ein erfolgreicher Update gibt Antwortcode `201 created` und das Ziel zurück.

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

>[!MORE_ LIKE_ THIS]
>
>* [Zielreihenbildung](../../../features/destinations/key-value-pairs.md#destination-serialized)


## Cookie-Ziel erstellen: Einzelschlüssel, nicht serialisiert {#create-cookie-dest-single}

`POST` Eine Methode, mit der Sie ein [!UICONTROL cookie destination] Segment erstellen können, das aus einzelnen Schlüsselwertpaaren (z. B. `gender=male` oder `gender=female`) besteht.

<!-- r_cookie_destination_singlekey_noserial.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`

### Beispielanforderung

Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

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

Ein erfolgreicher Update gibt Antwortcode `201 created` und das Ziel zurück.

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

>[!MORE_ LIKE_ THIS]
>
>* [Zielreihenbildung](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Wichtige Wertpaare](../../../reference/key-value-pairs-explained.md)


## Cookie-Ziel erstellen: Einzelner Schlüssel, serialisiert {#create-cookie-dest-single-serial}

`POST` Eine Methode, mit der Sie ein Ziel erstellen können, das mehrere Werte akzeptiert, die mit einem einzelnen Schlüssel verknüpft sind (z. `color=blue, red, green`B.).

<!-- r_cookie_destination_singlekey_serial.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`

### Beispielanforderung

Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

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

Ein erfolgreicher Update gibt Antwortcode `201 created` und das Ziel zurück.

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

>[!MORE_ LIKE_ THIS]
>
>* [Zielreihenbildung](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Wichtige Wertpaare](../../../reference/key-value-pairs-explained.md)


## Cookie-Ziel erstellen: Mehrere Schlüssel, nicht serialisiert {#create-cookie-dest-multi}

`POST` Eine Methode, mit der Sie ein Ziel erstellen können, das Segmente akzeptiert, die mehrere Schlüssel mit verschiedenen Werten enthalten (z. `gender=male; gender=female; color=blue; color=red`B.).

<!-- r_create_cookie_multikey_noserial.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`

### Beispielanforderung

Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

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

Ein erfolgreicher Update gibt Antwortcode `201 created` und das Ziel zurück.

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

## Cookie-Ziel erstellen: Mehrere Schlüssel, serialisierung {#create-cookie-dest-multi-serial}

`POST` Eine Methode, mit der Sie ein Ziel erstellen können, das Segmente akzeptiert, die mehrere Schlüssel und Werte enthalten (z. `gender=male, female; color=blue, red, green`B.).

<!-- r_cookie_destination_multikey_serial.xml -->

### Anfrage

`POST https://api.demdex.com/v1/destinations/`

### Beispielanforderung

Alle Anforderungswerte sind erforderlich, sofern nicht anders angegeben.

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

Ein erfolgreicher Update gibt Antwortcode `201 created` und das Ziel zurück.

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

>[!MORE_ LIKE_ THIS]
>
>* [Zielreihenbildung](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Wichtige Wertpaare](../../../reference/key-value-pairs-explained.md)

