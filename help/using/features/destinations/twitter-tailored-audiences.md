---
description: In diesem Artikel wird beschrieben, wie Sie benutzerdefinierte Twitter-Zielgruppen für neue und vorhandene Integrationen konfigurieren.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Benutzerdefinierte Twitter-Zielgruppen als gerätebasiertes Selbstbedienungsziel konfigurieren
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 8023bfe1e4ea415867e1233f143627ff179cce42
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 1%

---

# [!DNL Twitter Custom Audiences] als gerätebasiertes Selbstbedienungsziel konfigurieren {#configure-twitter}

In diesem Artikel wird beschrieben, wie Sie eine Integration mit [Twitter Custom Audiences](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html) konfigurieren.

## Voraussetzungen {#prerequisites}

Bevor Sie Ihr [!DNL Twitter Custom Audiences]-Ziel konfigurieren, überprüfen Sie die folgenden Twitter-Voraussetzungen, die Sie erfüllen müssen.

1. Ihr [!DNL Twitter Ads]-Konto muss für Werbung berechtigt sein. Neue [!DNL Twitter Ads]-Konten sind in den ersten 2 Wochen nach ihrer Erstellung nicht für Werbung geeignet.
2. Für Ihr [!DNL Twitter]-Benutzerkonto, für das Sie den Zugriff in Audience Manager genehmigt haben, muss die Berechtigung [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) aktiviert sein.
3. Wenden Sie sich beim Erstellen des ersten [!DNL Twitter Custom Audiences]-Ziels in Ihrer Audience Manager-Instanz an Adobe Consulting oder die Kundenunterstützung, um die [!DNL Twitter] ID-Synchronisierung (Datenquellen-ID = 1123) für Ihr  zu aktivieren. Dies ist für die korrekte Synchronisierung zwischen Audience Manager und [!DNL Twitter] erforderlich.

## Neues [!DNL Twitter Custom Audiences]-Ziel hinzufügen {#add-new-twitter-destination}

In diesem Abschnitt werden die Schritte beschrieben, die Sie beim Konfigurieren eines neuen gerätebasierten Ziels für [!DNL Twitter Custom Audiences] ausführen müssen. In diesem Szenario wird davon ausgegangen, dass Sie über Ihren Adobe-Berater oder die Kundenunterstützung kein vorhandenes [!DNL Twitter Custom Audiences]-Ziel konfiguriert haben.

### Schritt 1. Authentifizieren Sie sich mit [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Bevor Sie das gerätebasierte Ziel hinzufügen können, müssen Sie den Audience Manager und Ihr [!DNL Twitter Custom Audiences]-Konto verknüpfen. Gehen Sie wie folgt vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!DNL Administration > Integrated Accounts]**. Wenn Sie bereits eine Integration mit einer Zielplattform konfiguriert haben, sollte diese auf dieser Seite aufgeführt sein. Andernfalls ist die Seite leer.
1. Klicken **[!DNL Add Account]**.
1. Wählen Sie [!DNL Twitter Custom Audiences] und klicken Sie auf **[!DNL Confirm]** , um zur Authentifizierungsseite weitergeleitet zu werden.

   ![integrierte Plattformen](assets/dbd-integrated-platforms.png)

1. Nachdem Sie sich authentifiziert haben, werden Sie zu dem Audience Manager weitergeleitet, in dem Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das Advertiser-Konto aus, das Sie verwenden möchten, und klicken Sie auf **[!DNL Confirm]**.

### Schritt 2: Neues gerätebasiertes Ziel erstellen {#step2-create-new-destination}

Nachdem Sie Audience Manager und [!DNL Twitter Custom Audiences] verknüpft haben, können Sie das neue Ziel erstellen. Gehen Sie wie folgt vor:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen bei der korrekten Identifizierung des Ziels hilft.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, navigieren Sie zu **[!DNL Audience Data > Destinations]** und klicken Sie auf **[!DNL Create Destination]**.
1. Geben Sie im Abschnitt **[!DNL Basic Information]** einen **[!DNL Name]** und **[!DNL Description]** für Ihr neues Ziel ein und verwenden Sie die folgenden Einstellungen: ![setup](assets/dbd-new-basic.png)
1. Klicken **[!DNL Next]**.
1. Wählen Sie die [Datenexportbeschriftungen](/help/using/features/data-export-controls.md#controls-labels) aus, die Sie für dieses Ziel festlegen möchten.
1. Klicken **[!DNL Save]**.
1. Wählen Sie im Abschnitt **[!DNL Segment Mappings]** die Zielgruppensegmente aus, die Sie an dieses Ziel senden möchten.
1. Speichern Sie das Ziel.

## Überlegungen zur Segmentzuordnung {#segment-mapping-considerations}

Stellen Sie beim Zuordnen von Zielgruppensegmenten zu [!UICONTROL Twitter] sicher, dass Sie die folgenden Segmentbenennungsanforderungen erfüllen:

* Stellen Sie für Menschen lesbare Namen für die Segmentzuordnung bereit. Es wird empfohlen, denselben Namen zu verwenden, den Sie für die Audience Manager-Segmente verwendet haben.
* Verwenden Sie keine Sonderzeichen (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) in Segmentzuordnungsnamen und Segmentzuordnungsnamen. Wenn der Segmentname Ihres Audience Managers diese Zeichen enthält, entfernen Sie diese, bevor Sie das Segment einem [!UICONTROL Twitter]-Ziel zuordnen.

### Beispiel

* Richtiger Segment- oder Zuordnungsname: &quot;US- und europäische Käufer&quot;;
* Falscher Segment- oder Zuordnungsname: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Sie können die Namen von bereits zugeordneten Segmenten nicht ändern. Audience Manager verwendet die Segmentnamen, um die Segmente in der Integration korrekt zu identifizieren.

## Überlegungen zu Übereinstimmungsraten {#match-rates-considerations}

* Die Integration zwischen Audience Manager und [!UICONTROL Twitter Custom Audiences] unterstützt historische Zielgruppen-Backups. Alle Segmentqualifikationen werden beim Erstellen des Ziels an [!UICONTROL Twitter] gesendet.
