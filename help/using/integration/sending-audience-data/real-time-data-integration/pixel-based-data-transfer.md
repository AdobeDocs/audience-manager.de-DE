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


# Pixel-based Data Transfers {#pixel-based-data-transfers}

Einfache Pixel (die zum Qualifizieren von Benutzern für Eigenschaften verwendet werden können) führen Echtzeit-Datenübertragungen durch. Mit der Audience Manager-Oberfläche können Clients eine beliebige Anzahl von Pixeln selbstständig erstellen. Pixelzeichenfolgen bestehen aus einfachen IDs oder Schlüsselwertpaaren.

<!-- c_rt_inbound_pixel_transfers.xml -->

Um eingehende Datenübertragungen zu aktivieren, würde der Anbieter und Client:

1. Legen Sie fest, welche Eigenschaften der Anbieter oder Partner auslösen soll.
1. Besorgen Sie sich das Pixel für die Eigenschaft. In the traits list screen, hover over the **[!UICONTROL Actions]** column and click the **[!UICONTROL Get trait URL]** symbol for the desired trait.
1. Provide the [!DNL URL] to the vendor or partner.

## Beispiele

This basic event call sends trait ID 1234 to [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

You can serialize trait IDs in an event call to help reduce `HTTP` traffic from the page. Fügen Sie zusätzliche Eigenschafts-IDs an die URL-Zeichenfolge hinzu, wie im folgenden Beispiel gezeigt:

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
