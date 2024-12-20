---
description: In diesem Artikel wird erläutert, wie Sie benutzerdefinierte Twitter-Zielgruppen für neue und vorhandene Integrationen konfigurieren.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Konfigurieren von benutzerdefinierten Twitter-Zielgruppen als gerätebasiertes Self-Service-Ziel
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Konfigurieren von [!DNL Twitter Custom Audiences] als gerätebasiertes Self-Service-Ziel {#configure-twitter}

In diesem Artikel wird erläutert, wie Sie eine Integration mit [benutzerdefinierten Twitter-Zielgruppen konfigurieren](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Voraussetzungen {#prerequisites}

Bevor Sie Ihr [!DNL Twitter Custom Audiences]-Ziel konfigurieren, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen.

* Ihr [!DNL Twitter Ads] muss für die Werbung infrage kommen. Neue [!DNL Twitter Ads]-Konten sind in den ersten zwei Wochen nach ihrer Erstellung nicht für die Werbung geeignet.
* Für Ihr [!DNL Twitter]-Benutzerkonto, auf das Sie im Audience Manager Zugriff haben, muss die Berechtigung [Partner Audience Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) aktiviert sein.
* Wenden Sie sich beim Erstellen des ersten [!DNL Twitter Custom Audiences]-Ziels in Ihrer Audience Manager-Instanz an die Adobe Consulting- oder Kundenunterstützung, um die [!DNL Twitter]-ID-Synchronisierung (Data Source ID = 1123) für Ihr Konto zu aktivieren. Dies ist für die korrekte Synchronisierung zwischen Audience Manager und [!DNL Twitter] erforderlich.

## Ein neues [!DNL Twitter Custom Audiences] hinzufügen {#add-new-twitter-destination}

In diesem Abschnitt werden die Schritte beschrieben, die Sie beim Konfigurieren eines neuen gerätebasierten Ziels für [!DNL Twitter Custom Audiences] ausführen müssen. Bei diesem Szenario wird davon ausgegangen, dass Sie kein vorhandenes [!DNL Twitter Custom Audiences] über Ihren Adobe-Berater oder die Kundenunterstützung konfiguriert haben.

### Schritt 1. Mit [!DNL Twitter Custom Audiences] authentifizieren {#step1-authenticate-with-twitter}

Bevor Sie das gerätebasierte Ziel hinzufügen können, müssen Sie den Audience Manager und Ihr [!DNL Twitter Custom Audiences]-Konto verknüpfen. Gehen Sie wie folgt vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!DNL Administration > Integrated Accounts]**. Wenn Sie über eine zuvor konfigurierte Integration mit einer Zielplattform verfügen, sollte diese auf dieser Seite aufgeführt sein. Andernfalls ist die Seite leer.
1. Klicken Sie auf **[!DNL Add Account]**.
1. Wählen Sie [!DNL Twitter Custom Audiences] aus und klicken Sie auf **[!DNL Confirm]** , um zur Authentifizierungsseite weitergeleitet zu werden.

   ![integrierte Plattformen](assets/dbd-integrated-platforms.png)

1. Sobald Sie sich authentifiziert haben, werden Sie zum Audience Manager weitergeleitet, in dem Sie Ihre zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das zu verwendende Advertiser-Konto aus und klicken Sie auf **[!DNL Confirm]**.

### Schritt 2: Erstellen eines neuen gerätebasierten Ziels {#step2-create-new-destination}

Nachdem Sie Audience Manager und Ihre [!DNL Twitter Custom Audiences] verknüpft haben, können Sie das neue Ziel erstellen. Gehen Sie wie folgt vor:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen hilft, das Ziel korrekt zu identifizieren.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!DNL Audience Data > Destinations]** und klicken Sie auf **[!DNL Create Destination]**.
1. Geben Sie im Abschnitt **[!DNL Basic Information]** einen **[!DNL Name]** und einen **[!DNL Description]** für Ihr neues Ziel ein und verwenden Sie die folgenden Einstellungen: ![Setup](assets/dbd-new-basic.png)
1. Klicken Sie auf **[!DNL Next]**.
1. Wählen Sie [Datenexportkennzeichnungen](/help/using/features/data-export-controls.md#controls-labels) aus, die Sie für dieses Ziel festlegen möchten.
1. Klicken Sie auf **[!DNL Save]**.
1. Wählen Sie im Abschnitt **[!DNL Segment Mappings]** die Zielgruppensegmente aus, die Sie an dieses Ziel senden möchten.
1. Speichern Sie das Ziel.

## Überlegungen zur Segmentzuordnung {#segment-mapping-considerations}

Stellen Sie beim Zuordnen von Zielgruppensegmenten zu [!UICONTROL Twitter] sicher, dass die folgenden Anforderungen an die Segmentbenennung erfüllt sind:

* Geben Sie für Menschen lesbare Segmentzuordnungsnamen an. Es wird empfohlen, denselben Namen zu verwenden, den Sie für die Audience Manager-Segmente verwendet haben.
* Verwenden Sie keine Sonderzeichen (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) in Namen der Segment- und Segmentzuordnung. Wenn der Segmentname Ihres Audience Managers diese Zeichen enthält, entfernen Sie sie, bevor Sie das Segment einem [!UICONTROL Twitter] Ziel zuordnen.

### Beispiel

* Korrekter Segment- oder Zuordnungsname: „US- und europäische Käufer“;
* Falscher Segment- oder Zuordnungsname: „US, European 5h0pP3rs“.

>[!IMPORTANT]
>
>Die Namen bereits zugeordneter Segmente können nicht geändert werden. Audience Manager verwendet die Segmentnamen, um die Segmente in der Integration korrekt zu identifizieren.

## Überlegungen zu Übereinstimmungsraten {#match-rates-considerations}

* Die Integration zwischen Audience Manager und [!UICONTROL Twitter Custom Audiences] unterstützt Aufstockungen historischer Zielgruppen. Alle Segmentqualifikationen werden beim Erstellen des Ziels an [!UICONTROL Twitter] gesendet.

## Fehlerbehebung {#troubleshooting}

Beim Konfigurieren oder Senden von Daten an das Ziel &quot;Twitter Custom Audiences“ können die unten beschriebenen Fehler auftreten. In diesem Abschnitt wird erläutert, was die Fehler verursachen kann und wie sie behoben werden können.

| Fehlermeldung | Vorfall/Grund | Auflösung |
|---|---|---|
| `Internal server error` | Diese Fehlermeldung wird in der Audience Manager-Benutzeroberfläche angezeigt, wenn versucht wird, ein neues [!DNL Twitter] mit einer veralteten Version der Twitter-API hinzuzufügen. | Adobe-Kundenunterstützung kontaktieren. |
| `Twitter Error: This request is not properly authenticated` | Diese Fehlermeldung wird in der Audience Manager-Benutzeroberfläche angezeigt, wenn versucht wird, Segmente mit nicht unterstützten Segmentnamen dem Ziel zuzuordnen. | Überprüfen Sie die zugeordneten Segmentnamen und stellen Sie sicher, dass sie keine nicht unterstützten Zeichen enthalten. Siehe [Überlegungen zur Segmentzuordnung](#segment-mapping-considerations) für die Liste der nicht unterstützten Zeichen. |
| `Twitter Error: Account XXXXXXXXX was not found` | Diese Fehlermeldung wird in der Audience Manager-Benutzeroberfläche angezeigt, wenn die für das Ziel konfigurierten Anmeldeinformationen nicht für den Zugriff auf das entsprechende Twitter Ads-Konto autorisiert sind. | <ul><li>Stellen Sie sicher, dass die von Ihnen verwendeten Kontoanmeldeinformationen die [ Voraussetzungen ](#prerequisites).</li><li>Navigieren Sie zur Twitter Ads-Benutzeroberfläche mit denselben Anmeldeinformationen und überprüfen Sie, ob die richtigen Zielgruppen unter dem entsprechenden `XXXXXXXXX` angezeigt werden. </li></ul> |