---
description: 'Diese Seite enthält eine schrittweise Anleitung zum Erstellen von Zielgruppensegmenten aus reinen Offline-Kundendaten und zum Senden dieser Segmente an People-Based-Ziele.  '
seo-description: 'Diese Seite enthält eine schrittweise Anleitung zum Erstellen von Zielgruppensegmenten aus reinen Offline-Kundendaten und zum Senden dieser Segmente an People-Based-Ziele.  '
seo-title: Workflow B - Personalisierung auf Basis von Nur-Offline-Daten
solution: Audience Manager
title: Workflow B - Personalisierung auf Basis von Nur-Offline-Daten
translation-type: tm+mt
source-git-commit: ad9c077f538759e195a83d47e0ef36ccffa25c7e

---


# Workflow B - Personalisierung auf Basis von Nur-Offline-Daten {#workflow-b}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Diese Seite enthält eine schrittweise Anleitung zum Erstellen von Zielgruppensegmenten aus reinen Offline-Kundendaten und zum Senden dieser Segmente an People-Based-Ziele.

## Step 1 - Onboard Offline Traits {#step-1-onboard-traits}

Der erste Schritt beim Erstellen von Zielgruppensegmenten in diesem Szenario besteht darin, Ihre Offline-Kundendaten in Audience Manager zu importieren.

>[!IMPORTANT]
>
> Bevor Sie fortfahren, stellen Sie sicher, dass die Kundenaktivität, die Sie im Begriff sind zu berücksichtigen, bereits in Audience Manager mit den entsprechenden [integrierten Eigenschaften](../traits/trait-qualification-reference.md)definiert ist.

Regardless of whether your existing Audience Manager customer IDs (DPUUIDs) are hashed emails or not, you must perform the trait onboarding against the data source that contains your DPUUIDs.[](../../reference/ids-in-aam.md)[](../../reference/ids-in-aam.md)

### Beispiel 

You want to qualify the customer IDs from the table below for the corresponding onboarded trait IDs. Let's consider that your DPUUIDs are stored in a data source with the ID 999999, and your Audience Manager Partner ID is 123.[](../../reference/ids-in-aam.md)

| Customer ID (DPUUID) | Onboarded Trait ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />
To qualify the customer IDs in the example above for the corresponding onboarded traits, you must upload an [inbound data file](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) with the following contents:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

The file name would look like this: .
`ftp_dpm_999999_123_TIMESTAMP.sync.gz`
See Amazon S3 Name and File Size Requirements for Inbound Data Files for detailed information on the file name structure.[](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

## Step 2 - Configure Data Source Settings {#configure-data-source-settings}

Depending on whether your DPUUIDs are lowercase, hashed email addresses, you might need to configure the data source that will store the hashed email addresses.[](../../reference/ids-in-aam.md)

 

**Scenario 1: your DPUUIDs are already lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)**

In this case, you need to need to label the corresponding data source as such:

1. Go to  -&gt; .**[!UICONTROL Audience Data]****[!UICONTROL Data Sources]**
1. Find the data source that contains your DPUUIDs, and click it.[](../../reference/ids-in-aam.md)
1. Stellen Sie sicher, dass die Option deaktiviert **[!UICONTROL Cannot be tied to personally identifiable information]** ist.
1. Speichern Sie die Datenquelleneinstellungen.

 

**Szenario 2: Ihre[DPUUIDs](../../reference/ids-in-aam.md)sind nicht in Kleinbuchstaben, sondern Hash-E-Mail-Adressen.**

In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen, in der Ihre Hash-E-Mail-Adressen gespeichert werden. So geht das:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Data Sources]**, und klicken Sie auf **[!UICONTROL Add New]**.
1. Geben Sie ein **[!UICONTROL Name]** und **[!UICONTROL Description]** für Ihre neue Datenquelle ein.
1. Wählen Sie im **[!UICONTROL ID Type]** Dropdownmenü die Option **[!UICONTROL Cross Device]**.
1. Wählen Sie im **[!UICONTROL Data Source Settings]** Abschnitt die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die **[!UICONTROL Share associated cross-device IDs in people-based destinations]** Option.
1. Verwenden Sie das Dropdownmenü, um die **[!UICONTROL Emails(SHA256, lowercased)]** Bezeichnung für diese Datenquelle auszuwählen.
   >[!IMPORTANT]
   >
   >Diese Option bezeichnet die Datenquelle nur als mit diesem spezifischen Algorithmus Hash-Daten. In Audience Manager werden die Daten in diesem Schritt nicht zwischengespeichert. Vergewissern Sie sich, dass die E-Mail-Adressen, die Sie bei der Speicherung in dieser Datenquelle planen, bereits mit dem [!DNL SHA256] Algorithmus Hashing ausgeführt wurden. Andernfalls können Sie es nicht für [!DNL People-Based Destinations]die Anwendung verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Häufig gestellte Fragen dazu, wie Sie Ihre Offlinedaten in Audience Manager für People-Based-Ziele importieren sollten, finden Sie unter [DatenOnboarding](people-based-destinations-prerequisites.md#data-onboarding) .

## Schritt 3: Zuordnen von DPUUIDs zu Hash-E-Mail-Adressen über dateibasierte ID-Synchronisierung {#match-ids-emails}

>[!IMPORTANT]
>
> Dieser Schritt gilt nur für das oben beschriebene [Szenario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) . Wenn Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) bereits mit Hashing-E-Mail-Adressen versehen sind, fahren Sie mit [Schritt 4 - Eine Profilzusammenführungsregel für die Segmentierung](#create-profile-merge-rule)erstellen fort.

Angenommen, Sie möchten Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) aus dem Beispiel in Schritt 1 mit den Hash-E-Mail-Adressen aus der Tabelle unten (rechte Spalte) abgleichen und die Hash-E-Mail-Adressen in der neuen Datenquelle speichern, die Sie in [Schritt 2 - Datenquelleneinstellungen](#configure-data-source-settings)konfigurieren erstellt haben.

Zur Erinnerung haben Sie jetzt zwei Datenquellen:

| Datenquellen-ID | Datenquellinhalte |
| -------------- | -------------------------- |
| 999999 | Vorhandene DPUUIDs (CRM-IDs) |
| 987654 | Hash-E-Mail-Adressen |

| DPUUIDs (CRM-IDs) | E-Mail-Adresse | Hash-E-Mail-Adresse |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

In unserem Beispiel würde Ihre [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) folgenden Inhalt haben:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Die [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) muss der folgenden Benennungsstruktur entsprechen:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Im Beispiel oben würde der Dateiname wie folgt aussehen:
`c2c_id_999999_987654_1560431657.sync`

[Download example file here.](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)

Once you've created your ID synchronization file, you need to upload it to an  bucket. [!DNL Amazon S3] To learn how to upload ID synchronization files, see Send Batch Data to Audience Manager.[](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md)

## Step 4 - Create a Profile Merge Rule for Segmentation {#create-profile-merge-rule}

Der nächste Schritt ist die Erstellung einer neuen Zusammenführungsregel, mit der Sie die Zielgruppensegmente erstellen können, die an Ihre [!DNL People-Based Destinations]Benutzer gesendet werden.

1. Log in to your Audience Manager account and go to  -&gt; .**[!UICONTROL Audience Data]****[!UICONTROL Profile Merge Rules]**
2. Klicken [!UICONTROL Add New Rule].
3. Geben Sie eine Regel zum Zusammenführen des Profils ein **[!UICONTROL Name]** und **[!UICONTROL Description]**.
4. Wählen Sie im **[!UICONTROL Profile Merge Rule Setup]** Abschnitt die **[!UICONTROL All Cross-Device Profiles]** Regel aus der **[!UICONTROL Cross-Device Options]** Liste.
5. Wählen Sie in der **[!UICONTROL Cross-Device Profile Options]** Liste die Datenquelle aus, der Ihre Eigenschaften zugeordnet sind.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Schritt 5: Erstellen von Zielgruppensegmenten {#create-audience-segments}

Um neue Segmente aus reinen Offline-Daten zu erstellen, verwenden Sie den [Segmentaufbau](../segments/segment-builder.md) und stellen Sie sicher, dass Sie die neue Regel zum Profilzusammenführen verwenden, die Sie im vorherigen Schritt erstellt haben, wenn Sie das Segment erstellen.

## Schritt 6: Personalisierte Plattformauthentifizierung konfigurieren {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer sozialen Plattform haben, sollte diese auf dieser Seite aufgeführt werden. Andernfalls ist die Seite leer.
   ![people-based-integration](assets/pbd-config.png)
1. Klicken Sie auf **[!UICONTROL Add Account]**.
1. Verwenden Sie das **[!UICONTROL People-Based Platform]** Dropdownmenü, um die Plattform auszuwählen, mit der Sie die Integration konfigurieren möchten.
   ![people-based-platform](assets/pbd-add.png)
1. Klicken Sie auf **[!UICONTROL Confirm]** , um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
1. Nachdem Sie sich bei Ihrem Social-Plattform-Konto authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das gewünschte Advertiser-Konto aus und klicken Sie auf **[!UICONTROL Confirm]**.
1. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Sie darüber zu informieren, ob das Konto erfolgreich hinzugefügt wurde. Mit der Benachrichtigung können Sie auch eine E-Mail-Adresse hinzufügen, um Benachrichtigungen zu erhalten, wenn die Social-Plattform-Authentifizierung demnächst abläuft.

>[!IMPORTANT]
>
>Audience Manager verarbeitet die Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Weitere Informationen zur Verlängerung der abgelaufenen Token finden Sie unter Erneuerung des Authentifizierungstokens.

## Schritt 7: Erstellen eines benutzerbasierten Ziels {#create-destination}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** und klicken Sie auf **[!UICONTROL Create Destination]**.
1. Geben Sie im **[!UICONTROL Basic Information]** Abschnitt eine **[!UICONTROL Name]** und **[!UICONTROL Description]** für die neue Datenquelle ein und verwenden Sie die folgenden Einstellungen:
   * **[!UICONTROL Category]**: Integrierte Plattformen;
   * **[!UICONTROL Type]**: Volksansässige;
   * **[!UICONTROL Platform]**: Wählen Sie die personalbasierte Plattform aus, an die Sie Zielgruppensegmente senden möchten.
   * **[!UICONTROL Account]**: Wählen Sie das gewünschte Advertiser-Konto aus, das mit der ausgewählten Plattform verknüpft ist.
      ![create-destination](assets/pbd-create-destination.png)
1. Klicken Sie auf **[!UICONTROL Next]**.
1. Choose the  that you want to set for this destination.**[!UICONTROL Data Export Labels]**
1. Wählen Sie im **[!UICONTROL Configuration]** Abschnitt die Datenquelle aus, die Ihre Hash-Datenquellen enthält.
1. In the  section, select the segments that you want to send to this destination. **[!UICONTROL Segment Mappings]** Dies sind die Segmente, die Sie in [Schritt 5 - Zielgruppensegmente](people-based-destinations-workflow-offline.md#create-audience-segments)erstellen erstellt haben.
1. Speichern Sie das Ziel.
