---
description: In diesem Artikel wird beschrieben, wie Sie Amazon Advertising für neue und vorhandene Integrationen konfigurieren.
solution: Audience Manager
title: Amazon Advertising als gerätebasiertes Selbstbedienungsziel konfigurieren
source-git-commit: 01f3c2d813a91b8541bd8ba8a8b030f67a4f979e
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 0%

---


# Konfigurieren [!DNL Amazon Advertising] als gerätebasiertes Selbstbedienungsziel {#configure-amazon}

In diesem Artikel wird beschrieben, wie Sie eine Integration mit [Amazon-Werbung](https://advertising.amazon.com/API/docs/en-us).

## Voraussetzungen {#prerequisites}

Vor der Konfiguration [!DNL Amazon Advertising] Ziel festzulegen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen.

* Ihre [!DNL Amazon] müssen für Werbung zugelassen sein.
* Beim Erstellen der ersten [!DNL Amazon Advertising] Ziel in Ihrer Audience Manager-Instanz kontaktieren Sie bitte Adobe Consulting oder die Kundenunterstützung, um die [!DNL Amazon] ID-Synchronisierung (Datenquellen-ID = 139200) für Ihr Konto. Dies ist für die korrekte Synchronisierung zwischen Audience Manager und erforderlich. [!DNL Amazon].
* Nachdem die neuen Datenanbieter-Zielgruppen erstellt wurden, sollten Sie [Metadaten aktualisieren](https://advertising.amazon.com/API/docs/en-us/data-provider/openapi#tag/Metadata/paths/~1v2~1dp~1audiencemetadata~1%7BaudienceId%7D/put) und fügen Sie **[!DNL audience fees]**. Für diesen Vorgang können Sie die Variable [Amazon Ads API](https://advertising.amazon.com/API/docs/en-us/guides/onboarding/apply-for-access) oder [Amazon Advertising-Benutzeroberfläche](https://advertising.amazon.com/).

## Neu hinzufügen [!DNL Amazon Advertising] Ziel {#add-new-amazon-destination}

In diesem Abschnitt werden die Schritte beschrieben, die Sie beim Konfigurieren eines neuen gerätebasierten Ziels für [!DNL Amazon Advertising]. In diesem Szenario wird davon ausgegangen, dass Sie nicht über vorhandene [!DNL Amazon Advertising] Ziel, das über Ihren Adobe-Berater oder die Kundenunterstützung konfiguriert wurde.

### Schritt 1. Authentifizieren mit [!DNL Amazon Advertising] {#step1-authenticate-with-amazon}

Bevor Sie das gerätebasierte Ziel hinzufügen können, müssen Sie Audience Manager und Ihre [!DNL Amazon Advertising] -Konto. Gehen Sie dazu folgendermaßen vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und navigieren Sie zu **[!UICONTROL Administration > Integrated Accounts]**. Wenn Sie bereits eine Integration mit einer Zielplattform konfiguriert haben, sollte diese auf dieser Seite aufgeführt sein. Andernfalls ist die Seite leer.
1. Auswählen **[!UICONTROL Add Account]**.
1. Auswählen [!UICONTROL Amazon Data Provider].

   ![integrierte Plattformen](assets/dbd-amazon-without-options.png)

1. Wählen Sie eine der **[!UICONTROL Amazon Data Provider]** Optionen abhängig von der Region, in der Ihre [!DNL Amazon Ads] -Konto erstellt wird (Nordamerika, Europa oder Ferer Osten) und klicken Sie auf **[!DNL Confirm]** auf die Authentifizierungsseite umgeleitet werden.

   ![integrierte Plattformen](assets/dbd-amazon-with-options.png)

1. Nachdem Sie sich authentifiziert haben, werden Sie zu dem Audience Manager weitergeleitet, in dem Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das Advertiser-Konto aus, das Sie verwenden möchten, und klicken Sie auf **[!UICONTROL Confirm]**. Auf diese Weise haben Sie den Zugriff für Audience Manager genehmigt, um Updates für Ihre Zielgruppen zu senden.

### Schritt 2: Neues gerätebasiertes Ziel erstellen {#step2-create-new-destination}

Nach der Verknüpfung von Audience Manager und [!DNL Amazon Advertising] -Konto können Sie das neue Ziel erstellen. Gehen Sie dazu folgendermaßen vor:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen bei der korrekten Identifizierung des Ziels hilft.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, navigieren Sie zu **[!UICONTROL Audience Data > Destinations]** und wählen Sie **[!UICONTROL Create Destination]**.
1. Im **[!UICONTROL Basic Information]** eingeben. **[!UICONTROL Name]** und **[!UICONTROL Description]** und verwenden Sie die folgenden Einstellungen:

   ![Setup](assets/dbd-new-account-amazon.png)

1. Auswählen **[!UICONTROL Next]**.
1. Wählen Sie die [Datenexportbeschriftungen](/help/using/features/data-export-controls.md#controls-labels) die Sie für dieses Ziel festlegen möchten.
1. Auswählen **[!UICONTROL Save]**.
1. Im **[!UICONTROL Segment Mappings]** Wählen Sie die Zielgruppensegmente aus, die Sie an dieses Ziel senden möchten.
1. Speichern Sie das Ziel.

## Überlegungen zu Übereinstimmungsraten {#match-rates-considerations}

Die Integration zwischen Audience Manager und [!DNL Amazon Advertising] unterstützt historische Zielgruppen-Backups. Alle Segmentqualifikationen werden an gesendet. [!DNL Amazon] wenn Sie das Ziel erstellen.

## Fehlerbehebung {#troubleshooting}

Beim Konfigurieren oder Senden von Daten an [!DNL Amazon Advertising] Ziel, können Sie auf die unten beschriebenen Fehler stoßen. In diesem Abschnitt wird erläutert, was zu Fehlern führen kann und wie diese behoben werden können.

| Fehlermeldung | Vorfall/Grund | Auflösung |
|---|---|---|
| `Internal server error` | Diese Fehlermeldung wird in der Audience Manager-Benutzeroberfläche angezeigt, wenn versucht wird, eine neue [!DNL Amazon] -Konto mit einer veralteten Version der Amazon-API verwenden. | Wenden Sie sich an die Adobe-Kundenunterstützung. |
| `Amazon Error: Account XXXXXXXXX was not found` | Diese Fehlermeldung wird in der Audience Manager-Benutzeroberfläche angezeigt, wenn die für das Ziel konfigurierten Anmeldeinformationen nicht für den Zugriff auf das entsprechende Amazon Ads-Konto autorisiert sind. | <ul><li>Stellen Sie sicher, dass die von Ihnen verwendeten Kontoanmeldeinformationen den [Voraussetzungen](#prerequisites).</li><li>Navigieren Sie mit denselben Anmeldedaten zur Amazon Ads-Benutzeroberfläche und prüfen Sie, ob die richtigen Zielgruppen unter dem entsprechenden Konto angezeigt werden. </li></ul> |
