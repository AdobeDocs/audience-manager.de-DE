---
description: In diesem Artikel wird erläutert, wie Twitter-angepasste Zielgruppen für neue und vorhandene Integrationen konfiguriert werden.
seo-description: In diesem Artikel wird erläutert, wie Twitter-angepasste Zielgruppen für neue und vorhandene Integrationen konfiguriert werden.
seo-title: Twitter-angepasste Zielgruppen als selbstbedienungsbasiertes Ziel konfigurieren
solution: Audience Manager
title: Twitter-angepasste Zielgruppen als selbstbedienungsbasiertes Ziel konfigurieren
translation-type: tm+mt
source-git-commit: 96717384ebb82056f330312b0f99fb97086a2e05

---


# Als [!DNL Twitter Tailored Audiences] selbstbedienungsgerätebasiertes Ziel konfigurieren {#configure-twitter}

In diesem Artikel wird erläutert, wie [Twitter-angepasste Zielgruppen](https://business.twitter.com/en/targeting/tailored-audiences.html) für neue und vorhandene Integrationen konfiguriert werden.

## Voraussetzungen {#prerequisites}

Bevor Sie Ihr [!DNL Twitter Tailored Audiences] Ziel konfigurieren, überprüfen Sie die folgenden Twitter-Voraussetzungen, die Sie erfüllen müssen.

1. Ihr [!DNL Twitter Ads] Konto muss für Werbung qualifiziert sein. Neue [!DNL Twitter Ads] Konten sind in den ersten 2 Wochen nach deren Erstellung nicht für Werbung zulässig.
2. Für Ihr Twitter-Benutzerkonto, für das Sie Zugriff in Audience Manager haben, muss die Berechtigung [des Partner-Zielmanagers](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) aktiviert sein.
3. Wenn Sie Ihre bestehende Twitter-Integration auf Selbstbedienungsverwaltung [](#update-existing-twitter-integrations)aktualisieren, muss Ihr Twitter-Benutzerkonto über die Berechtigung [für den Anzeigenmanager](https://business.twitter.com/en/help/troubleshooting/multi-user-login-faq.html#accesslevels) verfügen.



## Neues [!DNL Twitter Tailored Audiences] Ziel hinzufügen {#add-new-twitter-destination}

In diesem Abschnitt werden die Schritte beschrieben, die Sie befolgen müssen, wenn Sie ein neues gerätebasiertes Ziel [!DNL Twitter Tailored Audiences]konfigurieren. Bei diesem Szenario wird angenommen, dass Sie kein vorhandenes Ziel [!DNL Twitter Tailored Audiences] über Ihren Adobe-Berater oder die Kundenunterstützung konfiguriert haben.

### Schritt 1. Authentifizieren bei [!DNL Twitter Tailored Audiences]{#step1-authenticate-with-twitter}

Bevor Sie das gerätebasierte Ziel hinzufügen können, müssen Sie Audience Manager und Ihr [!DNL Twitter Tailored Audiences] Konto verknüpfen. Gehen Sie wie folgt vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und wechseln **[!DNL Administration > Integrated Accounts]** Sie zu. Wenn Sie eine zuvor konfigurierte Integration mit einer Zielplattform haben, sollte sie auf dieser Seite aufgelistet werden. Andernfalls ist die Seite leer.
2. Klicken Sie auf **[!DNL Add Account]**.
3. Wählen [!DNL Twitter Tailored Audiences] Sie und klicken **[!DNL Confirm]** Sie auf, um zur Authentifizierungsseite umgeleitet zu werden. ![integrierte Plattformen](assets/dbd-integrated-platforms.png)
4. Nachdem Sie sich authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie Ihre zugeordneten Advertiserkonten sehen sollten. Wählen Sie das gewünschte Advertiserkonto aus und klicken **[!DNL Confirm]** Sie auf.

### Schritt 2: Neues gerätebasiertes Ziel erstellen {#step2-create-new-destination}

Nachdem Sie Audience Manager und Ihren Link [!DNL Twitter Tailored Audiences]verknüpft haben, können Sie das neue Ziel erstellen. Gehen Sie wie folgt vor:

>[!NOTE]
>
>Sie können den Namen eines vorhandenen gerätebasierten Ziels nicht ändern. Stellen Sie sicher, dass Sie einen Namen angeben, der Ihnen dabei hilft, das Ziel richtig zu identifizieren.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und **[!DNL Audience Data > Destinations]** klicken **[!DNL Create Destination]** Sie auf.
2. Geben Sie im **[!DNL Basic Information]** Abschnitt ein **[!DNL Name]** und **[!DNL Description]** für Ihr neues Ziel ein und verwenden Sie die folgenden Einstellungen: ![setup](assets/dbd-new-basic.png)
3. Klicken Sie auf **[!DNL Next]**.
4. Wählen Sie die [Datenexportbeschriftungen](/help/using/features/data-export-controls.md#controls-labels) aus, die Sie für dieses Ziel festlegen möchten.
5. Klicken Sie auf **[!DNL Save]**.
6. Wählen Sie im **[!DNL Segment Mappings]** Abschnitt die Zielgruppensegmente aus, die Sie an dieses Ziel senden möchten.
7. Speichern Sie das Ziel.

## Vorhandene Twitter-Integrationen auf Selbstbedienungsverwaltung aktualisieren {#update-existing-twitter-integrations}

Um die Benutzererfahrung zu verbessern und den Konfigurationsprozess zu optimieren, aktualisieren wir die [!DNL Twitter Tailored Audiences] Integration auf ein Selbstbedienungsmodell, wo Sie die Konfiguration selbst über die Benutzeroberfläche von Audience Manager durchführen können. In diesem Abschnitt werden die Schritte beschrieben, die Sie ergreifen müssen, um Ihre vorhandene Twitter-Integration zu aktualisieren.

>[!IMPORTANT]
>
>Die unten beschriebenen Schritte gelten nur, wenn Sie eine bestehende Integration mit [!DNL Twitter Tailored Audiences]einem Audience Manager-Berater oder Kundendienst haben. Der vollständige Aktualisierungsprozess Ihres Ziels auf das Selbstbedienungsmodell kann bis zu 5 Werktage dauern. In der Zwischenzeit ist Ihr Ziel noch aktiv und Audience Manager sendet weiterhin Zielgruppen an sie.
> Siehe Artikelnummer 3 unter [Voraussetzungen](#prerequisites) vor der Migration [!DNL Twitter Tailored Audiences] zum Selbstbedienungsmodell.

Gehen Sie wie folgt vor, um Ihr vorhandenes [!DNL Twitter Tailored Audiences] Ziel in das Selbstbedienungsmodell zu migrieren.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und wechseln **[!DNL Administration > Integrated Accounts]** Sie zu.
2. Klicken Sie auf **[!DNL Add Account]**.
3. Wählen [!DNL Twitter Tailored Audiences] Sie und klicken **[!DNL Confirm]** Sie auf, um zur Authentifizierungsseite umgeleitet zu werden. ![integrierte Plattformen](assets/dbd-integrated-platforms.png)
4. Sobald Sie sich bei Ihrem Twitter-Konto authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie Ihre zugeordneten Advertiserkonten sehen sollten. Wählen Sie das gewünschte Advertiserkonto aus und klicken **[!DNL Confirm]** Sie auf.

## Überlegungen zur Segmentzuordnung {#segment-mapping-considerations}

Achten Sie beim Zuordnen von Zielgruppensegmenten zu Twitter darauf, die folgenden Segmentbenennungsanforderungen zu erfüllen:

* Geben Sie für Menschen lesbare Segmentzuordnungsnamen an. Es wird empfohlen, denselben Namen wie für die Audience Manager-Segmente zu verwenden.
* Verwenden Sie keine Kommas in Segmenten und Segmentzuordnungsnamen.

**Beispiel**

* Segment oder Zuordnungsname korrigieren: " US- und europäische Käufer" ;
* Falsches Segment oder Zuordnungsname: " US, Europäische 5 h 0 pP 3 rs" .

>[!IMPORTANT]
>
>Sie können die Namen bereits zugeordneter Segmente nicht ändern. Audience Manager verwendet die Segmentnamen, um die Segmente in der Integration korrekt zu identifizieren.