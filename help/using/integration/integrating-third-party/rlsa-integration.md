---
description: Dieses Verfahren erfordert eine AdWords-Remarketing-Liste, Pixelcode und ein Audience Manager-URL-Ziel. Es wird auch als Remarketing-Liste für die Integration von Suchanzeigen (RLSA) bezeichnet. Gilt nur für Paid Search.
seo-description: This procedure requires an AdWords remarketing list, pixel code, and an Audience Manager URL destination. It is also known as a remarketing list for search ads (RLSA) integration. Applies to paid search only.
seo-title: Send Segments to a Google AdWords Remarketing List
solution: Audience Manager
title: Senden von Segmenten an eine Remarketing-Liste für Google AdWords
uuid: 5ad821c6-48b4-42c0-b912-1563331e93a2
feature: Third-party Integration
exl-id: 76676eae-de4f-4fee-8774-ee215525306a
source-git-commit: b8d65ef8c27100d174a997eb24a75f37b4e75d40
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 3%

---

# Senden von Segmenten an eine Google Ads-Remarketing-Liste {#send-segments-to-a-google-adwords-remarketing-list}

Dieses Verfahren erfordert [!DNL Google Ads] Remarketing-Liste, Pixelcode und ein Audience Manager [!DNL URL] [!DNL destination]. Sie wird auch als Remarketing-Liste für Suchanzeigen ([!DNL RLSA]). Gilt nur für Paid Search.

>[!IMPORTANT]
>Bitte beachten Sie, dass es sich hierbei nicht um eine produktive Integration der beiden Systeme handelt.

So richten Sie eine [!DNL Google Ads] Remarketing-Liste als [!DNL Audience Manager] [!DNL URL destination]:

1. In [!DNL Google Ads] Konto, [Erstellen einer Website-Remarketing-Liste](https://support.google.com/tagmanager/answer/6106960?hl=en) und schreiben Sie Ihre Konversions-ID auf.
1. Verwenden Sie die folgende URL als Vorlage für die Basis-URL und die sichere URL. Ersetzen Sie den Abschnitt xxxxxxxx durch Ihre Konversions-ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Im Audience Manager [Erstellen Sie eine [!DNL URL destination]](../../features/destinations/create-url-destination.md) oder vorhandene [!DNL destination]. Verwenden Sie beim Erstellen der [!DNL destination]:
   * Typ: URL
   * Serialisieren: Aktiviert
   * Trennzeichen: Semikolon ( &amp;semi; )

1. Im [!UICONTROL Segment Mappings] Abschnitt Ihres [!DNL URL] [!DNL destination], fügen Sie den Code aus Schritt 2 zum [!DNL URL] und [!DNL Secure URL] -Felder. Stellen Sie dem Code das Präfix `http:` und `https:` im [!DNL URL] und [!DNL Secure URL] angegeben.

   >[!IMPORTANT]
   >
   >Kodierte kaufmännische Und-Zeichen ersetzen `&` mit nicht kodierten kaufmännischen Und-Zeichen `&`

   Unsicher [!DNL URL] code:

   ```
    http://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

   Secure [!DNL URL] code:

   ```
    https://googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?
    value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Klicken **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Wenn Sie mit mehreren Segmenten arbeiten, erhalten Sie für jedes Segment, das Sie einer [!DNL Google Ads] [!DNL destination]. Dadurch wird sichergestellt, dass die Daten auf die entsprechende Remarketing-Liste angewendet werden.

1. Beim Zuordnen eines neuen Segments zu diesem [!DNL destination] Definieren Sie die Zuordnung im Audience Manager als `aam=segmentID` und ersetzen `segmentID` mit der Kennung Ihres Segments.
1. Beim Definieren eines Behälters in [!DNL Google Ads]erstellen Sie eine Regel, die mit der in Schritt 6 definierten Zuordnung übereinstimmt.

Eine abgeschlossene Zuordnung könnte in etwa wie folgt aussehen:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Erstellen Sie eine [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Über Remarketing-Listen für AdWords](https://support.google.com/adwords/answer/2472738)
>* [Funktionsweise von AdWords Remarketing](https://support.google.com/adwords/answer/2454000)

