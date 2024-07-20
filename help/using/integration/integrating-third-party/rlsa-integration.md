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
source-wordcount: '284'
ht-degree: 0%

---

# Senden von Segmenten an eine Google Ads-Remarketing-Liste {#send-segments-to-a-google-adwords-remarketing-list}

Dieser Vorgang erfordert eine [!DNL Google Ads] Remarketing-Liste, Pixelcode und einen Audience Manager [!DNL URL] [!DNL destination]. Es wird auch als Remarketing-Liste für die Integration von Suchanzeigen ([!DNL RLSA]) bezeichnet. Gilt nur für Paid Search.

>[!IMPORTANT]
>Bitte beachten Sie, dass es sich hierbei nicht um eine produktive Integration der beiden Systeme handelt.

So richten Sie eine [!DNL Google Ads] Remarketing-Liste als [!DNL Audience Manager] [!DNL URL destination] ein:

1. Erstellen Sie in Ihrem [!DNL Google Ads] -Konto eine Website-Remarketing-Liste](https://support.google.com/tagmanager/answer/6106960?hl=en) und schreiben Sie Ihre Konversions-ID auf.[
1. Verwenden Sie die folgende URL als Vorlage für die Basis-URL und die sichere URL. Ersetzen Sie den Abschnitt xxxxxxxx durch Ihre Konversions-ID.

   ```
    //googleads.g.doubleclick.net/pagead/viewthroughconversion/xxxxxxxx/?value=0&guid=ON&script=0&data=%ALIAS%
   ```

1. Im Audience Manager [Erstellen Sie einen  [!DNL URL destination]](../../features/destinations/create-url-destination.md) oder bearbeiten Sie einen vorhandenen [!DNL destination]. Verwenden Sie beim Erstellen von [!DNL destination] die folgenden Einstellungen:
   * Typ: URL
   * Serialisieren: Aktiviert
   * Trennzeichen: Semikolon ( &amp;semi; )

1. Fügen Sie im Abschnitt [!UICONTROL Segment Mappings] Ihres [!DNL URL] [!DNL destination] den Code aus Schritt 2 den Feldern [!DNL URL] und [!DNL Secure URL] hinzu. Setzen Sie in den Feldern [!DNL URL] bzw. [!DNL Secure URL] dem Code den Wert `http:` und `https:` voran.

   >[!IMPORTANT]
   >
   >Kodierte Und-Zeichen `&` durch nicht-kodierte Und-Zeichen `&` ersetzen

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

1. Klicken Sie auf **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Wenn Sie mit mehreren Segmenten arbeiten, erhalten Sie für jedes Segment, das Sie einer [!DNL Google Ads] [!DNL destination] zuordnen möchten, ein neues Pixel. Dadurch wird sichergestellt, dass die Daten auf die entsprechende Remarketing-Liste angewendet werden.

1. Definieren Sie beim Zuordnen eines neuen Segments zu dieser [!DNL destination] im Audience Manager die Zuordnung als `aam=segmentID` und ersetzen Sie `segmentID` durch die Kennung Ihres Segments.
1. Wenn Sie einen Behälter in [!DNL Google Ads] definieren, erstellen Sie eine Regel, die mit der in Schritt 6 definierten Zuordnung übereinstimmt.

Eine abgeschlossene Zuordnung könnte in etwa wie folgt aussehen:

![](../assets/rlsa_mapping.png)

>[!MORELIKETHIS]
>
>* [[!DNL Destinations]](../../features/destinations/destinations.md)
>* [Erstellen eines  [!DNL URL Destination]](../../features/destinations/create-url-destination.md)
>* [Über Remarketing-Listen für AdWords](https://support.google.com/adwords/answer/2472738)
>* [Funktionsweise des Remarketing von AdWords](https://support.google.com/adwords/answer/2454000)
