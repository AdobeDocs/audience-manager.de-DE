---
description: Einfache Pixel (die zur Qualifizierung von Benutzern für Eigenschaften verwendet werden können) führen Datenübertragungen in Echtzeit durch. Über die Audience Manager-Oberfläche können Clients eine beliebige Anzahl Pixel auf Selbstbedienungsbasis erstellen. Pixelzeichenfolgen bestehen aus einfachen IDs oder Schlüssel/Wert-Paaren.
seo-description: Einfache Pixel (die zur Qualifizierung von Benutzern für Eigenschaften verwendet werden können) führen Datenübertragungen in Echtzeit durch. Über die Audience Manager-Oberfläche können Clients eine beliebige Anzahl Pixel auf Selbstbedienungsbasis erstellen. Pixelzeichenfolgen bestehen aus einfachen IDs oder Schlüssel/Wert-Paaren.
seo-title: Pixelbasierte Datenübertragung
solution: Audience Manager
title: Pixelbasierte Datenübertragung
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Pixelbasierte Datenübertragung {#pixel-based-data-transfers}

Einfache Pixel (die zur Qualifizierung von Benutzern für Eigenschaften verwendet werden können) führen Datenübertragungen in Echtzeit durch. Über die Audience Manager-Oberfläche können Clients eine beliebige Anzahl Pixel auf Selbstbedienungsbasis erstellen. Pixelzeichenfolgen bestehen aus einfachen IDs oder Schlüssel/Wert-Paaren.

<!-- c_rt_inbound_pixel_transfers.xml -->

Um eingehende Datenübertragungen zu aktivieren, würden Anbieter und Client:

1. Bestimmen Sie, welche Eigenschaften vom Anbieter oder Partner ausgelöst werden sollen.
1. Rufen Sie das Pixel für die Eigenschaft ab. Bewegen Sie den Mauszeiger im Bildschirm "Eigenschaften"über die **[!UICONTROL Actions]** Spalte und klicken Sie auf das **[!UICONTROL Get trait URL]** Symbol für die gewünschte Eigenschaft.
1. Stellen Sie die [!DNL URL] Informationen dem Anbieter oder Partner zur Verfügung.

## Beispiele

Dieser grundlegende Ereignisaufruf sendet die Eigenschaften-ID 1234 an [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Sie können Eigenschaften-IDs in einem Ereignisaufruf serialisieren, um den `HTTP` Traffic von der Seite zu reduzieren. Fügen Sie der URL-Zeichenfolge wie im folgenden Beispiel zusätzliche Eigenschaften-IDs hinzu:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
