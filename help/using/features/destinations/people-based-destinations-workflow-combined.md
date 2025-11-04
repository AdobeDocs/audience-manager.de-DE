---
description: Auf dieser Seite finden Sie eine schrittweise Anleitung dazu, wie Sie Offline-CRM-Daten mit Verhaltensdaten kombinieren, die Sie bereits in Audience Manager haben, um neue Zielgruppensegmente zu erstellen, und diese Zielgruppensegmente dann an personenbasierte Ziele senden.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow A - Personalization Based on All Online Activity Combined with Offline Data
solution: Audience Manager
title: Workflow A - Personalization basiert auf allen Online-Aktivitäten in Kombination mit Offline-Daten
feature: People-based Destinations
exl-id: 1f906955-8fe7-4cce-95d6-0e4275d523e8
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 0%

---

# Workflow A - Personalization basiert auf allen Online-Aktivitäten in Kombination mit Offline-Daten {#workflow-a}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Verwendung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um Rechtsberatung zu erhalten.

Auf dieser Seite finden Sie eine schrittweise Anleitung dazu, wie Sie Offline-[!DNL CRM] mit Verhaltensdaten kombinieren, die Sie bereits in Audience Manager haben, um neue Zielgruppensegmente zu erstellen, und diese Zielgruppensegmente dann an [!DNL People-Based Destinations] senden.

## Schritt 1: Konfigurieren der Einstellungen für Data Source {#configure-data-source-settings}

Je nachdem, ob Ihre [DPUUIDs](../../reference/ids-in-aam.md) E-Mail-Adressen in Kleinbuchstaben mit Hash vorliegen, müssen Sie möglicherweise die Datenquelle konfigurieren, in der die Hash-E-Mail-Adressen gespeichert werden.

 

**Szenario 1: Ihre [DPUUIDs](../../reference/ids-in-aam.md) werden bereits in Kleinbuchstaben geschrieben und enthalten Hash-E-Mail-Adressen.**

In diesem Fall müssen Sie die entsprechende Datenquelle als solche kennzeichnen:

1. Gehen Sie zu [!UICONTROL Audience Data] > [!UICONTROL Data Sources].
1. Suchen Sie die Datenquelle, die Ihre [DPUUIDs](../../reference/ids-in-aam.md) enthält, und klicken Sie darauf.
1. Wählen Sie im Dropdown-Menü **[!UICONTROL ID Type]** die Option **[!UICONTROL Cross Device]** aus.
1. Stellen Sie sicher, dass die Option [!UICONTROL Cannot be tied to personally identifiable information] deaktiviert ist.
1. Wählen Sie im Abschnitt **[!UICONTROL Data Source Settings]** die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Wählen Sie im Dropdown-Menü die **[!UICONTROL Emails(SHA256, lowercased)]** für diese Datenquelle aus.

   >[!IMPORTANT]
   >
   >Diese Option kennzeichnet die Datenquelle nur als mit Daten, die mit diesem bestimmten Algorithmus gehasht wurden. Audience Manager hasst die Daten in diesem Schritt nicht. Stellen Sie sicher, dass die E-Mail-Adressen, die Sie in dieser Datenquelle speichern möchten, bereits mit dem [!DNL SHA256]-Algorithmus gehasht wurden. Andernfalls können Sie es nicht für [!DNL People-Based Destinations] verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

1. Speichern Sie die Datenquelleneinstellungen.

 

**Szenario 2: Ihre [DPUUIDs](../../reference/ids-in-aam.md) sind keine gehashten E-Mail-Adressen in Kleinbuchstaben.**

In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen, in der Ihre gehashten E-Mail-Adressen gespeichert werden. Gehen Sie wie folgt vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** und klicken Sie auf **[!UICONTROL Add New]**.
1. Geben Sie einen [!UICONTROL Name] und einen [!UICONTROL Description] für Ihre neue Datenquelle ein.
1. Wählen Sie im Dropdown-Menü **[!UICONTROL ID Type]** die Option **[!UICONTROL Cross Device]** aus.
1. Wählen Sie im Abschnitt **[!UICONTROL Data Source Settings]** die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Wählen Sie im Dropdown-Menü die **[!UICONTROL Emails(SHA256, lowercased)]** für diese Datenquelle aus.

   >[!IMPORTANT]
   >
   >Diese Option kennzeichnet die Datenquelle nur als mit Daten, die mit diesem bestimmten Algorithmus gehasht wurden. Audience Manager hasst die Daten in diesem Schritt nicht. Stellen Sie sicher, dass die E-Mail-Adressen, die Sie in dieser Datenquelle speichern möchten, bereits mit dem [!DNL SHA256]-Algorithmus gehasht wurden. Andernfalls können Sie es nicht für [!DNL People-Based Destinations] verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Speichern Sie die Datenquelleneinstellungen.

Sehen Sie sich das folgende Video an, um ein Video-Tutorial zum Erstellen einer Datenquelle für [!UICONTROL People-Based Destinations] zu erhalten.

>[!VIDEO](https://video.tv.adobe.com/v/32165?captions=ger)

>[!NOTE]
>
> Unter [Daten-Onboarding](people-based-destinations-prerequisites.md#data-onboarding) finden Sie häufig gestellte Fragen dazu, wie Sie Ihre Offline-Daten in Audience Manager für personenbasierte Ziele importieren sollten.

## Schritt 2: Abgleichen von DPUUIDs mit Hash-E-Mail-Adressen über die dateibasierte ID-Synchronisierung {#match-ids-emails}

>[!IMPORTANT]
>
> Dieser Schritt gilt nur für [&#x200B; oben &#x200B;](people-based-destinations-workflow-combined.md#configure-data-source-settings) Szenario 2. Wenn Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) bereits gehashte E-Mail-Adressen sind, fahren Sie mit [Schritt 3: Erstellen einer Profilzusammenführungsregel für die Segmentierung](people-based-destinations-workflow-combined.md#create-merge-rule) fort.

Nehmen wir an, Sie möchten Ihre bestehenden [DPUUIDs](../../reference/ids-in-aam.md) mit den Hash-E-Mail-Adressen aus der unten stehenden Tabelle (rechte Spalte) abgleichen und die Hash-E-Mail-Adressen in der neuen Datenquelle speichern, die Sie unter [Schritt 1 - Konfigurieren von Data Source Settings](people-based-destinations-workflow-combined.md#configure-data-source-settings) erstellt haben.

| DPUUID (CRM-ID) | E-Mail-Adresse | Hash-E-Mail-Adresse |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55E79200C1635B37AD31A378C39FEB12F120F116625093A19BC32FFF15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | FEEC5Debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Sie können bis zu 10 gehashte E-Mail-Adressen mit einer einzigen [DPUUID“ &#x200B;](../../reference/ids-in-aam.md). Trennen Sie dazu die gehashten E-Mail-Adressen in der Synchronisierungsdatei durch einen `<TAB>`.

In unserem Beispiel hätten Sie jetzt zwei Datenquellen.

| Datenquellen-ID | Datenquelleninhalte |
| -------------- | -------------------------- |
| 999999 | Vorhandene DPUUIDs (CRM-IDs) |
| 987654 | Hash-E-Mail-Adressen |

 

Ihre [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) würde die folgenden Inhalte haben:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Die [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) muss dieser Benennungsstruktur entsprechen:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Im obigen Beispiel würde der Dateiname wie folgt aussehen:
`c2c_id_999999_987654_1560431657.sync`

[Laden Sie hier die Beispieldatei &#x200B;](assets/c2c_id_999999_987654_1560431657.sync).

Nachdem Sie Ihre ID-Synchronisierungsdatei erstellt haben, müssen Sie sie in einen [!DNL Amazon S3] Bucket hochladen. Informationen zum Hochladen von ID-Synchronisierungsdateien finden Sie unter [Senden von Batch-Daten an Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Schritt 3: Erstellen einer Profilzusammenführungsregel für die Segmentierung {#create-merge-rule}

Der nächste Schritt besteht darin, eine neue Zusammenführungsregel zu erstellen, die Ihnen bei der Erstellung der Zielgruppensegmente hilft, die an Ihre personenbasierten Ziele gesendet werden sollen.

>[!IMPORTANT]
>
> Wenn Sie bereits eine Regel mit den Optionen [!UICONTROL Current Authenticated Profiles] oder [!UICONTROL Last Authenticated Profiles] definiert haben, können Sie zu [Schritt 4: Erstellen von Zielgruppensegmenten](people-based-destinations-workflow-combined.md#create-audience-segments) wechseln.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Klicken Sie auf **[!UICONTROL Add New Rule]**.
1. Geben Sie einen **[!UICONTROL Name]** und einen **[!UICONTROL Description]** für die Profilzusammenführungsregel ein.
1. Wählen Sie im Abschnitt **[!UICONTROL Profile Merge Rule Setup]** die Optionen **[!UICONTROL Current Authenticated Profiles]** oder **[!UICONTROL Last Authenticated Profiles]** aus.
1. Wählen Sie in der Liste **[!UICONTROL Cross-Device Profile Options]** die Datenquellen aus, für die Sie die Segmentierung ausführen möchten. Hierbei sollte es sich um die Datenquellen handeln, die Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) enthalten.

## Schritt 4: Erstellen von Zielgruppensegmenten {#create-audience-segments}

Verwenden Sie zum Erstellen neuer Zielgruppensegmente den [Segment Builder](../segments/segment-builder.md). Wenn Sie über vorhandene Zielgruppensegmente verfügen, die Sie an [!DNL People-Based Destinations] senden möchten, fahren Sie mit [Schritt 5: Konfigurieren der personenbasierten Platform-Authentifizierung](people-based-destinations-workflow-combined.md#configure-authentication) fort.

## Schritt 5: Konfigurieren der personenbasierten Platform-Authentifizierung {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Wenn Sie über eine zuvor konfigurierte Integration mit einer sozialen Plattform verfügen, sollte diese auf dieser Seite aufgeführt sein. Andernfalls ist die Seite leer.
   ![Personenbasierte Integration](assets/pbd-config.png)
1. Klicken Sie auf **[!UICONTROL Add Account]**.
1. Wählen Sie im Dropdown-Menü **[!UICONTROL People-Based Platform]** die Plattform aus, mit der Sie die Integration konfigurieren möchten.
   ![Personenbasierte Plattform](assets/pbd-add.png)
1. Klicken Sie auf **[!UICONTROL Confirm]** , um zur Authentifizierungsseite der ausgewählten Plattform weitergeleitet zu werden.
1. Nachdem Sie sich bei Ihrem Social-Media-Plattformkonto authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie Ihre zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das zu verwendende Advertiser-Konto aus und klicken Sie auf **[!UICONTROL Confirm]**.
1. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, die Sie darüber informiert, ob das Konto erfolgreich hinzugefügt wurde. Mit der Benachrichtigung können Sie auch eine Kontakt-E-Mail-Adresse hinzufügen, um Benachrichtigungen zu erhalten, wenn die Authentifizierung der Social-Media-Plattform bald abläuft.

>[!IMPORTANT]
>
>Audience Manager übernimmt die Integration mit Social-Media-Plattformen durch Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Weitere Informationen zum Verlängern der abgelaufenen Token finden Sie unter Erneuerung des Authentifizierungs-Tokens .

## Schritt 6: Erstellen eines personenbasierten Ziels {#create-destination}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** und klicken Sie auf **[!UICONTROL Create Destination]**.
1. Geben Sie im Abschnitt **[!UICONTROL Basic Information]** einen **[!UICONTROL Name]** und einen **[!UICONTROL Description]** für Ihre neue Datenquelle ein und verwenden Sie die folgenden Einstellungen:
   * **[!UICONTROL Category]**: integrierte Plattformen;
   * **[!UICONTROL Type]**: personenbezogen;
   * **[!UICONTROL Platform]**: Wählen Sie die personenbasierte Plattform aus, an die Sie Zielgruppensegmente senden möchten.
   * **[!UICONTROL Account]**: Wählen Sie das gewünschte Advertiser-Konto aus, das mit der ausgewählten Plattform verknüpft ist.
     ![create-destination](assets/pbd-create-destination.png)
1. Klicken Sie auf **[!UICONTROL Next]**.
1. Wählen Sie die **[!UICONTROL Data Export Labels]** aus, die Sie für dieses Ziel festlegen möchten.
1. Wählen Sie im Abschnitt **[!UICONTROL Configuration]** die Datenquelle aus, die Ihre gehashten Datenquellen enthält.
1. Wählen Sie im Abschnitt **[!UICONTROL Segment Mappings]** die Segmente aus, die Sie an dieses Ziel senden möchten. Hierbei handelt es sich um die Segmente, die Sie unter [Schritt 4: Erstellen von Zielgruppensegmenten) &#x200B;](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Speichern Sie das Ziel.
