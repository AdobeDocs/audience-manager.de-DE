---
description: Für dieses Verfahren sind eine adwords-Remarketing-Liste, ein Pixelcode und ein Zielgruppen-URL-Ziel erforderlich. Sie wird auch als Remarketing-Liste für Suchanzeigen (RLSA) bezeichnet. Gilt nur für gebührenpflichtige Suchvorgänge.
seo-description: Für dieses Verfahren sind eine adwords-Remarketing-Liste, ein Pixelcode und ein Zielgruppen-URL-Ziel erforderlich. Sie wird auch als Remarketing-Liste für Suchanzeigen (RLSA) bezeichnet. Gilt nur für gebührenpflichtige Suchvorgänge.
seo-title: Senden von Segmenten an eine Google adwords-Remarketing-Liste
solution: Audience Manager
title: Senden von Segmenten an eine Google adwords-Remarketing-Liste
uuid: 5 ad 821 c 6-48 b 4-42 c 0-b 912-1563331 e 93 a 2
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Senden von Segmenten an eine Google Ads-Remarketing-Liste {#send-segments-to-a-google-adwords-remarketing-list}

Für dieses Verfahren sind eine [!DNL Google Ads] Remarketing-Liste, ein Pixelcode und ein Zielgruppen-Manager [!DNL URL] -Ziel erforderlich. Sie wird auch als Remarketing-Liste für Search Ads ([!DNL RLSA])-Integration bezeichnet. Gilt nur für gebührenpflichtige Suchvorgänge.

>[!IMPORTANT]
>Beachten Sie, dass dies keine produktdefinierte Integration der beiden Systeme ist.

So richten Sie eine [!DNL Google Ads] Remarketing-Liste als [!DNL Audience Manager] URL-Ziel ein:

1. Erstellen Sie in Ihrem [!DNL Google Ads][Konto eine Website-Remarketing-Liste](https://support.google.com/adwords/answer/2454064?hl=en) und schreiben Sie Ihre Konversions-ID.
1. Verwenden Sie die folgende URL als Vorlage für die Basis-URL und die sichere URL. Ersetzen Sie den xxxxxxxx-Abschnitt durch Ihre Konversions-ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. [Erstellen Sie in Audience Manager ein URL-Ziel](../../features/destinations/create-url-destination.md) oder bearbeiten Sie ein vorhandenes Ziel. Verwenden Sie beim Erstellen des Ziels die folgenden Einstellungen:
   * Typ: URL
   * Serialisieren: Aktiviert
   * Trennzeichen: Semikolon (;)

1. Fügen Sie im [!UICONTROL Segment Mappings] Abschnitt Ihres [!DNL URL] Ziels den Code aus Schritt 2 in [!DNL URL] die Felder ein [!DNL Secure URL] . Präfix des Codes mit `http:` und `https:`[!DNL URL] in [!DNL Secure URL] den Feldern.

   >[!IMPORTANT]
   >
   >Kodierte Kaufmännische `&` durch dekodierte und nicht kodierte Zeichen ersetzen `&`

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
   >Wenn Sie mit mehreren Segmenten arbeiten, erhalten Sie ein neues Pixel für jedes Segment, das Sie einem Google Ads-Ziel zuordnen möchten. Dadurch wird sichergestellt, dass die Daten auf die entsprechende Remarketing-Liste angewendet werden.

1. Wenn Sie ein neues Segment diesem Ziel in Audience Manager zuordnen, definieren Sie die Zuordnung als `aam=segmentID` und ersetzen Sie sie durch `segmentID` die ID Ihres Segments.
1. Erstellen Sie beim Definieren eines [!DNL Google Ads]Behälters eine Regel, die mit der in Schritt 6 definierten Zuordnung übereinstimmt.

Eine abgeschlossene Zuordnung könnte wie folgt aussehen:

![](../assets/rlsa_mapping.png)

>[!MORE_ LIKE_ THIS]
>
>* [Ziele](../../features/destinations/destinations.md)
>* [URL-Ziel erstellen](../../features/destinations/create-url-destination.md)
>* [Info zu adwords Remarketing Lists](https://support.google.com/adwords/answer/2472738)
>* [Funktionsweise von adwords Remarketing](https://support.google.com/adwords/answer/2454000)

