---
description: In diesem Artikel wird beschrieben, wie Sie benutzerdefinierte Twitter-Zielgruppen für neue und vorhandene Integrationen konfigurieren.
seo-description: This article explains how to configure Twitter Custom Audiences for both new and existing integrations.
seo-title: Configure Twitter Custom Audiences as a Self-Service Device-Based Destination
solution: Audience Manager
title: Benutzerdefinierte Twitter-Zielgruppen als gerätebasiertes Selbstbedienungsziel konfigurieren
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
source-git-commit: 72be9e032ec3c92cf09a5286baa872b884feaaa0
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 1%

---

# Konfigurieren [!DNL Twitter Custom Audiences] als gerätebasiertes Selbstbedienungsziel {#configure-twitter}

In diesem Artikel wird beschrieben, wie Sie eine Integration mit [Benutzerdefinierte twitter-Zielgruppen](https://business.twitter.com/en/help/campaign-setup/campaign-targeting/custom-audiences.html).

## Voraussetzungen {#prerequisites}

Vor der Konfiguration [!DNL Twitter Custom Audiences] Ziel festzulegen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen.

* Ihre [!DNL Twitter Ads] für Werbung zugelassen sein. Neu [!DNL Twitter Ads] -Konten sind in den ersten zwei Wochen nach ihrer Erstellung nicht für Werbung geeignet.
* Ihre [!DNL Twitter] Das Benutzerkonto, für das Sie in Audience Manager autorisiert haben, muss über die [Partner-Audience-Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) -Berechtigung aktiviert ist.
* Beim Erstellen der ersten [!DNL Twitter Custom Audiences] Ziel in Ihrer Audience Manager-Instanz, wenden Sie sich an Adobe Consulting oder die Kundenunterstützung, um die [!DNL Twitter] ID-Synchronisierung (Datenquellen-ID = 1123) für Ihr Konto. Dies ist für die korrekte Synchronisierung zwischen Audience Manager und erforderlich. [!DNL Twitter].

## Neu hinzufügen [!DNL Twitter Custom Audiences] Ziel {#add-new-twitter-destination}

In diesem Abschnitt werden die Schritte beschrieben, die Sie beim Konfigurieren eines neuen gerätebasierten Ziels für [!DNL Twitter Custom Audiences]. In diesem Szenario wird davon ausgegangen, dass Sie nicht über vorhandene [!DNL Twitter Custom Audiences] Ziel, das über Ihren Adobe-Berater oder die Kundenunterstützung konfiguriert wurde.

### Schritt 1. Authentifizieren mit [!DNL Twitter Custom Audiences] {#step1-authenticate-with-twitter}

Bevor Sie das gerätebasierte Ziel hinzufügen können, müssen Sie Audience Manager und Ihre [!DNL Twitter Custom Audiences] -Konto. Gehen Sie wie folgt vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und navigieren Sie zu **[!DNL Administration > Integrated Accounts]**. Wenn Sie bereits eine Integration mit einer Zielplattform konfiguriert haben, sollte diese auf dieser Seite aufgeführt sein. Andernfalls ist die Seite leer.
1. Klicken **[!DNL Add Account]**.
1. Auswählen [!DNL Twitter Custom Audiences] und klicken Sie auf **[!DNL Confirm]** auf die Authentifizierungsseite umgeleitet werden.

   ![integrierte Plattformen](assets/dbd-integrated-platforms.png)

1. Nachdem Sie sich authentifiziert haben, werden Sie zu dem Audience Manager weitergeleitet, in dem Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das Advertiser-Konto aus, das Sie verwenden möchten, und klicken Sie auf **[!DNL Confirm]**.

### Schritt 2: Neues gerätebasiertes Ziel erstellen {#step2-create-new-destination}

Nach der Verknüpfung von Audience Manager und [!DNL Twitter Custom Audiences], können Sie das neue Ziel erstellen. Gehen Sie wie folgt vor:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen bei der korrekten Identifizierung des Ziels hilft.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, navigieren Sie zu **[!DNL Audience Data > Destinations]** und klicken Sie auf **[!DNL Create Destination]**.
1. Im **[!DNL Basic Information]** eingeben. **[!DNL Name]** und **[!DNL Description]** und verwenden Sie die folgenden Einstellungen: ![Setup](assets/dbd-new-basic.png)
1. Klicken **[!DNL Next]**.
1. Wählen Sie die [Datenexportbeschriftungen](/help/using/features/data-export-controls.md#controls-labels) die Sie für dieses Ziel festlegen möchten.
1. Klicken **[!DNL Save]**.
1. Im **[!DNL Segment Mappings]** Wählen Sie die Zielgruppensegmente aus, die Sie an dieses Ziel senden möchten.
1. Speichern Sie das Ziel.

## Überlegungen zur Segmentzuordnung {#segment-mapping-considerations}

Beim Zuordnen von Zielgruppensegmenten zu [!UICONTROL Twitter]müssen Sie die folgenden Segmentbenennungsanforderungen erfüllen:

* Stellen Sie für Menschen lesbare Namen für die Segmentzuordnung bereit. Es wird empfohlen, denselben Namen zu verwenden, den Sie für die Audience Manager-Segmente verwendet haben.
* Verwenden Sie keine Sonderzeichen (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) in den Namen der Segment- und Segmentzuordnung. Wenn der Segmentname Ihres Audience Managers diese Zeichen enthält, entfernen Sie diese, bevor Sie das Segment einem [!UICONTROL Twitter] Ziel.

### Beispiel

* Richtiger Segment- oder Zuordnungsname: &quot;US- und europäische Käufer&quot;;
* Falscher Segment- oder Zuordnungsname: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Sie können die Namen von bereits zugeordneten Segmenten nicht ändern. Audience Manager verwendet die Segmentnamen, um die Segmente in der Integration korrekt zu identifizieren.

## Überlegungen zu Übereinstimmungsraten {#match-rates-considerations}

* Die Integration zwischen Audience Manager und [!UICONTROL Twitter Custom Audiences] unterstützt historische Zielgruppen-Backups. Alle Segmentqualifikationen werden an gesendet. [!UICONTROL Twitter] wenn Sie das Ziel erstellen.

## Fehlerbehebung  {#troubleshooting}

Beim Konfigurieren oder Senden von Daten an das Twitter Custom Audiences-Ziel treten möglicherweise die unten beschriebenen Fehler auf. In diesem Abschnitt wird erläutert, was zu Fehlern führen kann und wie diese behoben werden können.

| Fehlermeldung | Vorfall/Grund | Auflösung |
|---|---|---|
| `Internal server error` | Diese Fehlermeldung wird in der Audience Manager-Benutzeroberfläche angezeigt, wenn versucht wird, eine neue [!DNL Twitter] -Konto mit einer veralteten Version der Twitter-API verwenden. | Wenden Sie sich an die Adobe-Kundenunterstützung. |
| `Twitter Error: This request is not properly authenticated` | Diese Fehlermeldung wird in der Audience Manager-Benutzeroberfläche angezeigt, wenn versucht wird, Segmente mit nicht unterstützten Segmentnamen dem Ziel zuzuordnen. | Überprüfen Sie die zugeordneten Segmentnamen und stellen Sie sicher, dass sie keine nicht unterstützten Zeichen enthalten. Siehe [Überlegungen zur Segmentzuordnung](#segment-mapping-considerations) für die Liste der nicht unterstützten Zeichen. |
| `Twitter Error: Account XXXXXXXXX was not found` | Diese Fehlermeldung wird in der Audience Manager-Benutzeroberfläche angezeigt, wenn die für das Ziel konfigurierten Anmeldeinformationen nicht für den Zugriff auf das entsprechende Twitter Ads-Konto autorisiert sind. | <ul><li>Stellen Sie sicher, dass die von Ihnen verwendeten Kontoanmeldeinformationen den [Voraussetzungen](#prerequisites).</li><li>Navigieren Sie zur Twitter Ads-Benutzeroberfläche mit denselben Anmeldedaten und überprüfen Sie, ob die richtigen Zielgruppen unter den entsprechenden angezeigt werden. `XXXXXXXXX` -Konto. </li></ul> |