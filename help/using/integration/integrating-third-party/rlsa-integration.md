---
description: Dieses Verfahren erfordert eine AdWords-Remarketing-Liste, einen Pixelcode und ein Audience Manager-URL-Ziel. Sie wird auch als Remarketing-Liste für die RLSA-Integration (Search Ads) bezeichnet. Gilt nur für bezahlte Suche.
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: Segmente an eine Remarketing-Liste für Google AdWords senden
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: b8d65ef8c27100d174a997eb24a75f37b4e75d40
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Segmente an eine Remarketing-Liste für Google Ads senden {#send-segments-to-a-google-adwords-remarketing-list}

Für dieses Verfahren sind eine [!DNL Google Ads] Remarketing-Liste, ein Pixelcode und ein Audience Manager [!DNL URL] [!DNL destination] erforderlich. Sie wird auch als Remarketing-Liste für die Integration von Suchanzeigen ([!DNL RLSA]) bezeichnet. Gilt nur für bezahlte Suche.

>[!IMPORTANT]
>Bitte beachten Sie, dass es sich hierbei nicht um eine produktbezogene Integration der beiden Systeme handelt.

So richten Sie eine [!DNL Google Ads] Remarketing-Liste als [!DNL Audience Manager] [!DNL URL destination] ein:

1. Erstellen Sie in Ihrem [!DNL Google Ads]-Konto [eine Website-Remarketing-Liste](https://support.google.com/tagmanager/answer/6106960?hl=en) und notieren Sie sich Ihre Konversions-ID.
1. Verwenden Sie die folgende URL als Vorlage für die Basis-URL und die sichere URL. Ersetzen Sie den Abschnitt xxxxxxxx durch Ihre Konversions-ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Erstellen Sie [ Audience Manager eine  [!DNL URL destination]](../../features/destinations/create-url-destination.md) oder bearbeiten Sie eine bestehende [!DNL destination]. Verwenden Sie beim Erstellen der [!DNL destination] die folgenden Einstellungen:
   * Typ: URL
   * Serialisieren: Aktiviert
   * Trennzeichen: Semikolon ( &amp;semi; )

1. Fügen Sie im [!UICONTROL Segment Mappings] Abschnitt Ihrer [!DNL URL]-[!DNL destination] den Code aus Schritt 2 zu den Feldern [!DNL URL] und [!DNL Secure URL] hinzu. Stellen Sie dem Code `http:` und `https:` in den Feldern [!DNL URL] bzw. [!DNL Secure URL] voran.

   >[!IMPORTANT]
   >
   >Ersetzen von kodierten kaufmännischen Und-Zeichen `&` durch nicht kodierte kaufmännische Und-Zeichen `&`

   Nicht sicherer [!DNL URL]:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Sicherer [!DNL URL]:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Klicken Sie auf **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Wenn Sie mit mehreren Segmenten arbeiten, rufen Sie für jedes Segment, das Sie einem [!DNL Google Ads] [!DNL destination] zuordnen möchten, ein neues Pixel ab. Dadurch wird sichergestellt, dass die Daten auf die entsprechende Remarketing-Liste angewendet werden.

1. Definieren Sie beim Zuordnen eines neuen Segments zu diesem [!DNL destination] im Audience Manager die Zuordnung als `aam=segmentID` und ersetzen Sie `segmentID` durch die ID Ihres Segments.
1. Erstellen Sie beim Definieren eines Buckets in [!DNL Google Ads] eine Regel, die der in Schritt 6 definierten Zuordnung entspricht.

Eine abgeschlossene Zuordnung könnte in etwa wie folgt aussehen:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Erstellen eines [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Über AdWords-Remarketing-Listen](https://support.google.com/adwords/answer/2472738)
>* [Funktionsweise von AdWords-Remarketing](https://support.google.com/adwords/answer/2454000)
