---
description: This article explains how to configure Twitter Tailored Audiences for both new and existing integrations.
seo-description: This article explains how to configure Twitter Tailored Audiences for both new and existing integrations.
seo-title: Konfigurieren von auf Twitter zugeschnittenen Zielgruppen als gerätebasiertes Selbstbedienungsziel
solution: Audience Manager
title: Konfigurieren von auf Twitter zugeschnittenen Zielgruppen als gerätebasiertes Selbstbedienungsziel
translation-type: tm+mt
source-git-commit: c6318921b49603015b4670a361ec85ffa29abb30

---


# Konfiguration [!DNL Twitter Tailored Audiences] als gerätebasiertes Selbstbedienungsziel {#configure-twitter}

In diesem Artikel wird beschrieben, wie Sie [Twitter-Zielgruppen](https://business.twitter.com/en/targeting/tailored-audiences.html) für neue und vorhandene Integrationen konfigurieren.

## Voraussetzungen {#prerequisites}

Bevor Sie Ihr [!DNL Twitter Tailored Audiences] Ziel konfigurieren, überprüfen Sie die folgenden Twitter-Voraussetzungen, die Sie erfüllen müssen.

1. Ihr [!DNL Twitter Ads] Konto muss für Werbung zugelassen sein. Neue [!DNL Twitter Ads] Konten sind in den ersten 2 Wochen nach ihrer Erstellung nicht für Werbung zugelassen.
1. Für Ihr Twitter-Benutzerkonto, für das Sie Zugriff in Audience Manager autorisiert haben, muss die Berechtigung für den [Partner-Zielgruppen-Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) aktiviert sein.
1. Wenn Sie Ihre vorhandene Twitter-Integration auf die Selbstbedienungsverwaltung[](#update-existing-twitter-integrations)aktualisieren, muss für Ihr Twitter-Benutzerkonto die Berechtigung [Ad Manager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) aktiviert sein.
1. Wenden Sie sich beim Erstellen des ersten [!DNL Twitter Tailored Audiences] Ziels in Ihrer Audience Manager-Instanz an Adobe Consulting oder den Kundendienst, um die [!DNL Twitter] ID-Synchronisierung (Datenquelle-ID = 1123) für Ihr Konto zu aktivieren. Dies ist für die korrekte Synchronisierung zwischen Audience Manager und [!DNL Twitter]erforderlich.

## Neues [!DNL Twitter Tailored Audiences] Ziel hinzufügen {#add-new-twitter-destination}

In diesem Abschnitt werden die Schritte beschrieben, die Sie beim Konfigurieren eines neuen gerätebasierten Ziels für [!DNL Twitter Tailored Audiences]ausführen müssen. Bei diesem Szenario wird davon ausgegangen, dass Sie über Ihren Adobe-Berater oder die Kundenunterstützung kein vorhandenes [!DNL Twitter Tailored Audiences] Ziel konfiguriert haben.

### Schritt 1. Authentifizieren mit [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Bevor Sie das gerätebasierte Ziel hinzufügen können, müssen Sie Audience Manager und Ihr [!DNL Twitter Tailored Audiences] Konto verknüpfen. So geht das:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!DNL Administration > Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer Zielplattform haben, sollte diese auf dieser Seite aufgeführt werden. Andernfalls ist die Seite leer.
2. Klicken Sie auf **[!DNL Add Account]**.
3. Wählen Sie [!DNL Twitter Tailored Audiences] und klicken Sie auf **[!DNL Confirm]** , um zur Authentifizierungsseite umgeleitet zu werden.                     ![integrierte Plattformen](assets/dbd-integrated-platforms.png)
4. Nachdem Sie sich authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das gewünschte Advertiser-Konto aus und klicken Sie auf **[!DNL Confirm]**.

### Schritt 2: Neues gerätebasiertes Ziel erstellen {#step2-create-new-destination}

Nachdem Sie Audience Manager und Ihre [!DNL Twitter Tailored Audiences]verknüpft haben, können Sie das neue Ziel erstellen. So geht das:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen bei der korrekten Identifizierung des Ziels hilft.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!DNL Audience Data > Destinations]** und klicken Sie auf **[!DNL Create Destination]**.
2. In the **[!DNL Basic Information]** section, enter a **[!DNL Name]** and **[!DNL Description]** for your new destination, and use the settings below: ![setup](assets/dbd-new-basic.png)
3. Klicken Sie auf **[!DNL Next]**.
4. Choose the Data Export Labels that you want to set for this destination.[](/help/using/features/data-export-controls.md#controls-labels)
5. Klicken Sie auf **[!DNL Save]**.
6. In the  section, select the audience segments that you want to send to this destination.**[!DNL Segment Mappings]**
7. Save the destination.

## Update Existing Twitter Integrations To Self-Service Administration {#update-existing-twitter-integrations}

To improve the user experience and streamline the configuration process, we are upgrading the  integration to a self-service model, where you can perform the configuration yourself, from the Audience Manager UI. [!DNL Twitter Tailored Audiences] This section describes the steps you need to take to update your existing Twitter integration.

>[!IMPORTANT]
>
>The steps described below only apply if you have an existing integration with [!DNL Twitter Tailored Audiences], configured by an Audience Manager consultant or Customer Care. The full upgrade process of your destination to the self-service model may take up to 5 business days. In the meantime, your destination is still active and Audience Manager continues to send audiences to it.
> See item number 3 in Prerequisites before migrating your  to the self-service model.[](#prerequisites)[!DNL Twitter Tailored Audiences]

Follow the steps below to migrate your existing  destination to the self-service model.[!DNL Twitter Tailored Audiences]

1. Log in to your Audience Manager account and go to .**[!DNL Administration > Integrated Accounts]**
1. Klicken Sie auf **[!DNL Add Account]**.
1. Select  and click  to be redirected to the authentication page. [!DNL Twitter Tailored Audiences]**[!DNL Confirm]** ![integrated-platforms](assets/dbd-integrated-platforms.png)
1. Nachdem Sie sich bei Ihrem [!DNL Twitter] Konto authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das gewünschte Advertiser-Konto aus und klicken Sie auf **[!DNL Confirm]**.
1. Gehen Sie zu **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** und klicken Sie auf das zu konfigurierende Twitter-Ziel.
1. Klicken Sie auf **[!UICONTROL Edit]**. Klicken Sie im **[!UICONTROL Basic Information]** Abschnitt auf das **[!UICONTROL Integrated Account]** [!DNL Twitter] Dropdown-Menü und wählen Sie das Konto aus, für das Sie sich in Schritt 4 authentifiziert haben.
1. **[!UICONTROL Save]** das Ziel.

## Validieren der Migration zur Selbstbedienungsverwaltung {#migration-validation}

Die vollständige Migration vorhandener [!DNL Twitter] Integrationen zur Selbstbedienung kann bis zu 7 Tage dauern. Nach Abschluss der Migration zeigt Audience Manager eine Benachrichtigung in der Benutzeroberfläche an.

Außerdem wird in Ihrem [!DNL Twitter] Konto eine neue Gruppe von Zielgruppen mit dem Präfix [[!DNL Adobe DMP Audience]] angezeigt. Bitte geben Sie bis zu 7 Tage Zeit, bis die Zielgruppe vollständig aufgestockt wurde. Nach Abschluss der Migration sollten Sie diese neuen Zielgruppen anstelle der alten verwenden.

## Überlegungen zur Segmentzuordnung {#segment-mapping-considerations}

Achten Sie beim Zuordnen von Zielgruppensegmenten zu Twitter darauf, die folgenden Segmentbenennungsanforderungen zu erfüllen:

* Stellen Sie für Menschen lesbare Segmentzuordnungsnamen bereit. Es wird empfohlen, denselben Namen wie für die Segmente von Audience Manager zu verwenden.
* Verwenden Sie keine Kommas in Segmentzuordnungsnamen und Segmentzuordnungsnamen.

### Beispiel 

* Korrigieren Sie den Segment- oder Zuordnungsnamen: "US-amerikanische und europäische Käufer";
* Falscher Segment- oder Zuordnungsname: "US, European 5h0pP3rs".

>[!IMPORTANT]
>
>Sie können die Namen der bereits zugeordneten Segmente nicht ändern. Audience Manager verwendet die Segmentnamen, um die Segmente in der Integration korrekt zu identifizieren.

## Überlegungen zu Übereinstimmungsraten {#match-rates-considerations}

Bei der Verwendung [!UICONTROL Twitter Tailored Audiences]werden die Werte [!UICONTROL Segment Addressable Audience] und [!UICONTROL Segment Match Rate] Metriken auf der Zielseite nicht angezeigt. Dies ist ein normales Verhalten, da die Zielgruppenübereinstimmung mit den Übereinstimmungsraten für dieses Ziel von [!UICONTROL Twitter]Adobe verarbeitet und gehostet wird.
