---
description: Für dieses Verfahren sind eine adwords-Remarketing-Liste, ein Pixelcode und ein Zielgruppen-URL-Ziel erforderlich. Sie wird auch als Remarketing-Liste für Suchanzeigen (RLSA) bezeichnet. Gilt nur für gebührenpflichtige Suchvorgänge.
seo-description: Für dieses Verfahren sind eine adwords-Remarketing-Liste, ein Pixelcode und ein Zielgruppen-URL-Ziel erforderlich. Sie wird auch als Remarketing-Liste für Suchanzeigen (RLSA) bezeichnet. Gilt nur für gebührenpflichtige Suchvorgänge.
seo-title: Senden von Segmenten an eine Google adwords-Remarketing-Liste
solution: Audience Manager
title: Senden von Segmenten an eine Google adwords-Remarketing-Liste
uuid: 5 ad 821 c 6-48 b 4-42 c 0-b 912-1563331 e 93 a 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Send Segments to a Google Ads Remarketing List {#send-segments-to-a-google-adwords-remarketing-list}

This procedure requires a [!DNL Google Ads] remarketing list, pixel code, and an Audience Manager [!DNL URL] destination. It is also known as a remarketing list for search ads ([!DNL RLSA]) integration. Gilt nur für gebührenpflichtige Suchvorgänge.

>[!IMPORTANT]
>Beachten Sie, dass dies keine produktdefinierte Integration der beiden Systeme ist.

To set up a [!DNL Google Ads] remarketing list as an [!DNL Audience Manager] URL destination:

1. In your [!DNL Google Ads] account, [create a website re-marketing list](https://support.google.com/adwords/answer/2454064?hl=en) and write down your conversion ID.
1. Verwenden Sie die folgende URL als Vorlage für die Basis-URL und die sichere URL. Ersetzen Sie den xxxxxxxx-Abschnitt durch Ihre Konversions-ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. [Erstellen Sie in Audience Manager ein URL-Ziel](../../features/destinations/manage-destinations.md#configure-url-destination) oder bearbeiten Sie ein vorhandenes Ziel. Verwenden Sie beim Erstellen des Ziels die folgenden Einstellungen:
   * Typ: URL
   * Serialisieren: Aktiviert
   * Trennzeichen: Semikolon (;)

1. In the [!UICONTROL Segment Mappings] section of your [!DNL URL] destination, add the code from step 2 to the [!DNL URL] and [!DNL Secure URL] fields. Prefix the code with `http:` and `https:` in the [!DNL URL] and [!DNL Secure URL] fields, respectively.

   >[!IMPORTANT]
   >
   >Replace encoded ampersands `&` with un-encoded ampersands `&`

   Unsecure [!DNL URL] code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Secure [!DNL URL] code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Klicken Sie auf **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Wenn Sie mit mehreren Segmenten arbeiten, erhalten Sie ein neues Pixel für jedes Segment, das Sie einem Google Ads-Ziel zuordnen möchten. Dadurch wird sichergestellt, dass die Daten auf die entsprechende Remarketing-Liste angewendet werden.

1. When mapping a new segment to this destination in Audience Manager, define the mapping as `aam=segmentID` and replace `segmentID` with the ID of your segment.
1. When defining a bucket in [!DNL Google Ads], create a rule that matches the mapping defined at step 6.

Eine abgeschlossene Zuordnung könnte wie folgt aussehen:

![](../assets/rlsa_mapping.png)

>[!MORE_ LIKE_ THIS]
>
>* [Ziele](../../features/destinations/destinations.md)
>* [URL-Ziel erstellen](../../features/destinations/manage-destinations.md#configure-url-destination)
>* [Info zu adwords Remarketing Lists](https://support.google.com/adwords/answer/2472738)
>* [Funktionsweise von adwords Remarketing](https://support.google.com/adwords/answer/2454000)

