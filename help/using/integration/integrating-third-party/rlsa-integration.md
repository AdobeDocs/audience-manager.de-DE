---
description: Dieser Vorgang erfordert eine AdWords-Remarketing-Liste, Pixelcode und ein Zielort für die Audience Manager-URL. Es wird auch als Remarketing-Liste für die RLSA-Integration (Search Ads) bezeichnet. Gilt nur für die gebührenpflichtige Suche.
seo-description: Dieser Vorgang erfordert eine AdWords-Remarketing-Liste, Pixelcode und ein Zielort für die Audience Manager-URL. Es wird auch als Remarketing-Liste für die RLSA-Integration (Search Ads) bezeichnet. Gilt nur für die gebührenpflichtige Suche.
seo-title: Segmente an eine Google AdWords Remarketing-Liste senden
solution: Audience Manager
title: Segmente an eine Google AdWords Remarketing-Liste senden
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Segmente an eine Remarketing-Liste für Google-Anzeigen senden {#send-segments-to-a-google-adwords-remarketing-list}

Dieser Vorgang erfordert eine [!DNL Google Ads] Remarketing-Liste, Pixelcode und ein Audience Manager- [!DNL URL] Ziel. Es wird auch als Remarketing-Liste für die Integration von Suchmaschinenwerbung ([!DNL RLSA]) bezeichnet. Gilt nur für die gebührenpflichtige Suche.

>[!IMPORTANT]
>Bitte beachten Sie, dass es sich hierbei nicht um eine produktive Integration der beiden Systeme handelt.

So richten Sie eine [!DNL Google Ads] Remarketing-Liste als [!DNL Audience Manager] URL-Ziel ein:

1. Erstellen Sie in Ihrem [!DNL Google Ads] Konto eine Website-Remarketing-Liste[ ](https://support.google.com/adwords/answer/2454064?hl=en)und schreiben Sie Ihre Konversions-ID auf.
1. Verwenden Sie die folgende URL als Vorlage für die Basis-URL und die sichere URL. Ersetzen Sie den Abschnitt xxxxxx durch Ihre Konversions-ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager [erstellen Sie ein URL-Ziel](../../features/destinations/create-url-destination.md) oder bearbeiten Sie ein vorhandenes Ziel. Verwenden Sie beim Erstellen des Ziels die folgenden Einstellungen:
   * Typ:URL
   * Serialisieren: Aktiviert
   * Trennzeichen: Semikolon (;)

1. Fügen Sie im [!UICONTROL Segment Mappings] Abschnitt Ihres [!DNL URL] Ziels den Code aus Schritt 2 den Feldern [!DNL URL] und [!DNL Secure URL] hinzu. Präfix des Codes mit `http:` und `https:` in den [!DNL URL] bzw. [!DNL Secure URL] den Feldern

   >[!IMPORTANT]
   >
   >Kodierte Ampersands `&` durch nicht kodierte Ampersands ersetzen `&`

   Unsicherer [!DNL URL] Code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Sicherer [!DNL URL] Code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Klicken Sie auf **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Wenn Sie mit mehreren Segmenten arbeiten, erhalten Sie für jedes Segment, das Sie einem Google Ads-Ziel zuordnen möchten, ein neues Pixel. Dadurch wird sichergestellt, dass die Daten auf die entsprechende Remarketing-Liste angewendet werden.

1. Definieren Sie beim Zuordnen eines neuen Segments zu diesem Ziel in Audience Manager die Zuordnung als `aam=segmentID` und ersetzen Sie sie durch die ID Ihres Segments `segmentID` .
1. Erstellen Sie beim Definieren eines Behälters in [!DNL Google Ads]eine Regel, die der in Schritt 6 definierten Zuordnung entspricht.

Eine abgeschlossene Zuordnung könnte wie folgt aussehen:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [Ziele](../../features/destinations/destinations.md)
>* [URL-Ziel erstellen](../../features/destinations/create-url-destination.md)
>* [Info zu AdWords Remarketing-Listen](https://support.google.com/adwords/answer/2472738)
>* [Funktionsweise von AdWords Remarketing](https://support.google.com/adwords/answer/2454000)

