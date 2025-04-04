---
description: Einfache Pixel (die verwendet werden können, um Benutzer für Eigenschaften zu qualifizieren) führen Echtzeit-Datenübertragungen durch. Über die Audience Manager-Benutzeroberfläche können Clients im Selbstbedienungsmodus eine beliebige Anzahl von Pixeln erstellen. Pixel-Zeichenfolgen bestehen aus einfachen IDs oder Schlüssel-Wert-Paaren.
seo-description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-title: Pixel-based Data Transfers
solution: Audience Manager
title: Pixelbasierte Datenübertragungen
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# Pixelbasierte Datenübertragungen {#pixel-based-data-transfers}

Einfache Pixel (die verwendet werden können, um Benutzer für Eigenschaften zu qualifizieren) führen Echtzeit-Datenübertragungen durch. Über die Audience Manager-Benutzeroberfläche können Clients im Selbstbedienungsmodus eine beliebige Anzahl von Pixeln erstellen. Pixel-Zeichenfolgen bestehen aus einfachen IDs oder Schlüssel-Wert-Paaren.

<!-- c_rt_inbound_pixel_transfers.xml -->

Um eingehende Datenübertragungen zu aktivieren, gehen Anbieter und Client folgendermaßen vor:

1. Bestimmen Sie, welche Eigenschaften der Anbieter oder Partner auslösen soll.
1. Ruft den Pixel für die Eigenschaft ab. Bewegen Sie im Bildschirm Eigenschaftenliste den Mauszeiger über die Spalte **[!UICONTROL Actions]** und klicken Sie auf das **[!UICONTROL Get trait URL]** für die gewünschte Eigenschaft.
1. Stellen Sie dem Anbieter oder Partner die [!DNL URL] bereit.

## Beispiele

Dieser grundlegende Ereignisaufruf sendet die Trait-ID 1234 an [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Sie können Eigenschaften-IDs in einem Ereignisaufruf serialisieren, um den `HTTP` Traffic von der Seite zu reduzieren. Hängen Sie zusätzliche Eigenschafts-IDs an die URL-Zeichenfolge an, wie im folgenden Beispiel gezeigt:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
