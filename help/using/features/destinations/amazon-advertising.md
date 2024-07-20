---
description: In diesem Artikel wird beschrieben, wie Sie Amazon Advertising für sowohl neue als auch vorhandene Integrationen konfigurieren.
solution: Audience Manager
title: Amazon Advertising als gerätebasiertes Selbstbedienungsziel konfigurieren
exl-id: 049af52a-b425-493d-9e77-9ced7ba6d168
source-git-commit: bac3167927af0957e7081e1ea653464101affcb8
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 0%

---

# Konfigurieren von [!DNL Amazon Advertising] als gerätebasiertes Selbstbedienungsziel {#configure-amazon}

In diesem Artikel wird beschrieben, wie Sie eine Integration mit [Amazon Advertising](https://advertising.amazon.com/API/docs/en-us) konfigurieren.

## Voraussetzungen {#prerequisites}

Bevor Sie Ihr [!DNL Amazon Advertising]-Ziel konfigurieren, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen.

* Ihr [!DNL Amazon]-Konto muss für Werbung berechtigt sein.
* Wenden Sie sich beim Erstellen des ersten [!DNL Amazon Advertising] -Ziels in Ihrer Audience Manager-Instanz an die Adobe Consulting- oder Kundenunterstützung, um die [!DNL Amazon] ID-Synchronisierung (Data Source ID = 139200) für Ihr Konto zu aktivieren. Dies ist für die korrekte Synchronisierung zwischen Audience Manager und [!DNL Amazon] erforderlich.
* Nachdem die neuen Datenanbieter-Zielgruppen erstellt wurden, sollten Sie [ihre Metadaten aktualisieren](https://advertising.amazon.com/API/docs/en-us/data-provider/openapi#tag/Metadata/paths/~1v2~1dp~1audiencemetadata~1%7BaudienceId%7D/put) und die **[!DNL audience fees]** hinzufügen. Für diesen Vorgang können Sie die [Amazon Ads API](https://advertising.amazon.com/API/docs/en-us/guides/onboarding/apply-for-access) oder die [Amazon Advertising UI](https://advertising.amazon.com/) verwenden.

## Neues [!DNL Amazon Advertising] Ziel hinzufügen {#add-new-amazon-destination}

In diesem Abschnitt werden die Schritte beschrieben, die Sie beim Konfigurieren eines neuen gerätebasierten Ziels für [!DNL Amazon Advertising] ausführen müssen. In diesem Szenario wird davon ausgegangen, dass Sie kein vorhandenes [!DNL Amazon Advertising] -Ziel über Ihren Adobe-Berater oder die Kundenunterstützung konfiguriert haben.

### Schritt 1. Authentifizieren mit [!DNL Amazon Advertising] {#step1-authenticate-with-amazon}

Bevor Sie das gerätebasierte Ziel hinzufügen können, müssen Sie Audience Manager und Ihr [!DNL Amazon Advertising] -Konto verknüpfen. Gehen Sie dazu folgendermaßen vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration > Integrated Accounts]**. Wenn Sie bereits eine Integration mit einer Zielplattform konfiguriert haben, sollte diese auf dieser Seite aufgeführt sein. Andernfalls ist die Seite leer.
1. Wählen Sie **[!UICONTROL Add Account]** aus.
1. Wählen Sie [!UICONTROL Amazon Data Provider] aus.

   ![integrated-platforms](assets/dbd-amazon-without-options.png)

1. Wählen Sie je nach Region, in der Ihr [!DNL Amazon Ads]-Konto erstellt wird (Nordamerika, Europa oder Ferer Osten) eine der **[!UICONTROL Amazon Data Provider]**-Optionen aus und klicken Sie auf **[!DNL Confirm]** , um zur Authentifizierungsseite umgeleitet zu werden.

   ![integrated-platforms](assets/dbd-amazon-with-options.png)

1. Nachdem Sie sich authentifiziert haben, werden Sie zu dem Audience Manager weitergeleitet, in dem Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das Advertiser-Konto aus, das Sie verwenden möchten, und klicken Sie auf **[!UICONTROL Confirm]**. Auf diese Weise haben Sie den Zugriff für Audience Manager genehmigt, um Updates für Ihre Zielgruppen zu senden.

### Schritt 2: Neues gerätebasiertes Ziel erstellen {#step2-create-new-destination}

Nachdem Sie den Audience Manager und Ihr [!DNL Amazon Advertising] -Konto verknüpft haben, können Sie das neue Ziel erstellen. Gehen Sie dazu folgendermaßen vor:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen bei der korrekten Identifizierung des Ziels hilft.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!UICONTROL Audience Data > Destinations]** und wählen Sie **[!UICONTROL Create Destination]** aus.
1. Geben Sie im Abschnitt **[!UICONTROL Basic Information]** einen **[!UICONTROL Name]** und einen **[!UICONTROL Description]** für Ihr neues Ziel ein und verwenden Sie die folgenden Einstellungen:

   ![setup](assets/dbd-new-account-amazon.png)

1. Wählen Sie **[!UICONTROL Next]** aus.
1. Wählen Sie die [Datenexportbeschriftungen](/help/using/features/data-export-controls.md#controls-labels) aus, die Sie für dieses Ziel festlegen möchten.
1. Wählen Sie **[!UICONTROL Save]** aus.
1. Wählen Sie im Abschnitt **[!UICONTROL Segment Mappings]** die Zielgruppensegmente aus, die Sie an dieses Ziel senden möchten.
1. Speichern Sie das Ziel.

## Überlegungen zu Übereinstimmungsraten {#match-rates-considerations}

Die Integration zwischen Audience Manager und [!DNL Amazon Advertising] unterstützt historische Zielgruppen-Backups. Alle Segmentqualifikationen werden beim Erstellen des Ziels an [!DNL Amazon] gesendet.

## Fehlerbehebung {#troubleshooting}

Beim Konfigurieren oder Senden von Daten an das [!DNL Amazon Advertising]-Ziel treten möglicherweise die unten beschriebenen Fehler auf. In diesem Abschnitt wird erläutert, was zu Fehlern führen kann und wie diese behoben werden können.

| Fehlermeldung | Vorfall/Grund | Auflösung |
|---|---|---|
| `Internal server error` | Diese Fehlermeldung wird in der Audience Manager-Benutzeroberfläche angezeigt, wenn versucht wird, ein neues [!DNL Amazon] -Konto mit einer veralteten Version der Amazon-API hinzuzufügen. | Wenden Sie sich an die Adobe-Kundenunterstützung. |
| `Amazon Error: Account XXXXXXXXX was not found` | Diese Fehlermeldung wird in der Audience Manager-Benutzeroberfläche angezeigt, wenn die für das Ziel konfigurierten Anmeldeinformationen nicht für den Zugriff auf das entsprechende Amazon Ads-Konto autorisiert sind. | <ul><li>Stellen Sie sicher, dass die von Ihnen verwendeten Kontoanmeldeinformationen die [Voraussetzungen](#prerequisites) erfüllen.</li><li>Navigieren Sie mit denselben Anmeldedaten zur Amazon Ads-Benutzeroberfläche und prüfen Sie, ob die richtigen Zielgruppen unter dem entsprechenden Konto angezeigt werden. </li></ul> |
