---
description: Methoden, mit denen Sie programmgesteuert mit der Data Integration Library (DIL) arbeiten können.
seo-description: Methods that let you work programmatically with the Data Integration Library (DIL).
seo-title: Data Integration Library API Methods
solution: Audience Manager
title: Data Integration Library-API-Methoden
uuid: 507e7afd-3ae7-44de-98b0-589d699c453b
feature: API
exl-id: d2f3e4e8-65be-4fec-90d7-5991514b8efc
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 3%

---

# Data Integration Library-API-Methoden {#data-integration-library-api-methods}

Methoden, mit denen Sie programmgesteuert mit dem [!UICONTROL Data Integration Library] arbeiten können ([!UICONTROL DIL].

>[!IMPORTANT]
>
>Die Data Integration Library-API wird nicht mehr unterstützt. Mit dieser API wurde DIL generiert, die Sie jetzt selbst hier herunterladen können: [DIL-Download](https://github.com/Adobe-Marketing-Cloud/dil/releases).

<!-- c_data_integr_library_api.xml -->

## Rückgabe von Versionen für DIL {#return-version-dil}

Eine `GET` Methode, die eine Liste der Versionen zurückgibt, die von der ältesten zur neuesten sortiert sind.

<!-- r_api_return_versions_dil.xml -->

### Anfrage

`GET https://api.demdex.com/v1/dil/`

### Antwort

Bei einer erfolgreichen Anfrage wird der Antwort-Code `["4.0", "4.1"]` wie unten dargestellt zurückgegeben.

```
["4.0", "4.1"]
```

## JSON-Schema für Version zurückgeben {#return-json-schema-version}

Eine `GET` Methode, die das [!DNL JSON] für die [!UICONTROL DIL] Version zurückgibt. Unterstützt die Verwendung von Alias-[!UICONTROL LATEST] für Version , um die neueste Version von [!UICONTROL DIL] zu erhalten.

<!-- r_api_return_json_schema_for_version.xml -->

### Anfrage

`GET https://api.demdex.com/v1/dil/`*`<version>`*

### Antwort

Eine erfolgreiche Anfrage gibt den Antwort-Code `["4.0", "4.1"]` und die Daten zurück, wie unten dargestellt.

```
{ 
    "type": "object", 
    "$schema": "https://json-schema.org/draft-03/schema", 
    "required": true, 
    "additionalProperties": false, 
    "properties": { 
        "core": { 
            "id": "core", 
            "required": true, 
            "type": "object", 
            "properties": { 
                "code": { 
                    "type": "boolean", 
                    "required": true, 
                    "id": "code" 
                }, 
                "instanceVariable": { 
                    "type": "string", 
                    "id": "instanceVariable", 
                    "required": false 
                }, 
                "create": { 
                    "type": "object", 
                    "id": "create", 
                    "required": false, 
                    "properties": { 
                        "initConfig": { 
                            "additionalProperties": false, 
                            "type": "object", 
                            "id": "initConfig", 
                            "required": true, 
                            "properties": { 
                                "declaredId": { 
                                    "id": "declaredId", 
                                    "required": false, 
                                    "type": "object", 
                                    "additionalProperties": false, 
                                    "properties": { 
                                        "dpid": { 
                                            "id": "dpid", 
                                            "required": true, 
                                            "type": "string" 
                                        }, 
                                        "dpuuid": { 
                                            "id": "dpuuid", 
                                            "required": true, 
                                            "type": "string" 
                                        } 
                                    } 
                                }, 
                                "containerNSID": { 
                                    "type": "number", 
                                    "id": "containerNSID", 
                                    "required": false 
                                }, 
                                "disableDestinationPublishingIframe": { 
                                    "type": "boolean", 
                                    "id": "disableDestinationPublishingIframe", 
                                    "required": false 
                                }, 
                                "enableErrorReporting": { 
                                    "type": "boolean", 
                                    "id": "enableErrorReporting", 
                                    "required": false 
                                }, 
                                "iframeAkamaiHTTPS": { 
                                    "type": "boolean", 
                                    "id": "iframeAkamaiHTTPS", 
                                    "required": false 
                                }, 
                                "iframeAttachmentDelay": { 
                                    "type": "number", 
                                    "id": "iframeAttachmentDelay", 
                                    "required": false 
                                }, 
                                "mappings": { 
                                    "type": "object", 
                                    "id": "mappings", 
                                    "required": false, 
                                    "additionalProperties": { 
                                        "type": "string" 
                                    } 
                                }, 
                                "removeFinishedScriptsAndCallbacks": { 
                                    "type": "boolean", 
                                    "id": "removeFinishedScriptsAndCallbacks", 
                                    "required": false 
                                }, 
                                "uuidCookie": { 
                                    "type": "object", 
                                    "id": "uuidCookie", 
                                    "additionalProperties": false, 
                                    "required": false, 
                                    "properties": { 
                                        "days": { 
                                            "type": "number", 
                                            "id": "days", 
                                            "required": false 
                                        }, 
                                        "domain": { 
                                            "type": "string", 
                                            "id": "domain", 
                                            "required": false 
                                        }, 
                                        "name": { 
                                            "type": "string", 
                                            "id": "name", 
                                            "required": true 
                                        }, 
                                        "path": { 
                                            "type": "string", 
                                            "id": "path", 
                                            "required": false 
                                        }, 
                                        "secure": { 
                                            "type": "boolean", 
                                            "id": "secure", 
                                            "required": false 
                                        } 
                                    } 
                                }, 
                                "visitorService": { 
                                    "type": "object", 
                                    "id": "visitorService", 
                                    "required": false, 
                                    "properties": { 
                                        "namespace": { 
                                            "type": "string", 
                                            "id": "namespace", 
                                            "required": true 
                                        } 
                                    } 
                                } 
                            } 
                        } 
                    } 
                } 
            } 
        }, 
        "options": { 
            "id": "options", 
            "type": "object", 
            "required": false, 
            "properties": { 
                "minify": { 
                    "id": "minify", 
                    "required": false, 
                    "type": "boolean" 
                } 
            } 
        }, 
        "include": { 
            "type": "object", 
            "id": "include", 
            "required": false, 
            "properties": { 
                "modules": { 
                    "type": "object", 
                    "id": "modules", 
                    "required": false, 
                    "additionalProperties": false, 
                    "properties": { 
                        "GoogleAnalytics": { 
                            "type": "object", 
                            "id": "GoogleAnalytics", 
                            "required": false, 
                            "properties": { 
                                "code": { 
                                    "id": "code", 
                                    "type": "boolean", 
                                    "required": true 
                                } 
                            } 
                        }, 
                        "Peer39": { 
                            "type": "object", 
                            "id": "Peer39", 
                            "required": false, 
                            "properties": { 
                                "code": { 
                                    "id": "code", 
                                    "type": "boolean", 
                                    "required": true 
                                } 
                            } 
                        }, 
                        "SiteCatalyst": { 
                            "type": "object", 
                            "id": "SiteCatalyst", 
                            "required": false, 
                            "additionalProperties": false, 
                            "properties": { 
                                "code": { 
                                    "type": "boolean", 
                                    "id": "code", 
                                    "required": true 
                                }, 
                                "init": { 
                                    "type": "object", 
                                    "id": "init", 
                                    "required": false, 
                                    "additionalProperties": false, 
                                    "properties": { 
                                        "siteCatalystInstance": { 
                                            "type": "string", 
                                            "id": "siteCatalystInstance", 
                                            "required": true 
                                        }, 
                                        "dilInstance": { 
                                            "type": "string", 
                                            "id": "dilInstance", 
                                            "required": true 
                                        }, 
                                        "trackedVariables": { 
                                            "id": "trackedVariables", 
                                            "required": false, 
                                            "type": "object", 
                                            "properties": { 
                                                "iteratedNames": { 
                                                    "type": "array", 
                                                    "id": "iteratedNames", 
                                                    "required": false, 
                                                    "items": { 
                                                        "type": "object", 
                                                        "id": "0", 
                                                        "required": true, 
                                                        "properties": { 
                                                            "maxIndex": { 
                                                                "type": "number", 
                                                                "id": "maxIndex", 
                                                                "required": true 
                                                            }, 
                                                            "name": { 
                                                                "type": "string", 
                                                                "id": "name", 
                                                                "required": true 
                                                            } 
                                                        } 
                                                    } 
                                                }, 
                                                "names": { 
                                                    "type": "array", 
                                                    "additionalItems": false, 
                                                    "id": "names", 
                                                    "required": false, 
                                                    "items": [ 
                                                        { 
                                                            "type": "string", 
                                                            "required": true 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        } 
                                                    ] 
                                                } 
                                            } 
                                        } 
                                    } 
                                } 
                            } 
                        } 
                    } 
                }, 
                "tools": { 
                    "type": "object", 
                    "id": "tools", 
                    "required": false, 
                    "additionalProperties": false, 
                    "properties": { 
                        "getMetaTags": { 
                            "type": "boolean", 
                            "id": "getMetaTags", 
                            "required": false 
                        }, 
                        "getSearchReferrer": { 
                            "type": "boolean", 
                            "id": "getSearchReferrer", 
                            "required": false 
                        }, 
                        "decomposeURI": { 
                            "type": "boolean", 
                            "id": "decomposeURI", 
                            "required": false 
                        } 
                    } 
                } 
            } 
        } 
    } 
} 
```

## DIL generieren {#generate-dil}

Eine `GET` Methode, die [!UICONTROL DIL] basierend auf dem übergebenen Anfragetext unter Verwendung der angegebenen Version von [!UICONTROL DIL] generiert. Wenn der Alias `LATEST` für die Version in der URL verwendet wird, wird die neueste Version von [!UICONTROL DIL] generiert.

<!-- r_api_generate_dil.xml -->

### Anfrage

`POST https://api.demdex.com/v1/dil/`*`<version>`*`/generate`

### Beispielanforderung

```
{ 
    core: { 
        code: true, 
        instanceVariable: 'dil_instance', 
        create: { 
            initConfig: { 
                declaredId: { 
                    dpid: '159', 
                    dpuuid: '456' 
                }, 
                containerNSID: 81, 
                disableDestinationPublishingIframe: false, 
                enableErrorReporting: false, 
                iframeAkamaiHTTPS: false, 
                iframeAttachmentDelay: 575, 
                mappings: { 
                    c_k1: 'd_k1', 
                    c_k2: 'd_k2' 
                }, 
                removeFinishedScriptsAndCallbacks: false, 
                uuidCookie: { 
                    days: 12, 
                    domain: 'adobe.com', 
                    name: 'adobe_did', 
                    path: '/', 
                    secure: false 
                }, 
                visitorService: { 
                    namespace: 'demofirst' 
                } 
            } 
        } 
    }, 
    options: { 
        minify: true 
    }, 
    include: { 
        modules: { 
            GoogleAnalytics: { 
                code: true 
            }, 
            Peer39: { 
                code: true 
            }, 
            SiteCatalyst: { 
                code: true, 
                init: { 
                    siteCatalystInstance: 'sc_instance', 
                    dilInstance: 'dil_instance', 
                    trackedVariables: { 
                        iteratedNames: [{ 
                            name: 'prop', 
                            maxIndex: 5 
                        }, { 
                            name: 'pev', 
                            maxIndex: 3 
                        }], 
                        names: ['pageName', 'channel', 'campaign', 'products', 'events', 'spe', 'spev1', 'spev2', 'spev3'] 
                    } 
                } 
            } 
        }, 
        tools: { 
            getMetaTags: true, 
            getSearchReferrer: true, 
            decomposeURI: true 
        } 
    } 
} 
```

### Antwort

Bei einer erfolgreichen Aktualisierung wird der Antwort-Code `201 created` zusammen mit dem [!UICONTROL DIL] [!DNL JavaScript]-Code zurückgegeben.
