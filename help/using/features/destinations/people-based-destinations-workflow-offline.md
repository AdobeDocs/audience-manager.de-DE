---
description: 'Diese Seite enthält eine schrittweise Anleitung zum Erstellen von Audiencen-Segmenten aus reinen Offline-Kundendaten und zum Senden dieser Segmente an People-Based-Ziele.  '
seo-description: 'Diese Seite enthält eine schrittweise Anleitung zum Erstellen von Audiencen-Segmenten aus reinen Offline-Kundendaten und zum Senden dieser Segmente an People-Based-Ziele.  '
seo-title: Workflow B – Personalisierung basierend auf reinen Offline-Daten
solution: Audience Manager
title: Workflow B – Personalisierung basierend auf reinen Offline-Daten
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 6%

---


# Workflow B – Personalisierung basierend auf reinen Offline-Daten {#workflow-b}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Diese Seite enthält eine schrittweise Anleitung zum Erstellen von Audiencen-Segmenten aus reinen Offline-Kundendaten und zum Senden dieser Segmente an People-Based-Ziele.

## Schritt 1: Integrierte Offline-Eigenschaften {#step-1-onboard-traits}

Der erste Schritt beim Erstellen von Audiencen-Segmenten in diesem Szenario besteht darin, Ihre Offline-Kundendaten in den Audience Manager zu bringen.

>[!IMPORTANT]
>
> Bevor Sie fortfahren, stellen Sie sicher, dass die Aktivität des Kunden, die Sie im Begriff sind zu berücksichtigen, bereits in Audience Manager mit den entsprechenden [Onboarded-Eigenschaften](../traits/trait-and-segment-qualification-reference.md) definiert ist.

Unabhängig davon, ob es sich bei Ihren bestehenden Audience Manager-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) um Hash-E-Mails handelt oder nicht, müssen Sie die Eigenschaft für die Datenquelle, die Ihre [DPUUIDs](../../reference/ids-in-aam.md) enthält, aktivieren.

### Beispiel

Sie möchten die Kunden-IDs aus der unten stehenden Tabelle für die entsprechenden IDs für nicht integrierte Eigenschaften qualifizieren. Denken wir daran, dass Ihre [DPUUIDs](../../reference/ids-in-aam.md) in einer Datenquelle mit der ID 9999999 gespeichert sind und Ihre Audience Manager-Partner-ID 123 beträgt.

| Kunden-ID (DPUUID) | Integrierte Eigenschaften-ID |
| -------------------------------------- | ------------------- |
| 68079982765673198504052656074456196039 | 12345, 23456 |
| 67412682083411995725538770443620307584 | 45678 |
| 89159024796760343733111707646026765593 | 11223, 93342, 27341 |

<br />

Um die Kunden-IDs im obigen Beispiel für die entsprechenden Onboarded-Eigenschaften zu qualifizieren, müssen Sie eine [Inbound-Datendatei](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) mit folgendem Inhalt hochladen:

```
68079982765673198504052656074456196039<TAB>d_sid=12345,d_sid=23456
67412682083411995725538770443620307584<TAB>d_sid=45678
89159024796760343733111707646026765593<TAB>d_sid=11223,d_sid=93342,d_sid=27341
```

Der Dateiname würde wie folgt aussehen: `ftp_dpm_999999_123_TIMESTAMP.sync.gz`.
Detaillierte Informationen zur Dateinamenstruktur finden Sie unter [Amazon S3 Name and File Size requirements for Inbound Data Files](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md).

## Schritt 2: Konfigurieren der Datenquelleneinstellungen {#configure-data-source-settings}

Je nachdem, ob Ihre [DPUUIDs](../../reference/ids-in-aam.md) in Kleinbuchstaben und Hash-E-Mail-Adressen vorliegen, müssen Sie möglicherweise die Datenquelle konfigurieren, in der die Hash-E-Mail-Adressen gespeichert werden.

 

**Szenario 1: Ihre  [](../../reference/ids-in-aam.md) DPUUIDs sind bereits in Kleinbuchstaben, mit Hash-E-Mail-Adressen.**

In diesem Fall müssen Sie die entsprechende Datenquelle als solche kennzeichnen:

1. Gehen Sie zu **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**.
1. Suchen Sie die Datenquelle, die Ihre [DPUUIDs](../../reference/ids-in-aam.md) enthält, und klicken Sie darauf.
1. Stellen Sie sicher, dass die Option **[!UICONTROL Cannot be tied to personally identifiable information]** deaktiviert ist.
1. Speichern Sie die Datenquelleneinstellungen.

 

**Szenario 2: Ihre  [](../../reference/ids-in-aam.md) DPUUIDsare nicht in Kleinbuchstaben, Hash-E-Mail-Adressen.**

In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen, in der Ihre Hash-E-Mail-Adressen gespeichert werden. So geht das:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** und klicken Sie auf **[!UICONTROL Add New]**.
1. Geben Sie für Ihre neue Datenquelle **[!UICONTROL Name]** und **[!UICONTROL Description]** ein.
1. Wählen Sie im Dropdownmenü **[!UICONTROL ID Type]** **[!UICONTROL Cross Device]**.
1. Wählen Sie im Abschnitt **[!UICONTROL Data Source Settings]** sowohl die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Verwenden Sie das Dropdown-Menü, um die Beschriftung **[!UICONTROL Emails(SHA256, lowercased)]** für diese Datenquelle auszuwählen.
   >[!IMPORTANT]
   >
   >Diese Option bezeichnet die Datenquelle nur als mit diesem spezifischen Algorithmus Hash-Daten. In diesem Schritt werden die Daten von Audience Manager nicht gehackt. Vergewissern Sie sich, dass die E-Mail-Adressen, die Sie in dieser Datenquelle speichern möchten, bereits mit dem Algorithmus [!DNL SHA256] Hashing arbeiten. Andernfalls können Sie es nicht für [!DNL People-Based Destinations] verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Häufig gestellte Fragen dazu, wie Sie Ihre Offline-Daten in Audience Manager für People-Based Destination integrieren sollten, finden Sie unter [Data Onboarding](people-based-destinations-prerequisites.md#data-onboarding).

Sehen Sie sich das folgende Video an, um einen Video-Lehrgang zum Erstellen einer Datenquelle für [!UICONTROL People-Based Destinations] anzuzeigen.

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Schritt 3: Abgleichen von DPUUIDs mit Hash-E-Mail-Adressen über dateibasierte ID-Synchronisierung {#match-ids-emails}

>[!IMPORTANT]
>
> Dieser Schritt gilt nur für das oben beschriebene [Szenario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings). Wenn Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) bereits Hash-E-Mail-Adressen sind, gehen Sie zu [Schritt 4 - Eine Profil-Merge-Regel für die Segmentierung](#create-profile-merge-rule) erstellen.

Angenommen, Sie möchten Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) aus dem Beispiel in Schritt 1 mit den Hash-E-Mail-Adressen aus der Tabelle unten (rechte Spalte) abgleichen und die Hash-E-Mail-Adressen in der neuen Datenquelle speichern, die Sie unter [Schritt 2 - Konfigurieren der Datenquelleneinstellungen](#configure-data-source-settings) erstellt haben.

Zur Erinnerung haben Sie jetzt zwei Datenquellen:

| Datenquellen-ID | Datenquelleninhalte |
| -------------- | -------------------------- |
| 999999 | Vorhandene DPUUIDs (CRM-IDs) |
| 987654 | Hash-E-Mail-Adressen |

| DPUUIDs (CRM-IDs) | E-Mail-Adresse | Hash-E-Mail-Adresse |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

In unserem Beispiel würde Ihre [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) den folgenden Inhalt haben:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Die [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) muss der folgenden Benennungsstruktur entsprechen:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Im Beispiel oben würde der Dateiname wie folgt aussehen:
`c2c_id_999999_987654_1560431657.sync`

[Beispieldatei hier](assets/c2c_id_999999_987654_1560431657.sync) herunterladen.

Nachdem Sie die ID-Synchronisierungsdatei erstellt haben, müssen Sie sie in einen [!DNL Amazon S3]-Behälter hochladen. Informationen zum Hochladen von ID-Synchronisierungsdateien finden Sie unter [Stapeldaten an Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) senden.

## Schritt 4: Erstellen einer Profil Merge Rule for Segmentation {#create-profile-merge-rule}

Im nächsten Schritt erstellen Sie eine neue Zusammenführungsregel, die Ihnen hilft, die an Ihr [!DNL People-Based Destinations] zu sendenden Audiencen zu erstellen.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Klicken [!UICONTROL Add New Rule].
3. Geben Sie eine Profil Mergeregel **[!UICONTROL Name]** und **[!UICONTROL Description]** ein.
4. Wählen Sie im Abschnitt **[!UICONTROL Profile Merge Rule Setup]** die **[!UICONTROL All Cross-Device Profiles]**-Regel aus der **[!UICONTROL Cross-Device Options]**-Liste.
5. Wählen Sie in der Liste **[!UICONTROL Cross-Device Profile Options]** die Datenquelle aus, der Ihre Eigenschaften zugeordnet sind.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Schritt 5: Erstellen von Audiencen-Segmenten {#create-audience-segments}

Um neue Segmente aus reinen Offline-Daten zu erstellen, verwenden Sie den [Segmentaufbau](../segments/segment-builder.md) und stellen Sie sicher, dass Sie die neue Segmentzusammenführungsregel verwenden, die Sie im vorherigen Profil erstellt haben, wenn Sie das Segment erstellen.

## Schritt 6: Personenbasierte Plattformauthentifizierung konfigurieren {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer sozialen Plattform haben, sollte diese auf dieser Seite aufgeführt werden. Andernfalls ist die Seite leer.
   ![people-based-integration](assets/pbd-config.png)
1. Klicken **[!UICONTROL Add Account]**.
1. Verwenden Sie das Dropdownmenü **[!UICONTROL People-Based Platform]**, um die Plattform auszuwählen, mit der Sie die Integration konfigurieren möchten.
   ![people-based-platform](assets/pbd-add.png)
1. Klicken Sie auf **[!UICONTROL Confirm]**, um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
1. Nachdem Sie sich bei Ihrem Social-Plattform-Konto authentifiziert haben, werden Sie an den Audience Manager weitergeleitet, wo Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das gewünschte Advertiser-Konto aus und klicken Sie auf **[!UICONTROL Confirm]**.
1. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Sie darüber zu informieren, ob das Konto erfolgreich hinzugefügt wurde. Mit der Benachrichtigung können Sie auch eine E-Mail-Adresse hinzufügen, um Benachrichtigungen zu erhalten, wenn die Social-Plattform-Authentifizierung demnächst abläuft.

>[!IMPORTANT]
>
>Audience Manager verarbeitet die Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Weitere Informationen zur Verlängerung der abgelaufenen Token finden Sie unter Erneuerung des Authentifizierungstokens.

## Schritt 7 - Erstellen eines benutzerbasierten Ziels {#create-destination}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** und klicken Sie auf **[!UICONTROL Create Destination]**.
1. Geben Sie im Abschnitt **[!UICONTROL Basic Information]** für Ihre neue Datenquelle **[!UICONTROL Name]** und **[!UICONTROL Description]** ein und verwenden Sie die folgenden Einstellungen:
   * **[!UICONTROL Category]**: Integrierte Plattformen;
   * **[!UICONTROL Type]**: Volksansässige;
   * **[!UICONTROL Platform]**: Wählen Sie die benutzerbasierte Plattform aus, an die Sie Audiencen-Segmente senden möchten.
   * **[!UICONTROL Account]**: Wählen Sie das gewünschte Advertiser-Konto aus, das mit der ausgewählten Plattform verknüpft ist.
      ![create-destination](assets/pbd-create-destination.png)
1. Klicken **[!UICONTROL Next]**.
1. Wählen Sie die **[!UICONTROL Data Export Labels]** aus, die Sie für dieses Ziel festlegen möchten.
1. Wählen Sie im Abschnitt **[!UICONTROL Configuration]** die Datenquelle aus, die Ihre Hash-Datenquellen enthält.
1. Wählen Sie im Abschnitt **[!UICONTROL Segment Mappings]** die Segmente aus, die Sie an dieses Ziel senden möchten. Dies sind die Segmente, die Sie unter [Schritt 5 - Erstellen von Audiencen-Segmenten](people-based-destinations-workflow-offline.md#create-audience-segments) erstellt haben.
1. Speichern Sie das Ziel.
