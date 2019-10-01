---
description: 'Diese Seite enthält eine schrittweise Anleitung zum Erstellen von Zielgruppensegmenten aus reinen Offline-Kundendaten und zum Senden dieser Segmente an People-Based-Ziele.  '
seo-description: 'Diese Seite enthält eine schrittweise Anleitung zum Erstellen von Zielgruppensegmenten aus reinen Offline-Kundendaten und zum Senden dieser Segmente an People-Based-Ziele.  '
seo-title: Workflow B - Personalisierung auf Basis von Nur-Offline-Daten
solution: Audience Manager
title: Workflow B - Personalisierung auf Basis von Nur-Offline-Daten
translation-type: tm+mt
source-git-commit: fb5d9eff3573048d3e8a570b342a97bce3cd8da0

---


# Workflow B - Personalisierung auf Basis von Nur-Offline-Daten {#workflow-b}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Please consult your own legal counsel for legal guidance.

This page includes step-by-step guidance on how to build audience segments from offline-only customer data, and send them to People-Based Destinations.

## Schritt 1: Integrierte Offline-Eigenschaften {#step-1-onboard-traits}

The first step creating audience segments in this scenario is to bring your offline customer data into Audience Manager.

>[!IMPORTANT]
>
> Bevor Sie fortfahren, stellen Sie sicher, dass die Kundenaktivität, die Sie im Begriff sind zu berücksichtigen, bereits in Audience Manager mit den entsprechenden [integrierten Eigenschaften](../traits/trait-qualification-reference.md)definiert ist.

Unabhängig davon, ob es sich bei Ihren bestehenden Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) um Hash-E-Mails handelt oder nicht, müssen Sie die Eigenschaft für die Datenquelle, die Ihre [DPUUIDs](../../reference/ids-in-aam.md)enthält, aktivieren.

### Beispiel 

Sie möchten die Kunden-IDs aus der unten stehenden Tabelle für die entsprechenden IDs für nicht integrierte Eigenschaften qualifizieren. Denken wir daran, dass Ihre [DPUUIDs](../../reference/ids-in-aam.md) in einer Datenquelle mit der ID 999999 gespeichert sind und Ihre Audience Manager Partner-ID 123 beträgt.

| Kunden-ID (DPUUID) | Integrierte Eigenschaften-ID |
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

Der Dateiname würde wie folgt aussehen: `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Detaillierte Informationen zur Dateistruktur finden Sie unter [Amazon S3-Anforderungen an Name und Dateigröße für Inbound-Datendateien](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) .

## Schritt 2: Konfigurieren der Datenquelleneinstellungen {#configure-data-source-settings}

Depending on whether your DPUUIDs are lowercase, hashed email addresses, you might need to configure the data source that will store the hashed email addresses.[](../../reference/ids-in-aam.md)

 

**Scenario 1: your DPUUIDs are already lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)**

In this case, you need to need to label the corresponding data source as such:

1. Go to  -&gt; .**[!UICONTROL Audience Data]****[!UICONTROL Data Sources]**
1. Suchen Sie die Datenquelle, die Ihre [DPUUIDs](../../reference/ids-in-aam.md)enthält, und klicken Sie darauf.
1. Stellen Sie sicher, dass die Option deaktiviert **[!UICONTROL Cannot be tied to personally identifiable information]** ist.
1. Speichern Sie die Datenquelleneinstellungen.

 

**Scenario 2: your DPUUIDs are not lowercase, hashed email addresses.[](../../reference/ids-in-aam.md)**

In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen, in der Ihre Hash-E-Mail-Adressen gespeichert werden. So geht das:

1. Log in to your Audience Manager account and go to  -&gt; , and click .**[!UICONTROL Audience Data]****[!UICONTROL Data Sources]****[!UICONTROL Add New]**
1. Geben Sie ein **[!UICONTROL Name]** und **[!UICONTROL Description]** für Ihre neue Datenquelle ein.
1. Wählen Sie im **[!UICONTROL ID Type]** Dropdownmenü die Option **[!UICONTROL Cross Device]**.
1. Wählen Sie im **[!UICONTROL Data Source Settings]** Abschnitt die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die **[!UICONTROL Share associated cross-device IDs in people-based destinations]** Option.
1. Verwenden Sie das Dropdownmenü, um die **[!UICONTROL Emails(SHA256, lowercased)]** Bezeichnung für diese Datenquelle auszuwählen.
   >[!IMPORTANT]
   >
   >This option only labels the data source as containing data hashed with that specific algorithm. In Audience Manager werden die Daten in diesem Schritt nicht zwischengespeichert. Vergewissern Sie sich, dass die E-Mail-Adressen, die Sie bei der Speicherung in dieser Datenquelle planen, bereits mit dem [!DNL SHA256] Algorithmus Hashing ausgeführt wurden. Otherwise, you won't be able to use it for .[!DNL People-Based Destinations]

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Häufig gestellte Fragen dazu, wie Sie Ihre Offlinedaten in Audience Manager für People-Based-Ziele importieren sollten, finden Sie unter [DatenOnboarding](people-based-destinations-prerequisites.md#data-onboarding) .

## Step 3 - Match DPUUIDs to Hashed Email Addresses via File-Based ID Synchronization {#match-ids-emails}

>[!IMPORTANT]
>
> Dieser Schritt gilt nur für das oben beschriebene [Szenario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings) . Wenn Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) bereits mit Hashing-E-Mail-Adressen versehen sind, fahren Sie mit [Schritt 4 - Eine Profilzusammenführungsregel für die Segmentierung](#create-profile-merge-rule)erstellen fort.

Angenommen, Sie möchten Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) aus dem Beispiel in Schritt 1 mit den Hash-E-Mail-Adressen aus der Tabelle unten (rechte Spalte) abgleichen und die Hash-E-Mail-Adressen in der neuen Datenquelle speichern, die Sie in [Schritt 2 - Datenquelleneinstellungen](#configure-data-source-settings)konfigurieren erstellt haben.

Zur Erinnerung haben Sie jetzt zwei Datenquellen:

| Data source ID | Datenquellinhalte |
| -------------- | -------------------------- |
| 999999 | Existing DPUUIDs (CRM IDs) |
| 987654 | Hashed email addresses |

| DPUUIDs (CRM IDs) | E-Mail-Adresse | Hash-E-Mail-Adresse |
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

[Beispieldatei hier](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)herunterladen.

Nachdem Sie die ID-Synchronisierungsdatei erstellt haben, müssen Sie sie in einen [!DNL Amazon S3] Behälter hochladen. Informationen zum Hochladen von ID-Synchronisierungsdateien finden Sie unter Stapeldaten an Audience Manager [senden](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Schritt 4: Erstellen einer Regel zur Profilzusammenführung für die Segmentierung {#create-profile-merge-rule}

The next step is creating a new merge rule that will help you create the audience segments to send to your .[!DNL People-Based Destinations]

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Klicken [!UICONTROL Add New Rule].
3. Enter a profile merge rule  and .**[!UICONTROL Name]****[!UICONTROL Description]**
4. In the  section, select the  rule from the  list.**[!UICONTROL Profile Merge Rule Setup]****[!UICONTROL All Cross-Device Profiles]****[!UICONTROL Cross-Device Options]**
5. Wählen Sie in der **[!UICONTROL Cross-Device Profile Options]** Liste die Datenquelle aus, der Ihre Eigenschaften zugeordnet sind.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Schritt 5: Erstellen von Zielgruppensegmenten {#create-audience-segments}

To create new segments from offline-only data, use the Segment Builder and make sure you use the new profile merge rule that you created in the previous step when creating the segment.[](../segments/segment-builder.md)

## Step 6 - Configure People-Based Platform Authentication {#configure-authentication}

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
>Ein Audience Manager verarbeitet die Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Weitere Informationen zur Verlängerung der abgelaufenen Token finden Sie unter Erneuerung des Authentifizierungstokens.

## Schritt 7: Erstellen eines benutzerbasierten Ziels {#create-destination}

1. Log in to your Audience Manager account, go to  &gt; , and click .**[!UICONTROL Audience Data]****[!UICONTROL Destinations]****[!UICONTROL Create Destination]**
1. Geben Sie im **[!UICONTROL Basic Information]** Abschnitt eine **[!UICONTROL Name]** und **[!UICONTROL Description]** für die neue Datenquelle ein und verwenden Sie die folgenden Einstellungen:
   * **[!UICONTROL Category]**: Integrierte Plattformen;
   * **[!UICONTROL Type]**: Volksansässige;
   * **[!UICONTROL Platform]**: Wählen Sie die personalbasierte Plattform aus, an die Sie Zielgruppensegmente senden möchten.
   * **[!UICONTROL Account]**: Wählen Sie das gewünschte Advertiser-Konto aus, das mit der ausgewählten Plattform verknüpft ist.
      ![create-destination](assets/pbd-create-destination.png)
1. Klicken Sie auf **[!UICONTROL Next]**.
1. Choose the  that you want to set for this destination.**[!UICONTROL Data Export Labels]**
1. Wählen Sie im **[!UICONTROL Configuration]** Abschnitt die Datenquelle aus, die Ihre Hash-Datenquellen enthält.
1. Wählen Sie im **[!UICONTROL Segment Mappings]** Abschnitt die Segmente aus, die Sie an dieses Ziel senden möchten. Dies sind die Segmente, die Sie in [Schritt 5 - Zielgruppensegmente](people-based-destinations-workflow-offline.md#create-audience-segments)erstellen erstellt haben.
1. Speichern Sie das Ziel.
