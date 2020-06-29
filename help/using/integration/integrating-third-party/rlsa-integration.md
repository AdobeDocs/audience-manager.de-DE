---
description: Dieser Vorgang erfordert eine AdWords-Remarketing-Liste, Pixelcode und ein Audience Manager-URL-Ziel. Es wird auch als Remarketing-Liste für die RLSA-Integration (Search Ads) bezeichnet. Gilt nur für die gebührenpflichtige Suche.
seo-description: Dieser Vorgang erfordert eine AdWords-Remarketing-Liste, Pixelcode und ein Audience Manager-URL-Ziel. Es wird auch als Remarketing-Liste für die RLSA-Integration (Search Ads) bezeichnet. Gilt nur für die gebührenpflichtige Suche.
seo-title: Segmente an eine Marketing-Liste für Google AdWords senden
solution: Audience Manager
title: Segmente an eine Marketing-Liste für Google AdWords senden
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---


# Segmente an eine Remarketing-Liste für Google-Anzeigen senden {#send-segments-to-a-google-adwords-remarketing-list}

Dieser Vorgang erfordert eine [!DNL Google Ads] Remarketing-Liste, Pixelcode und einen Audience Manager [!DNL URL] [!DNL destination]. Es wird auch als Remarketing-Liste für die Integration von Suchmaschinenwerbung ([!DNL RLSA]) bezeichnet. Gilt nur für die gebührenpflichtige Suche.

>[!IMPORTANT]
>Bitte beachten Sie, dass es sich hierbei nicht um eine produktive Integration der beiden Systeme handelt.

So richten Sie eine [!DNL Google Ads] Remarketing-Liste als [!DNL Audience Manager] ein [!DNL URL destination]:

1. Erstellen Sie in Ihrem [!DNL Google Ads] Konto eine Website-Remarketing-Liste [](https://support.google.com/adwords/answer/2454064?hl=en) und schreiben Sie Ihre Konversions-ID auf.
1. Verwenden Sie die folgende URL als Vorlage für die Basis-URL und die sichere URL. Ersetzen Sie den Abschnitt xxxxxx durch Ihre Konversions-ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager [erstellen Sie ein [!DNL-URL-Ziel]](../../features/destinations/create-url-destination.md) oder bearbeiten Sie ein vorhandenes [!DNL destination]. Verwenden Sie beim Erstellen der [!DNL destination]Variablen die folgenden Einstellungen:
   * Typ: URL
   * Serialisieren: Aktiviert
   * Trennzeichen: Semikolon (;)

1. Fügen Sie im [!UICONTROL Segment Mappings] Abschnitt Ihres [!DNL URL] Codes den Code aus Schritt 2 in die Felder [!DNL destination]und [!DNL URL] [!DNL Secure URL] ein. Präfix des Codes mit `http:` und `https:` in den [!DNL URL] bzw. [!DNL Secure URL] den Feldern

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

1. Klicken **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Wenn Sie mit mehreren Segmenten arbeiten, erhalten Sie für jedes Segment, das Sie einem Segment zuordnen möchten, ein neues Pixel [!DNL Google Ads][!DNL destination]. Dadurch wird sichergestellt, dass die Daten auf die entsprechende Remarketing-Liste angewendet werden.

1. Definieren Sie beim Zuordnen eines neuen Segments zu diesem Segment [!DNL destination] in Audience Manager die Zuordnung als `aam=segmentID` und ersetzen Sie sie `segmentID` durch die ID Ihres Segments.
1. Erstellen Sie beim Definieren eines Behälters in [!DNL Google Ads]eine Regel, die der in Schritt 6 definierten Zuordnung entspricht.

Eine abgeschlossene Zuordnung könnte wie folgt aussehen:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL-Ziele]](../../features/destinations/destinations.md)
>* [Erstellen eines [!DNL-URL-Ziels]](../../features/destinations/create-url-destination.md)
>* [AdWords Remarketing-Listen](https://support.google.com/adwords/answer/2472738)
>* [Funktionsweise von AdWords Remarketing](https://support.google.com/adwords/answer/2454000)

