---
description: In diesem Artikel wird beschrieben, wie Sie Twitter Custom Audiences für neue und vorhandene Integrationen konfigurieren.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Konfigurieren von Twitter benutzerspezifischen Zielgruppen als gerätebasiertes Selbstbedienungsziel
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Konfigurieren von [!DNL Twitter Custom Audiences] als gerätebasiertes Selbstbedienungsziel {#configure-twitter}

In diesem Artikel wird beschrieben, wie Sie eine Integration mit [Twitter benutzerspezifischen Zielgruppen](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html) konfigurieren.

## Voraussetzungen {#prerequisites}

Bevor Sie Ihr [!DNL Twitter Custom Audiences]-Ziel konfigurieren, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen.

* Ihr [!DNL Twitter Ads]-Konto muss für Werbung berechtigt sein. Neue [!DNL Twitter Ads] -Konten sind in den ersten 2 Wochen nach ihrer Erstellung nicht für Werbung geeignet.
* Für Ihr [!DNL Twitter] -Benutzerkonto, für das Sie den Zugriff in Audience Manager genehmigt haben, muss die Berechtigung [Partner audience manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) aktiviert sein.
* Wenden Sie sich beim Erstellen des ersten [!DNL Twitter Custom Audiences] -Ziels in Ihrer Audience Manager-Instanz an die Adobe Consulting- oder Kundenunterstützung, um die [!DNL Twitter] ID-Synchronisierung (Data Source ID = 1123) für Ihr Konto zu aktivieren. Dies ist für die korrekte Synchronisierung zwischen Audience Manager und [!DNL Twitter] erforderlich.

## Neues [!DNL Twitter Custom Audiences] Ziel hinzufügen {#add-new-twitter-destination}

In diesem Abschnitt werden die Schritte beschrieben, die Sie beim Konfigurieren eines neuen gerätebasierten Ziels für [!DNL Twitter Custom Audiences] ausführen müssen. In diesem Szenario wird davon ausgegangen, dass Sie kein vorhandenes [!DNL Twitter Custom Audiences] -Ziel über Ihren Adobe-Berater oder die Kundenunterstützung konfiguriert haben.

### Schritt 1. Authentifizieren mit [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Bevor Sie das gerätebasierte Ziel hinzufügen können, müssen Sie Audience Manager und Ihr [!DNL Twitter Custom Audiences] -Konto verknüpfen. Gehen Sie dazu folgendermaßen vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!DNL Administration > Integrated Accounts]**. Wenn Sie bereits eine Integration mit einer Zielplattform konfiguriert haben, sollte diese auf dieser Seite aufgeführt sein. Andernfalls ist die Seite leer.
1. Klicken Sie auf **[!DNL Add Account]**.
1. Wählen Sie [!DNL Twitter Custom Audiences] und klicken Sie auf **[!DNL Confirm]** , um zur Authentifizierungsseite umgeleitet zu werden.

   ![integrated-platforms](assets/dbd-integrated-platforms.png)

1. Nachdem Sie sich authentifiziert haben, werden Sie zu dem Audience Manager weitergeleitet, in dem Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das Advertiser-Konto aus, das Sie verwenden möchten, und klicken Sie auf **[!DNL Confirm]**.

### Schritt 2: Neues gerätebasiertes Ziel erstellen {#step2-create-new-destination}

Nachdem Sie den Audience Manager und Ihre [!DNL Twitter Custom Audiences] verknüpft haben, können Sie das neue Ziel erstellen. Gehen Sie dazu folgendermaßen vor:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen bei der korrekten Identifizierung des Ziels hilft.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!DNL Audience Data > Destinations]** und klicken Sie auf **[!DNL Create Destination]**.
1. Geben Sie im Abschnitt **[!DNL Basic Information]** einen **[!DNL Name]** und einen **[!DNL Description]** für Ihr neues Ziel ein und verwenden Sie die folgenden Einstellungen: ![setup](assets/dbd-new-basic.png)
1. Klicken Sie auf **[!DNL Next]**.
1. Wählen Sie die [Datenexportbeschriftungen](/help/using/features/data-export-controls.md#controls-labels) aus, die Sie für dieses Ziel festlegen möchten.
1. Klicken Sie auf **[!DNL Save]**.
1. Wählen Sie im Abschnitt **[!DNL Segment Mappings]** die Zielgruppensegmente aus, die Sie an dieses Ziel senden möchten.
1. Speichern Sie das Ziel.

## Überlegungen zur Segmentzuordnung {#segment-mapping-considerations}

Stellen Sie beim Zuordnen von Zielgruppensegmenten zu [!UICONTROL Twitter] sicher, dass Sie die folgenden Segmentbenennungsanforderungen erfüllen:

* Stellen Sie für Menschen lesbare Namen für die Segmentzuordnung bereit. Es wird empfohlen, denselben Namen zu verwenden, den Sie für die Audience Manager-Segmente verwendet haben.
* Verwenden Sie keine Sonderzeichen (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) in Segmentzuordnungsnamen und Segmentzuordnungsnamen. Wenn der Segmentname Ihres Audience Managers diese Zeichen enthält, entfernen Sie diese, bevor Sie das Segment einem [!UICONTROL Twitter] -Ziel zuordnen.

### Beispiel

* Richtiger Segment- oder Zuordnungsname: &quot;US- und europäische Käufer&quot;;
* Falscher Segment- oder Zuordnungsname: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Sie können die Namen von bereits zugeordneten Segmenten nicht ändern. Audience Manager verwendet die Segmentnamen, um die Segmente in der Integration korrekt zu identifizieren.

## Überlegungen zu Übereinstimmungsraten {#match-rates-considerations}

* Die Integration zwischen Audience Manager und [!UICONTROL Twitter Custom Audiences] unterstützt historische Zielgruppen-Backups. Alle Segmentqualifikationen werden beim Erstellen des Ziels an [!UICONTROL Twitter] gesendet.

## Fehlerbehebung {#troubleshooting}

Beim Konfigurieren oder Senden von Daten an das Twitter Custom Audiences-Ziel treten möglicherweise die unten beschriebenen Fehler auf. In diesem Abschnitt wird erläutert, was zu Fehlern führen kann und wie diese behoben werden können.

| Fehlermeldung | Vorfall/Grund | Auflösung |
|---|---|---|
| `Internal server error` | Diese Fehlermeldung wird in der Audience Manager-Benutzeroberfläche angezeigt, wenn versucht wird, ein neues [!DNL Twitter] -Konto mit einer veralteten Version der Twitter-API hinzuzufügen. | Wenden Sie sich an die Adobe-Kundenunterstützung. |
| `Twitter Error: This request is not properly authenticated` | Diese Fehlermeldung wird in der Audience Manager-Benutzeroberfläche angezeigt, wenn versucht wird, Segmente mit nicht unterstützten Segmentnamen dem Ziel zuzuordnen. | Überprüfen Sie die zugeordneten Segmentnamen und stellen Sie sicher, dass sie keine nicht unterstützten Zeichen enthalten. Eine Liste der nicht unterstützten Zeichen finden Sie unter [Überlegungen zur Segmentzuordnung](#segment-mapping-considerations) . |
| `Twitter Error: Account XXXXXXXXX was not found` | Diese Fehlermeldung wird in der Audience Manager-Benutzeroberfläche angezeigt, wenn die für das Ziel konfigurierten Anmeldeinformationen nicht für den Zugriff auf das entsprechende Twitter Ads-Konto autorisiert sind. | <ul><li>Stellen Sie sicher, dass die von Ihnen verwendeten Kontoanmeldeinformationen die [Voraussetzungen](#prerequisites) erfüllen.</li><li>Navigieren Sie mit denselben Anmeldedaten zur Twitter Ads-Benutzeroberfläche und prüfen Sie, ob die richtigen Zielgruppen unter dem entsprechenden `XXXXXXXXX` -Konto angezeigt werden. </li></ul> |