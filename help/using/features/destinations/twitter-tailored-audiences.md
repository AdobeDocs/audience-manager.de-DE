---
description: In diesem Artikel wird beschrieben, wie Sie Twitter-Zielgruppen für neue und vorhandene Integrationen konfigurieren.
seo-description: In diesem Artikel wird beschrieben, wie Sie Twitter-Zielgruppen für neue und vorhandene Integrationen konfigurieren.
seo-title: Konfigurieren von auf Twitter zugeschnittenen Zielgruppen als gerätebasiertes Selbstbedienungsziel
solution: Audience Manager
title: Konfigurieren von auf Twitter zugeschnittenen Zielgruppen als gerätebasiertes Selbstbedienungsziel
translation-type: tm+mt
source-git-commit: 0f1ab99b648dd6e1eda5f2e5b6bd1f620c0331ee

---


# Konfiguration [!DNL Twitter Tailored Audiences] als gerätebasiertes Selbstbedienungsziel {#configure-twitter}

In diesem Artikel wird beschrieben, wie Sie eine Integration mit [Twitter-Zielgruppen](https://business.twitter.com/en/targeting/tailored-audiences.html)konfigurieren.

## Voraussetzungen {#prerequisites}

Bevor Sie Ihr [!DNL Twitter Tailored Audiences] Ziel konfigurieren, überprüfen Sie die folgenden Twitter-Voraussetzungen, die Sie erfüllen müssen.

1. Ihr [!DNL Twitter Ads] Konto muss für Werbung zugelassen sein. Neue [!DNL Twitter Ads] Konten sind in den ersten 2 Wochen nach ihrer Erstellung nicht für Werbung zugelassen.
2. Für Ihr [!DNL Twitter] Benutzerkonto, für das Sie Zugriff in Audience Manager autorisiert haben, muss die Berechtigung für den [Partner-Zielgruppen-Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) aktiviert sein.
3. Wenden Sie sich beim Erstellen des ersten [!DNL Twitter Tailored Audiences] Ziels in Ihrer Audience Manager-Instanz an Adobe Consulting oder den Kundendienst, um die [!DNL Twitter] ID-Synchronisierung (Datenquelle-ID = 1123) für Ihr Konto zu aktivieren. Dies ist für die korrekte Synchronisierung zwischen Audience Manager und [!DNL Twitter]erforderlich.

## Neues [!DNL Twitter Tailored Audiences] Ziel hinzufügen {#add-new-twitter-destination}

In diesem Abschnitt werden die Schritte beschrieben, die Sie beim Konfigurieren eines neuen gerätebasierten Ziels für [!DNL Twitter Tailored Audiences]ausführen müssen. Bei diesem Szenario wird davon ausgegangen, dass Sie über Ihren Adobe-Berater oder die Kundenunterstützung kein vorhandenes [!DNL Twitter Tailored Audiences] Ziel konfiguriert haben.

### Schritt 1. Authentifizieren mit [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Bevor Sie das gerätebasierte Ziel hinzufügen können, müssen Sie Audience Manager und Ihr [!DNL Twitter Tailored Audiences] Konto verknüpfen. So geht das:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!DNL Administration > Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer Zielplattform haben, sollte diese auf dieser Seite aufgeführt werden. Andernfalls ist die Seite leer.
1. Klicken Sie auf **[!DNL Add Account]**.
1. Wählen Sie [!DNL Twitter Tailored Audiences] und klicken Sie auf **[!DNL Confirm]** , um zur Authentifizierungsseite umgeleitet zu werden.                     ![integrierte Plattformen](assets/dbd-integrated-platforms.png)
1. Nachdem Sie sich authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das gewünschte Advertiser-Konto aus und klicken Sie auf **[!DNL Confirm]**.

### Schritt 2: Neues gerätebasiertes Ziel erstellen {#step2-create-new-destination}

Nachdem Sie Audience Manager und Ihre [!DNL Twitter Tailored Audiences]verknüpft haben, können Sie das neue Ziel erstellen. So geht das:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen bei der korrekten Identifizierung des Ziels hilft.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!DNL Audience Data > Destinations]** und klicken Sie auf **[!DNL Create Destination]**.
1. Geben Sie im **[!DNL Basic Information]** Abschnitt einen Wert **[!DNL Name]** und **[!DNL Description]** für Ihr neues Ziel ein und verwenden Sie die folgenden Einstellungen: ![Setup](assets/dbd-new-basic.png)
1. Klicken Sie auf **[!DNL Next]**.
1. Wählen Sie die [Datenexportbeschriftungen](/help/using/features/data-export-controls.md#controls-labels) aus, die Sie für dieses Ziel festlegen möchten.
1. Klicken Sie auf **[!DNL Save]**.
1. Wählen Sie im **[!DNL Segment Mappings]** Abschnitt die Zielgruppensegmente aus, die Sie an dieses Ziel senden möchten.
1. Speichern Sie das Ziel.

<!--
## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

To improve the user experience and streamline the configuration process, we are upgrading the [!DNL Twitter Tailored Audiences] integration to a self-service model, where you can perform the configuration yourself, from the Audience Manager UI. This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>The steps described below only apply if you have an existing integration with [!DNL Twitter Tailored Audiences], configured by an Audience Manager consultant or Customer Care.
> See item number 3 in [Prerequisites](#prerequisites) before migrating your [!DNL Twitter Tailored Audiences] to the self-service model.

Follow the steps below to migrate your existing [!DNL Twitter Tailored Audiences] destination to the self-service model.

1. Log in to your Audience Manager account and go to **[!DNL Administration > Integrated Accounts]**.
2. Click **[!DNL Add Account]**.
3. Select [!DNL Twitter Tailored Audiences] and click **[!DNL Confirm]** to be redirected to the authentication page. ![integrated-platforms](assets/dbd-integrated-platforms.png)
4. Once you've authenticated with your [!DNL Twitter] account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click **[!DNL Confirm]**.
5. Go to **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** and click the Twitter destination that you need to configure.
6. Click **[!UICONTROL Edit]**. In the **[!UICONTROL Basic Information]** section, click the **[!UICONTROL Integrated Account]** drop-down menu and select the [!DNL Twitter] account that you have authenticated with at Step 4.
7. **[!UICONTROL Save]** the destination.

## Validating the Migration to Self-Service Administration {#migration-validation}

The complete migration of existing [!DNL Twitter] integrations to self-service administration can take up to 7 days. Once the migration is complete, Audience Manager shows you a notification in the UI.

You will also see a new set of audiences in your [!DNL Twitter] account, with their names prefixed by [[!DNL Adobe DMP Audience]]. Please allow up to 7 days for the audience population to be completely backfilled. Once the migration is complete, you should use these new audiences instead of the old ones. -->

## Überlegungen zur Segmentzuordnung {#segment-mapping-considerations}

Achten Sie beim Zuordnen von Zielgruppensegmenten zu [!UICONTROL Twitter]darauf, die folgenden Segmentbenennungsanforderungen zu erfüllen:

* Stellen Sie für Menschen lesbare Segmentzuordnungsnamen bereit. Es wird empfohlen, denselben Namen wie für die Segmente von Audience Manager zu verwenden.
* Verwenden Sie keine Sonderzeichen (`,``%``:``;``@``/` `=` `?` `$`) in Segmentzuordnungsnamen. Wenn Ihr Audience Manager-Segmentname diese Zeichen enthält, entfernen Sie diese, bevor Sie das Segment einem [!UICONTROL Twitter] Ziel zuordnen.

### Beispiel 

* Korrigieren Sie den Segment- oder Zuordnungsnamen: "US-amerikanische und europäische Käufer";
* Falscher Segment- oder Zuordnungsname: "US, European 5h0pP3rs".

>[!IMPORTANT]
>
>Sie können die Namen der bereits zugeordneten Segmente nicht ändern. Audience Manager verwendet die Segmentnamen, um die Segmente in der Integration korrekt zu identifizieren.

## Überlegungen zu Übereinstimmungsraten {#match-rates-considerations}

* Bei der Verwendung [!UICONTROL Twitter Tailored Audiences]werden die Werte [!UICONTROL Segment Addressable Audience] und [!UICONTROL Segment Match Rate] Metriken auf der Zielseite nicht angezeigt. Dies ist ein normales Verhalten, da die Zielgruppenübereinstimmung mit den Übereinstimmungsraten für dieses Ziel von [!UICONTROL Twitter]Adobe verarbeitet und gehostet wird.
* Zurzeit unterstützt die Integration zwischen Audience Manager und [!UICONTROL Twitter Tailored Audiences] nicht die Rückfüllung historischer Zielgruppen. Das bedeutet, dass nur die Segmentqualifikationen, die *nach* der Zuordnung des Segments zu einem Twitter-Ziel auftreten, in Echtzeit an gesendet werden [!UICONTROL Twitter] .
