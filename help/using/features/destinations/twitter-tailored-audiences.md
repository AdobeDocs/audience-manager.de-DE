---
description: In diesem Artikel wird beschrieben, wie Sie Twitter-Zielgruppen für neue und vorhandene Integrationen konfigurieren.
seo-description: In diesem Artikel wird beschrieben, wie Sie Twitter-Zielgruppen für neue und vorhandene Integrationen konfigurieren.
seo-title: Konfigurieren von auf Twitter zugeschnittenen Zielgruppen als gerätebasiertes Selbstbedienungsziel
solution: Audience Manager
title: Konfigurieren von auf Twitter zugeschnittenen Zielgruppen als gerätebasiertes Selbstbedienungsziel
translation-type: tm+mt
source-git-commit: cd770afc39221687f4eb47cc358d8d57a51b9fb5

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
2. Geben Sie im **[!DNL Basic Information]** Abschnitt einen Wert **[!DNL Name]** und **[!DNL Description]** für Ihr neues Ziel ein und verwenden Sie die folgenden Einstellungen: ![Setup](assets/dbd-new-basic.png)
3. Klicken Sie auf **[!DNL Next]**.
4. Wählen Sie die [Datenexportbeschriftungen](/help/using/features/data-export-controls.md#controls-labels) aus, die Sie für dieses Ziel festlegen möchten.
5. Klicken Sie auf **[!DNL Save]**.
6. Wählen Sie im **[!DNL Segment Mappings]** Abschnitt die Zielgruppensegmente aus, die Sie an dieses Ziel senden möchten.
7. Speichern Sie das Ziel.

## Vorhandene Twitter-Integrationen auf Selbstbedienungsverwaltung aktualisieren {#update-existing-twitter-integrations}

Um die Benutzerfreundlichkeit zu verbessern und den Konfigurationsprozess zu optimieren, aktualisieren wir die [!DNL Twitter Tailored Audiences] Integration auf ein Selbstbedienungsmodell, bei dem Sie die Konfiguration über die Benutzeroberfläche von Audience Manager selbst durchführen können. In diesem Abschnitt werden die Schritte beschrieben, die Sie zur Aktualisierung Ihrer vorhandenen Twitter-Integration unternehmen müssen.

>[!IMPORTANT]
>
>Die unten beschriebenen Schritte gelten nur, wenn Sie über eine bestehende Integration mit verfügen, die von einem Audience Manager-Berater oder der Kundenunterstützung konfiguriert [!DNL Twitter Tailored Audiences]wurde. Die vollständige Aktualisierung Ihres Ziels auf das Selbstbedienungsmodell kann bis zu 5 Werktage dauern. In der Zwischenzeit ist Ihr Ziel noch aktiv und Audience Manager sendet weiterhin Zielgruppen an das Ziel.
> Siehe Element Nr. 3 unter [Voraussetzungen](#prerequisites) , bevor Sie Ihre [!DNL Twitter Tailored Audiences] Version in das Selbstbedienungsmodell migrieren.

Gehen Sie wie folgt vor, um Ihr bestehendes [!DNL Twitter Tailored Audiences] Ziel in das Selbstbedienungsmodell zu migrieren.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!DNL Administration > Integrated Accounts]**.
1. Klicken Sie auf **[!DNL Add Account]**.
1. Wählen Sie [!DNL Twitter Tailored Audiences] und klicken Sie auf **[!DNL Confirm]** , um zur Authentifizierungsseite umgeleitet zu werden. ![integrierte Plattformen](assets/dbd-integrated-platforms.png)
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
