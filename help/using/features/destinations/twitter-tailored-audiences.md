---
description: In diesem Artikel wird beschrieben, wie Sie Twitter-Audiencen für neue und vorhandene Integrationen konfigurieren.
seo-description: In diesem Artikel wird beschrieben, wie Sie Twitter-Audiencen für neue und vorhandene Integrationen konfigurieren.
seo-title: Konfigurieren von auf Twitter zugeschnittenen Zielgruppen als gerätebasiertes Selbstbedienungsziel
solution: Audience Manager
title: Konfigurieren von auf Twitter zugeschnittenen Zielgruppen als gerätebasiertes Selbstbedienungsziel
feature: People-based Destinations
exl-id: 13b36469-3f61-47b1-9355-ca329de1fb24
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 4%

---

# [!DNL Twitter Tailored Audiences] als gerätebasiertes Selbstbedienungsziel {#configure-twitter} konfigurieren

In diesem Artikel wird beschrieben, wie Sie eine Integration mit [Twitter-Audiencen mit maßgeschneiderten Vorgaben](https://business.twitter.com/en/targeting/tailored-audiences.html) konfigurieren.

## Voraussetzungen {#prerequisites}

Bevor Sie Ihr [!DNL Twitter Tailored Audiences]-Ziel konfigurieren, überprüfen Sie die folgenden Twitter-Voraussetzungen, die Sie erfüllen müssen.

1. Ihr [!DNL Twitter Ads]-Konto muss für Werbung zugelassen sein. Neue [!DNL Twitter Ads]-Konten sind in den ersten 2 Wochen nach ihrer Erstellung nicht für Werbung zugelassen.
2. Für Ihr [!DNL Twitter]-Benutzerkonto, für das Sie den Zugriff in Audience Manager genehmigt haben, muss die Berechtigung [Partner-Audience-Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) aktiviert sein.
3. Wenden Sie sich beim Erstellen des ersten [!DNL Twitter Tailored Audiences]-Ziels in Ihrer Audience Manager-Instanz an Adobe Consulting oder den Kundendienst, um die [!DNL Twitter]-ID-Synchronisierung (Datenquelle-ID = 1123) für Ihr Konto zu aktivieren. Dies ist für die korrekte Synchronisierung zwischen Audience Manager und [!DNL Twitter] erforderlich.

## hinzufügen eines neuen [!DNL Twitter Tailored Audiences] Ziels {#add-new-twitter-destination}

In diesem Abschnitt werden die Schritte beschrieben, die Sie beim Konfigurieren eines neuen gerätebasierten Ziels für [!DNL Twitter Tailored Audiences] befolgen müssen. Bei diesem Szenario wird davon ausgegangen, dass Sie kein [!DNL Twitter Tailored Audiences]-Ziel über Ihren Adobe-Berater oder den Kundendienst konfiguriert haben.

### Schritt 1. Authentifizieren Sie sich mit [!DNL Twitter Tailored Audiences] {#step1-authenticate-with-twitter}

Bevor Sie das gerätebasierte Ziel hinzufügen können, müssen Sie Audience Manager und Ihr [!DNL Twitter Tailored Audiences]-Konto verknüpfen. So geht das:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!DNL Administration > Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer Zielplattform haben, sollte diese auf dieser Seite aufgeführt werden. Andernfalls ist die Seite leer.
1. Klicken **[!DNL Add Account]**.
1. Wählen Sie [!DNL Twitter Tailored Audiences] und klicken Sie auf **[!DNL Confirm]**, um zur Authentifizierungsseite umgeleitet zu werden.                     ![integrierte Plattformen](assets/dbd-integrated-platforms.png)
1. Nachdem Sie sich authentifiziert haben, werden Sie an den Audience Manager weitergeleitet, in dem Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das gewünschte Advertiser-Konto aus und klicken Sie auf **[!DNL Confirm]**.

### Schritt 2: Neues gerätebasiertes Ziel erstellen {#step2-create-new-destination}

Nachdem Sie den verknüpften Audience Manager und das [!DNL Twitter Tailored Audiences] verknüpft haben, können Sie das neue Ziel erstellen. So geht das:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen bei der korrekten Identifizierung des Ziels hilft.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!DNL Audience Data > Destinations]** und klicken Sie auf **[!DNL Create Destination]**.
1. Geben Sie im Abschnitt **[!DNL Basic Information]** einen **[!DNL Name]** und **[!DNL Description]** für Ihr neues Ziel ein und verwenden Sie die folgenden Einstellungen: ![setup](assets/dbd-new-basic.png)
1. Klicken **[!DNL Next]**.
1. Wählen Sie die für dieses Ziel festzulegenden [Datenexportbezeichnungen](/help/using/features/data-export-controls.md#controls-labels).
1. Klicken **[!DNL Save]**.
1. Wählen Sie im Abschnitt **[!DNL Segment Mappings]** die Audiencen aus, die Sie an dieses Ziel senden möchten.
1. Speichern Sie das Ziel.

## Überlegungen zur Segmentzuordnung {#segment-mapping-considerations}

Stellen Sie beim Zuordnen von Segmenten zu [!UICONTROL Twitter] sicher, dass die folgenden Segmentbenennungsanforderungen erfüllt sind:

* Stellen Sie für Menschen lesbare Segmentzuordnungsnamen bereit. Es wird empfohlen, denselben Namen zu verwenden, den Sie für die Audience Manager-Segmente verwendet haben.
* Verwenden Sie keine Sonderzeichen (`+` `&` `,` `%` `:` `;` `@` `/` `=` `?` `$`) in Segmentzuordnungsnamen. Wenn der Segmentname des Audience Managers diese Zeichen enthält, entfernen Sie diese, bevor Sie das Segment einem [!UICONTROL Twitter]-Ziel zuordnen.

### Beispiel

* Korrigieren Sie den Segment- oder Zuordnungsnamen: &quot;US-amerikanische und europäische Käufer&quot;;
* Falscher Segment- oder Zuordnungsname: &quot;US, European 5h0pP3rs&quot;.

>[!IMPORTANT]
>
>Sie können die Namen der bereits zugeordneten Segmente nicht ändern. Audience Manager verwendet die Segmentnamen, um die Segmente in der Integration korrekt zu identifizieren.

## Überlegungen zu Übereinstimmungsraten {#match-rates-considerations}

* Die Integration zwischen Audience Manager und [!UICONTROL Twitter Tailored Audiences] unterstützt Backfills für historische Audiencen. Alle Segmentqualifikationen werden beim Erstellen des Ziels an [!UICONTROL Twitter] gesendet.
