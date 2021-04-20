---
description: Einfache Pixel (die verwendet werden können, um Benutzer für Eigenschaften zu qualifizieren) führen Datenübertragungen in Echtzeit durch. Die Audience Manager-Oberfläche ermöglicht es Clients, eine beliebige Pixelanzahl auf Selbstbedienungsbasis zu erstellen. Pixelzeichenfolgen bestehen aus einfachen IDs oder Schlüssel/Wert-Paaren.
seo-description: Einfache Pixel (die verwendet werden können, um Benutzer für Eigenschaften zu qualifizieren) führen Datenübertragungen in Echtzeit durch. Die Audience Manager-Oberfläche ermöglicht es Clients, eine beliebige Pixelanzahl auf Selbstbedienungsbasis zu erstellen. Pixelzeichenfolgen bestehen aus einfachen IDs oder Schlüssel/Wert-Paaren.
seo-title: Pixelbasierte Datenübertragungen
solution: Audience Manager
title: Pixelbasierte Datenübertragungen
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 5%

---

# Pixelbasierte Datenübertragungen {#pixel-based-data-transfers}

Einfache Pixel (die verwendet werden können, um Benutzer für Eigenschaften zu qualifizieren) führen Datenübertragungen in Echtzeit durch. Die Audience Manager-Oberfläche ermöglicht es Clients, eine beliebige Pixelanzahl auf Selbstbedienungsbasis zu erstellen. Pixelzeichenfolgen bestehen aus einfachen IDs oder Schlüssel/Wert-Paaren.

<!-- c_rt_inbound_pixel_transfers.xml -->

Um eingehende Datenübertragungen zu aktivieren, würden Anbieter und Client:

1. Bestimmen Sie, welche Eigenschaften vom Anbieter oder Partner ausgelöst werden sollen.
1. Rufen Sie das Pixel für die Eigenschaft ab. Bewegen Sie den Mauszeiger im Bildschirm &quot;Liste der Eigenschaften&quot;über die Spalte **[!UICONTROL Actions]** und klicken Sie auf das **[!UICONTROL Get trait URL]**-Symbol für die gewünschte Eigenschaft.
1. Stellen Sie [!DNL URL] dem Anbieter oder Partner bereit.

## Beispiele

Dieser grundlegende Ereignis-Aufruf sendet die Eigenschaften-ID 1234 an [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Sie können Eigenschaften-IDs in einem Ereignis-Aufruf serialisieren, um den Datenverkehr von der Seite zu verringern. `HTTP` Fügen Sie der URL-Zeichenfolge weitere Eigenschaften-IDs hinzu, wie im folgenden Beispiel gezeigt:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
