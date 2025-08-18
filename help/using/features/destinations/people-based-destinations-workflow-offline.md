---
description: Auf dieser Seite finden Sie eine schrittweise Anleitung zum Erstellen von Zielgruppensegmenten aus Kundendaten, die nur offline sind, und zum Senden an personenbasierte Ziele.
seo-description: This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.
seo-title: Workflow B - Personalization Based on Offline-Only Data
solution: Audience Manager
title: Workflow B - Personalization basierend auf reinen Offline-Daten
feature: People-based Destinations
exl-id: d980de26-3133-4ae3-80c2-8c3bf2480bbd
source-git-commit: 87c3169083f0dc66490e6a8c808e16371f1d78c0
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 1%

---

# Workflow B - Personalization basierend auf reinen Offline-Daten {#workflow-b}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Verwendung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um Rechtsberatung zu erhalten.

Auf dieser Seite finden Sie eine schrittweise Anleitung zum Erstellen von Zielgruppensegmenten aus Kundendaten, die nur offline sind, und zum Senden an personenbasierte Ziele.

## Schritt 1: Onboarding von Offline-Eigenschaften {#step-1-onboard-traits}

Der erste Schritt beim Erstellen von Zielgruppensegmenten in diesem Szenario besteht darin, Ihre Offline-Kundendaten in Audience Manager zu importieren.

>[!IMPORTANT]
>
> Bevor Sie fortfahren, stellen Sie sicher, dass die Kundenaktivität, die Sie integrieren möchten, bereits in Audience Manager mit den entsprechenden [integrierten Eigenschaften](../traits/trait-and-segment-qualification-reference.md) definiert ist.

Unabhängig davon, ob es sich bei Ihren bestehenden Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) um Hash-E-Mails handelt oder nicht, müssen Sie das Onboarding der Eigenschaft mit der Datenquelle durchführen, die Ihre [DPUUIDs](../../reference/ids-in-aam.md) enthält.

### Beispiel

Sie möchten die Kunden-IDs aus der folgenden Tabelle für die entsprechenden integrierten Trait-IDs qualifizieren. Beachten wir, dass Ihre [DPUUIDs](../../reference/ids-in-aam.md) in einer Datenquelle mit der ID 999999 gespeichert sind und Ihre Audience Manager-Datenquellen-ID 123 ist.

| Kunden-ID (DPUUID) | Integrierte Eigenschafts-ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

Um die Kunden-IDs im obigen Beispiel für die entsprechenden integrierten Eigenschaften zu qualifizieren, müssen Sie eine [eingehende Datendatei](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) mit folgendem Inhalt hochladen:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

Der Dateiname würde wie folgt aussehen: `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Siehe [Anforderungen an Amazon S3-Namen und Dateigrößen für eingehende Datendateien](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) für detaillierte Informationen zur Dateinamenstruktur.

## Schritt 2: Konfigurieren der Einstellungen für Data Source {#configure-data-source-settings}

Je nachdem, ob Ihre [DPUUIDs](../../reference/ids-in-aam.md) E-Mail-Adressen in Kleinbuchstaben mit Hash vorliegen, müssen Sie möglicherweise die Datenquelle konfigurieren, in der die Hash-E-Mail-Adressen gespeichert werden.

 

**Szenario 1: Ihre [DPUUIDs](../../reference/ids-in-aam.md) werden bereits in Kleinbuchstaben geschrieben und enthalten Hash-E-Mail-Adressen.**

In diesem Fall müssen Sie die entsprechende Datenquelle als solche kennzeichnen:

1. Gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Suchen Sie die Datenquelle, die Ihre [DPUUIDs](../../reference/ids-in-aam.md) enthält, und klicken Sie darauf.
1. Stellen Sie sicher, dass die Option **[!UICONTROL Cannot be tied to personally identifiable information]** deaktiviert ist.
1. Speichern Sie die Datenquelleneinstellungen.

 

**Szenario 2: Ihre [DPUUIDs](../../reference/ids-in-aam.md) sind keine gehashten E-Mail-Adressen in Kleinbuchstaben.**

In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen, in der Ihre gehashten E-Mail-Adressen gespeichert werden. Gehen Sie wie folgt vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** und klicken Sie auf **[!UICONTROL Add New]**.
1. Geben Sie einen **[!UICONTROL Name]** und einen **[!UICONTROL Description]** für Ihre neue Datenquelle ein.
1. Wählen Sie im Dropdown-Menü **[!UICONTROL ID Type]** die Option **[!UICONTROL Cross Device]** aus.
1. Wählen Sie im Abschnitt **[!UICONTROL Data Source Settings]** die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Wählen Sie im Dropdown-Menü die **[!UICONTROL Emails(SHA256, lowercased)]** für diese Datenquelle aus.
   >[!IMPORTANT]
   >
   >Diese Option kennzeichnet die Datenquelle nur als mit Daten, die mit diesem bestimmten Algorithmus gehasht wurden. Audience Manager hasst die Daten in diesem Schritt nicht. Stellen Sie sicher, dass die E-Mail-Adressen, die Sie in dieser Datenquelle speichern möchten, bereits mit dem [!DNL SHA256]-Algorithmus gehasht wurden. Andernfalls können Sie es nicht für [!DNL People-Based Destinations] verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Unter [Daten-Onboarding](people-based-destinations-prerequisites.md#data-onboarding) finden Sie häufig gestellte Fragen dazu, wie Sie Ihre Offline-Daten in Audience Manager für personenbasierte Ziele importieren sollten.

Sehen Sie sich das folgende Video an, um ein Video-Tutorial zum Erstellen einer Datenquelle für [!UICONTROL People-Based Destinations] zu erhalten.

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Schritt 3: Abgleichen von DPUUIDs mit Hash-E-Mail-Adressen über die dateibasierte ID-Synchronisierung {#match-ids-emails}

>[!IMPORTANT]
>
> Dieser Schritt gilt nur für [ oben ](people-based-destinations-workflow-offline.md#configure-data-source-settings) Szenario 2. Wenn Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) bereits gehashte E-Mail-Adressen sind, fahren Sie mit [Schritt 4: Erstellen einer Profilzusammenführungsregel für die Segmentierung](#create-profile-merge-rule) fort.

Nehmen wir an, Sie möchten Ihre bestehenden [DPUUIDs](../../reference/ids-in-aam.md) aus dem Beispiel in Schritt 1 mit den Hash-E-Mail-Adressen aus der unten stehenden Tabelle (rechte Spalte) abgleichen und die Hash-E-Mail-Adressen in der neuen Datenquelle speichern, die Sie unter [Schritt 2 - Einstellungen für Data Source konfigurieren](#configure-data-source-settings) erstellt haben.

Zur Erinnerung: Sie hätten jetzt zwei Datenquellen:

| Datenquellen-ID | Datenquelleninhalte |
| -------------- | -------------------------- |
| 999999 | Vorhandene DPUUIDs (CRM-IDs) |
| 987654 | Hash-E-Mail-Adressen |

| DPUUIDs (CRM-IDs) | E-Mail-Adresse | Hash-E-Mail-Adresse |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55E79200C1635B37AD31A378C39FEB12F120F116625093A19BC32FFF15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | FEEC5Debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

In unserem Beispiel hätte Ihre [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) folgenden Inhalt:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Die [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) muss dieser Benennungsstruktur entsprechen:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Im obigen Beispiel würde der Dateiname wie folgt aussehen:
`c2c_id_999999_987654_1560431657.sync`

[Laden Sie hier die Beispieldatei ](assets/c2c_id_999999_987654_1560431657.sync).

Nachdem Sie Ihre ID-Synchronisierungsdatei erstellt haben, müssen Sie sie in einen [!DNL Amazon S3] Bucket hochladen. Informationen zum Hochladen von ID-Synchronisierungsdateien finden Sie unter [Senden von Batch-Daten an Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Schritt 4: Erstellen einer Profilzusammenführungsregel für die Segmentierung {#create-profile-merge-rule}

Der nächste Schritt besteht darin, eine neue Zusammenführungsregel zu erstellen, die Ihnen bei der Erstellung der Zielgruppensegmente hilft, die an Ihre [!DNL People-Based Destinations] gesendet werden sollen.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Klicken Sie auf [!UICONTROL Add New Rule].
3. Geben Sie einen **[!UICONTROL Name]** und einen **[!UICONTROL Description]** für die Profilzusammenführungsregel ein.
4. Wählen Sie im Abschnitt **[!UICONTROL Profile Merge Rule Setup]** die Regel **[!UICONTROL All Cross-Device Profiles]** aus der Liste **[!UICONTROL Cross-Device Options]** aus.
5. Wählen Sie in der Liste **[!UICONTROL Cross-Device Profile Options]** die Datenquelle aus, für die Ihre Eigenschaften integriert wurden.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Schritt 5: Erstellen von Zielgruppensegmenten {#create-audience-segments}

Um neue Segmente aus ausschließlich Offline-Daten zu erstellen, verwenden Sie [Segment Builder](../segments/segment-builder.md) und stellen Sie sicher, dass Sie beim Erstellen des Segments die neue Profilzusammenführungsregel verwenden, die Sie im vorherigen Schritt erstellt haben.

## Schritt 6: Konfigurieren der personenbasierten Platform-Authentifizierung {#configure-authentication}

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
>Audience Manager übernimmt die Integration mit Social-Media-Plattformen mithilfe von Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Weitere Informationen zum Verlängern der abgelaufenen Token finden Sie unter Erneuerung des Authentifizierungs-Tokens .

## Schritt 7: Erstellen eines personenbasierten Ziels {#create-destination}

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
1. Wählen Sie im Abschnitt **[!UICONTROL Segment Mappings]** die Segmente aus, die Sie an dieses Ziel senden möchten. Hierbei handelt es sich um die Segmente, die Sie unter [Schritt 5: Erstellen von Zielgruppensegmenten](people-based-destinations-workflow-offline.md#create-audience-segments) erstellt haben.
1. Speichern Sie das Ziel.
