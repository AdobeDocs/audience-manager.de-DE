---
description: Einfache Pixel (die zum Qualifizieren von Benutzern für Eigenschaften verwendet werden können) führen Echtzeit-Datenübertragungen durch. Mit der Audience Manager-Oberfläche können Clients eine beliebige Anzahl von Pixeln selbstständig erstellen. Pixelzeichenfolgen bestehen aus einfachen IDs oder Schlüsselwertpaaren.
seo-description: Einfache Pixel (die zum Qualifizieren von Benutzern für Eigenschaften verwendet werden können) führen Echtzeit-Datenübertragungen durch. Mit der Audience Manager-Oberfläche können Clients eine beliebige Anzahl von Pixeln selbstständig erstellen. Pixelzeichenfolgen bestehen aus einfachen IDs oder Schlüsselwertpaaren.
seo-title: Pixelbasierte Datenübertragungen
solution: Audience Manager
title: Pixelbasierte Datenübertragungen
uuid: 8773 bfc 0-6 b 8 d -4 a 6 a-a 8 b 7-e 043744486 ab
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Pixelbasierte Datenübertragungen {#pixel-based-data-transfers}

Einfache Pixel (die zum Qualifizieren von Benutzern für Eigenschaften verwendet werden können) führen Echtzeit-Datenübertragungen durch. Mit der Audience Manager-Oberfläche können Clients eine beliebige Anzahl von Pixeln selbstständig erstellen. Pixelzeichenfolgen bestehen aus einfachen IDs oder Schlüsselwertpaaren.

<!-- c_rt_inbound_pixel_transfers.xml -->

Um eingehende Datenübertragungen zu aktivieren, würde der Anbieter und Client:

1. Legen Sie fest, welche Eigenschaften der Anbieter oder Partner auslösen soll.
1. Besorgen Sie sich das Pixel für die Eigenschaft. Bewegen Sie den Mauszeiger im Bildschirm der Eigenschaftsliste über die **[!UICONTROL Actions]** Spalte und klicken Sie auf das **[!UICONTROL Get trait URL]** Symbol für die gewünschte Eigenschaft.
1. Geben Sie [!DNL URL] dem Anbieter oder Partner die Möglichkeit.

## Beispiele

Dieser einfache Ereignisaufruf sendet Eigenschaften-ID 1234 an [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Sie können Eigenschaften-IDs in einem Ereignisaufruf serialisieren, um `HTTP` den Traffic von der Seite zu reduzieren. Fügen Sie zusätzliche Eigenschafts-IDs an die URL-Zeichenfolge hinzu, wie im folgenden Beispiel gezeigt:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
