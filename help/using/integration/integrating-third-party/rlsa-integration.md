---
description: Dieser Vorgang erfordert eine AdWords-Remarketing-Liste, Pixelcode und ein Audience Manager-URL-Ziel. Es wird auch als Remarketing-Liste für die RLSA-Integration (Search Ads) bezeichnet. Gilt nur für die gebührenpflichtige Suche.
seo-description: Dieser Vorgang erfordert eine AdWords-Remarketing-Liste, Pixelcode und ein Audience Manager-URL-Ziel. Es wird auch als Remarketing-Liste für die RLSA-Integration (Search Ads) bezeichnet. Gilt nur für die gebührenpflichtige Suche.
seo-title: Senden von Segmenten an eine Remarketing-Liste für Google AdWords
solution: Audience Manager
title: Senden von Segmenten an eine Remarketing-Liste für Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 5%

---


# Segmente an eine Marketing-Liste für Google-Anzeigen {#send-segments-to-a-google-adwords-remarketing-list} senden

Dieser Vorgang erfordert eine [!DNL Google Ads]-Remarketing-Liste, einen Pixelcode und einen Audience Manager [!DNL URL] [!DNL destination]. Es wird auch als Remarketing-Liste für Suchmaschinenwerbung ([!DNL RLSA])-Integration bezeichnet. Gilt nur für die gebührenpflichtige Suche.

>[!IMPORTANT]
>Bitte beachten Sie, dass es sich hierbei nicht um eine produktive Integration der beiden Systeme handelt.

So richten Sie eine [!DNL Google Ads] Remarketing-Liste als [!DNL Audience Manager] [!DNL URL destination] ein:

1. Erstellen Sie in Ihrem [!DNL Google Ads]-Konto [eine Website-Remarketing-Liste](https://support.google.com/adwords/answer/2454064?hl=en) und notieren Sie Ihre Konversions-ID.
1. Verwenden Sie die folgende URL als Vorlage für die Basis-URL und die sichere URL. Ersetzen Sie den Abschnitt xxxxxx durch Ihre Konversions-ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. In Audience Manager [Erstellen Sie einen  [!DNL URL destination]](../../features/destinations/create-url-destination.md) oder bearbeiten Sie einen vorhandenen [!DNL destination]. Verwenden Sie beim Erstellen von [!DNL destination] die folgenden Einstellungen:
   * Typ: URL
   * Serialisieren: Aktiviert
   * Trennzeichen: Semikolon (;)

1. Fügen Sie im Abschnitt [!UICONTROL Segment Mappings] Ihres [!DNL URL] [!DNL destination] den Code aus Schritt 2 in die Felder [!DNL URL] und [!DNL Secure URL] ein. Präfix für den Code mit `http:` und `https:` in den Feldern [!DNL URL] bzw. [!DNL Secure URL].

   >[!IMPORTANT]
   >
   >Kodierte Ampersands `&` durch nicht kodierte Ampersands `&` ersetzen

   Unsicherer [!DNL URL]-Code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Sicherer [!DNL URL]-Code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Klicken **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Wenn Sie mit mehreren Segmenten arbeiten, erhalten Sie für jedes Segment, das Sie einem [!DNL Google Ads] [!DNL destination] zuordnen möchten, ein neues Pixel. Dadurch wird sichergestellt, dass die Daten auf die entsprechende Remarketing-Liste angewendet werden.

1. Definieren Sie beim Zuordnen eines neuen Segments zu diesem in Audience Manager die Zuordnung als `aam=segmentID` und ersetzen Sie `segmentID` durch die ID Ihres Segments.[!DNL destination]
1. Erstellen Sie beim Definieren eines Behälters in [!DNL Google Ads] eine Regel, die der in Schritt 6 definierten Zuordnung entspricht.

Eine abgeschlossene Zuordnung könnte wie folgt aussehen:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Erstellen Sie eine [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [AdWords Remarketing-Listen](https://support.google.com/adwords/answer/2472738)
>* [Funktionsweise von AdWords Remarketing](https://support.google.com/adwords/answer/2454000)

