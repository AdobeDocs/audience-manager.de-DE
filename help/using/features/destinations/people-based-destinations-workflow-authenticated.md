---
description: 'Diese Seite enthält eine schrittweise Anleitung dazu, wie Offline-CRM-Daten mit Echtzeit-Verhaltensdaten für authentifizierte Benutzer kombiniert werden können, um Zielgruppensegmente zu erstellen und diese Zielgruppensegmente dann an People-basierte Ziele zu senden. '
seo-description: 'Diese Seite enthält eine schrittweise Anleitung dazu, wie Offline-CRM-Daten mit Echtzeit-Verhaltensdaten für authentifizierte Benutzer kombiniert werden können, um Zielgruppensegmente zu erstellen und diese Zielgruppensegmente dann an People-basierte Ziele zu senden.  '
seo-title: Workflow C - Personalisierung basierend auf authentifizierter Aktivität in Kombination mit Offline-Daten
solution: Audience Manager
title: Workflow C - Personalisierung basierend auf authentifizierter Aktivität in Kombination mit Offline-Daten
feature: Benutzerbasierte Ziele
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 5%

---

# Workflow C - Personalisierung basierend auf authentifizierter Aktivität in Kombination mit Offline-Daten {#workflow-c}

>[!IMPORTANT]
>Dieser Artikel enthält die Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um rechtliche Hinweise zu erhalten.

Diese Seite enthält eine schrittweise Anleitung dazu, wie Offline-[!DNL CRM]-Daten mit Echtzeit-Verhaltensdaten für authentifizierte Benutzer kombiniert werden, um Zielgruppensegmente zu erstellen, und diese Zielgruppensegmente dann an [!DNL People-Based Destinations] sendet.

## Schritt 1: Konfigurieren der Datenquelleneinstellungen {#configure-data-source-settings}

Je nachdem, ob Ihre [DPUUIDs](../../reference/ids-in-aam.md) in Kleinbuchstaben und Hash-E-Mail-Adressen enthalten, müssen Sie möglicherweise die Datenquelle konfigurieren, in der die Hash-E-Mail-Adressen gespeichert werden.

 

**Szenario 1: Ihre  [](../../reference/ids-in-aam.md) DPUUIDs sind bereits in Kleinbuchstaben, gehashte E-Mail-Adressen.**

Überspringen Sie in diesem Fall [Schritt 5 - Konfiguration der personenbasierten Plattformauthentifizierung](#configure-authentication).

 

**Szenario 2: Ihre  [](../../reference/ids-in-aam.md) DPUUIDs sind keine E-Mail-Adressen mit Hash-Zeichen in Kleinbuchstaben.**

In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen, in der Ihre Hash-E-Mail-Adressen gespeichert werden. Gehen Sie wie folgt vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, navigieren Sie zu **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** und klicken Sie auf **[!UICONTROL Add New]**.
1. Geben Sie für Ihre neue Datenquelle **[!UICONTROL Name]** und **[!UICONTROL Description]** ein.
1. Wählen Sie im Dropdown-Menü **[!UICONTROL ID Type]** die Option **[!UICONTROL Cross Device]** aus.
1. Wählen Sie im Abschnitt **[!UICONTROL Data Source Settings]** die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Wählen Sie im Dropdown-Menü die **[!UICONTROL Emails(SHA256, lowercased)]**-Beschriftung für diese Datenquelle aus.
   >[!IMPORTANT]
   >
   >Diese Option bezeichnet die Datenquelle nur als die mit diesem spezifischen Algorithmus gehashten Daten. In diesem Schritt werden die Daten von Audience Manager nicht gehasht. Stellen Sie sicher, dass die E-Mail-Adressen, die Sie in dieser Datenquelle speichern möchten, bereits mit dem Algorithmus [!DNL SHA256] gehasht sind. Andernfalls können Sie es nicht für [!DNL People-Based Destinations] verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Unter [Daten-Onboarding](people-based-destinations-prerequisites.md#data-onboarding) finden Sie häufig gestellte Fragen dazu, wie Sie Ihre Offline-Daten für personenbasierte Ziele in den Audience Manager einbringen sollten.

Sehen Sie sich das Video unten an, um ein Video-Tutorial zum Erstellen einer Datenquelle für [!UICONTROL People-Based Destinations] anzuzeigen.

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Schritt 2: Verwenden deklarierter IDs zum Abgleichen von DPUUIDs mit Hash-E-Mail-Adressen über HTTP-Aufrufe in Echtzeit {#match-email-addresses}

Um authentifizierte Benutzer für regelbasierte Eigenschaften zu qualifizieren, müssen Sie die Eigenschaftsqualifizierung über [deklarierte IDs](../declared-ids.md) senden.

### Beispiel

Angenommen, Sie haben die beiden folgenden Datenquellen erstellt.

| Datenquellen-ID | Datenquelleninhalte |
| -------------- | -------------------------- |
| 999999 | Vorhandene DPUUIDs (CRM-IDs) |
| 987654 | Hash-E-Mail-Adressen |

 

Anschließend möchten Sie die unten stehenden CRM-IDs für die Eigenschaft in der Tabelle qualifizieren.

| DPUUID (CRM ID) | E-Mail-Adresse | Hash-E-Mail-Adresse | Eigenschaft |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f11625093a19bc32fff15041 149 | location = US |

 

Ihre deklarierte ID sollte dieser Syntax entsprechen:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

Im obigen Beispiel sollte der deklarierte ID-Aufruf wie folgt aussehen:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Schritt 3: Erstellen einer Profilzusammenführungsregel für die Segmentierung {#create-profile-merge-rule-segmentation}

Der nächste Schritt besteht darin, eine neue Zusammenführungsregel zu erstellen, mit der Sie die Zielgruppensegmente erstellen können, die an Ihre [!DNL People-Based Destinations] gesendet werden.

>[!IMPORTANT]
>
>Wenn Sie bereits eine Regel mit den Optionen **[!UICONTROL Current Authenticated Profiles]** oder **[!UICONTROL Last Authenticated Profiles]** definiert haben, können Sie zu [Schritt 4 - Zielgruppensegmente erstellen](#create-audience-segments) überspringen.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Klicken **[!UICONTROL Add New Rule]**.
3. Geben Sie eine Profilzusammenführungsregel **[!UICONTROL Name]** und **[!UICONTROL Description]** ein.
4. Wählen Sie im Abschnitt **[!UICONTROL Profile Merge Rule Setup]** die Regel **[!UICONTROL Current Authenticated Profiles]** oder **[!UICONTROL Last Authenticated Profiles]** aus der Liste **[!UICONTROL Cross-Device Options]** aus.
5. Wählen Sie in der Liste **[!UICONTROL Cross-Device Profile Options]** die Datenquellen aus, für die Sie die Segmentierung ausführen möchten. Dies sollten die Datenquellen sein, die Ihre vorhandenen DPUUIDs enthalten.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Schritt 4: Erstellen von Zielgruppensegmenten {#create-audience-segments}

Verwenden Sie zum Erstellen neuer Segmente den [Segment Builder](../segments/segment-builder.md). Wenn Sie bereits über Zielgruppensegmente verfügen, die Sie an [!DNL People-Based Destinations] senden möchten, gehen Sie zu [Schritt 5: Konfigurieren der personenbasierten Plattformauthentifizierung](#configure-authentication).

## Schritt 5: Konfigurieren der personenbasierten Plattformauthentifizierung {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Wenn Sie bereits eine Integration mit einer sozialen Plattform konfiguriert haben, sollte diese auf dieser Seite aufgeführt sein. Andernfalls ist die Seite leer.
   ![People-based-integration](assets/pbd-config.png)
2. Klicken **[!UICONTROL Add Account]**.
3. Wählen Sie im Dropdown-Menü **[!UICONTROL People-Based Platform]** die Plattform aus, mit der Sie die Integration konfigurieren möchten.
   ![people-based-platform](assets/pbd-add.png)
4. Klicken Sie auf **[!UICONTROL Confirm]** , um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
5. Nachdem Sie sich bei Ihrem Social-Plattform-Konto authentifiziert haben, werden Sie zu dem Audience Manager weitergeleitet, in dem Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das Advertiser-Konto aus, das Sie verwenden möchten, und klicken Sie auf **[!UICONTROL Confirm]**.
6. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Sie darüber zu informieren, ob das Konto erfolgreich hinzugefügt wurde. Mit der Benachrichtigung können Sie auch eine Kontakt-E-Mail-Adresse hinzufügen, um Benachrichtigungen zu erhalten, wenn die Authentifizierung der sozialen Plattform bald abläuft.

>[!IMPORTANT]
>
>Audience Manager verarbeitet die Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Weitere Informationen zur Verlängerung der abgelaufenen Token finden Sie unter Erneuerung des Authentifizierungstokens .

## Schritt 6: Erstellen eines personenbasierten Ziels {#create-destination}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, navigieren Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** und klicken Sie auf **[!UICONTROL Create Destination]**.
1. Geben Sie im Abschnitt **[!UICONTROL Basic Information]** einen **[!UICONTROL Name]** und **[!UICONTROL Description]** für die neue Datenquelle ein und verwenden Sie die folgenden Einstellungen:
   * **[!UICONTROL Category]**: integrierte Plattformen;
   * **[!UICONTROL Type]**: personenbezogene Daten;
   * **[!UICONTROL Platform]**: Wählen Sie die personenbasierte Plattform aus, an die Sie Zielgruppensegmente senden möchten.
   * **[!UICONTROL Account]**: Wählen Sie das gewünschte Advertiser-Konto aus, das mit der ausgewählten Plattform verknüpft ist.
      ![create-destination](assets/pbd-create-destination.png)
1. Klicken **[!UICONTROL Next]**.
1. Wählen Sie die **[!UICONTROL Data Export Labels]** aus, die Sie für dieses Ziel festlegen möchten.
1. Wählen Sie im Abschnitt **[!UICONTROL Configuration]** die Datenquelle aus, die Ihre Hash-Datenquellen enthält.
1. Wählen Sie im Abschnitt **[!UICONTROL Segment Mappings]** die Segmente aus, die Sie an dieses Ziel senden möchten. Dies wären die Segmente, die Sie unter [Schritt 4 - Erstellen von Zielgruppensegmenten](#create-audience-segments) erstellt haben.
1. Speichern Sie das Ziel.
