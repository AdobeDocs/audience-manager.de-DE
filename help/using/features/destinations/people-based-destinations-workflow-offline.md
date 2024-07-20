---
description: Diese Seite enthält eine schrittweise Anleitung zum Erstellen von Zielgruppensegmenten aus reinen Offline-Kundendaten und zum Senden dieser Segmente an People-basierte Ziele.
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
>Dieser Artikel enthält die Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um rechtliche Hinweise zu erhalten.

Diese Seite enthält eine schrittweise Anleitung zum Erstellen von Zielgruppensegmenten aus reinen Offline-Kundendaten und zum Senden dieser Segmente an People-basierte Ziele.

## Schritt 1: Integrierte Offline-Eigenschaften {#step-1-onboard-traits}

Der erste Schritt beim Erstellen von Zielgruppensegmenten in diesem Szenario besteht darin, Ihre Offline-Kundendaten in den Audience Manager zu bringen.

>[!IMPORTANT]
>
> Bevor Sie fortfahren, stellen Sie sicher, dass die Kundenaktivität, die Sie im Begriff sind zu integrieren, bereits im Audience Manager mit den entsprechenden [integrierten Eigenschaften](../traits/trait-and-segment-qualification-reference.md) definiert ist.

Unabhängig davon, ob es sich bei Ihren bestehenden Audience Manager-Kunden-IDs ([DPUUIDs](../../reference/ids-in-aam.md)) um Hash-E-Mails handelt oder nicht, müssen Sie die Eigenschaft für die Datenquelle, die Ihre [DPUUIDs](../../reference/ids-in-aam.md) enthält, Onboarding durchführen.

### Beispiel

Sie möchten die Kunden-IDs aus der folgenden Tabelle für die entsprechenden integrierten Eigenschaften-IDs qualifizieren. Nehmen wir an, Ihre [DPUUIDs](../../reference/ids-in-aam.md) sind in einer Datenquelle mit der ID 999999 gespeichert, und Ihre Audience Manager-Datenquelle-ID ist 123.

| Kunden-ID (DPUUID) | Integrierte Eigenschaften-ID |
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
Detaillierte Informationen zur Dateinamenstruktur finden Sie unter [Anforderungen an Namen und Dateigrößen der über Amazon S3 eingehenden Datendateien](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) .

## Schritt 2: Konfigurieren der Data Source-Einstellungen {#configure-data-source-settings}

Je nachdem, ob Ihre [DPUUIDs](../../reference/ids-in-aam.md) in Kleinbuchstaben und Hash-E-Mail-Adressen enthalten, müssen Sie möglicherweise die Datenquelle konfigurieren, in der die Hash-E-Mail-Adressen gespeichert werden.

 

**Szenario 1: Ihre [DPUUIDs](../../reference/ids-in-aam.md) sind bereits in Kleinbuchstaben geschrieben und Hash-E-Mail-Adressen**.

In diesem Fall müssen Sie die entsprechende Datenquelle als solche beschriften:

1. Gehen Sie zu **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**.
1. Suchen Sie die Datenquelle, die Ihre [DPUUIDs](../../reference/ids-in-aam.md) enthält, und klicken Sie darauf.
1. Stellen Sie sicher, dass die Option **[!UICONTROL Cannot be tied to personally identifiable information]** deaktiviert ist.
1. Speichern Sie die Datenquelleneinstellungen.

 

**Szenario 2: Ihre [DPUUIDs](../../reference/ids-in-aam.md) sind keine E-Mail-Adressen mit Hashing in Kleinbuchstaben.**

In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen, in der Ihre Hash-E-Mail-Adressen gespeichert werden. Gehen Sie dazu folgendermaßen vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu &quot;**[!UICONTROL Audience Data]**&quot;> &quot;**[!UICONTROL Data Sources]**&quot;und klicken Sie auf &quot;**[!UICONTROL Add New]**&quot;.
1. Geben Sie für Ihre neue Datenquelle **[!UICONTROL Name]** und **[!UICONTROL Description]** ein.
1. Wählen Sie im Dropdownmenü **[!UICONTROL ID Type]** die Option **[!UICONTROL Cross Device]** aus.
1. Wählen Sie im Abschnitt **[!UICONTROL Data Source Settings]** sowohl die Optionen **[!UICONTROL Inbound]** als auch **[!UICONTROL Outbound]** aus und aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Verwenden Sie das Dropdown-Menü, um die Bezeichnung **[!UICONTROL Emails(SHA256, lowercased)]** für diese Datenquelle auszuwählen.
   >[!IMPORTANT]
   >
   >Diese Option bezeichnet die Datenquelle nur als die mit diesem spezifischen Algorithmus gehashten Daten. In diesem Schritt werden die Daten von Audience Manager nicht gehasht. Stellen Sie sicher, dass die E-Mail-Adressen, die Sie in dieser Datenquelle speichern möchten, bereits mit dem Algorithmus [!DNL SHA256] gehasht sind. Andernfalls können Sie es nicht für [!DNL People-Based Destinations] verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Unter [Datenintegration](people-based-destinations-prerequisites.md#data-onboarding) finden Sie häufig gestellte Fragen dazu, wie Sie Ihre Offline-Daten in den Audience Manager für personenbasierte Ziele integrieren sollten.

Sehen Sie sich das Video unten an, um ein Video-Tutorial zum Erstellen einer Datenquelle für [!UICONTROL People-Based Destinations] zu erhalten.

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Schritt 3: Abgleichen von DPUUIDs mit Hash-E-Mail-Adressen über dateibasierte ID-Synchronisierung {#match-ids-emails}

>[!IMPORTANT]
>
> Dieser Schritt gilt nur für das oben beschriebene [Szenario 2](people-based-destinations-workflow-offline.md#configure-data-source-settings). Wenn Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) bereits Hash-E-Mail-Adressen sind, gehen Sie zu [Schritt 4 - Erstellen einer Profilzusammenführungsrichtlinie für die Segmentierung](#create-profile-merge-rule).

Angenommen, Sie möchten Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) aus dem Beispiel in Schritt 1 mit den Hash-E-Mail-Adressen aus der unten stehenden Tabelle (rechte Spalte) abgleichen und die Hash-E-Mail-Adressen in der neuen Datenquelle speichern, die Sie anhand der Anweisungen unter [Schritt 2 - Source-Einstellungen konfigurieren](#configure-data-source-settings) erstellt haben.

Zur Erinnerung: Sie verfügen jetzt über zwei Datenquellen:

| Datenquellen-ID | Datenquelleninhalte |
| -------------- | -------------------------- |
| 999999 | Vorhandene DPUUIDs (CRM-IDs) |
| 987654 | Hash-E-Mail-Adressen |

| DPUUIDs (CRM-IDs) | E-Mail-Adresse | Hash-E-Mail-Adresse |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f11625093a19bc32fff15041 149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

In unserem Beispiel würde Ihre [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) den folgenden Inhalt haben:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Die [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) muss der folgenden Namensstruktur entsprechen:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Im obigen Beispiel würde der Dateiname wie folgt aussehen:
`c2c_id_999999_987654_1560431657.sync`

[Laden Sie die Beispieldatei hier herunter](assets/c2c_id_999999_987654_1560431657.sync).

Nachdem Sie Ihre ID-Synchronisierungsdatei erstellt haben, müssen Sie sie in einen [!DNL Amazon S3] -Behälter hochladen. Informationen zum Hochladen von ID-Synchronisierungsdateien finden Sie unter [Batch-Daten an Audience Manager senden](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Schritt 4: Erstellen einer Profilzusammenführungsrichtlinie für die Segmentierung {#create-profile-merge-rule}

Der nächste Schritt besteht darin, eine neue Zusammenführungsregel zu erstellen, mit der Sie die Zielgruppensegmente erstellen können, die an Ihre [!DNL People-Based Destinations] gesendet werden.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Klicken Sie auf [!UICONTROL Add New Rule].
3. Geben Sie eine Profilzusammenführungsregel **[!UICONTROL Name]** und **[!UICONTROL Description]** ein.
4. Wählen Sie im Abschnitt **[!UICONTROL Profile Merge Rule Setup]** die Regel **[!UICONTROL All Cross-Device Profiles]** aus der Liste **[!UICONTROL Cross-Device Options]** aus.
5. Wählen Sie in der Liste **[!UICONTROL Cross-Device Profile Options]** die Datenquelle aus, an der Ihre Eigenschaften integriert sind.
   ![merge-rule-setup](assets/pbd-pmr.png)

## Schritt 5: Erstellen von Zielgruppensegmenten {#create-audience-segments}

Um neue Segmente aus reinen Offline-Daten zu erstellen, verwenden Sie den [Segment Builder](../segments/segment-builder.md) und stellen Sie sicher, dass Sie die neue Profilzusammenführungsregel verwenden, die Sie im vorherigen Schritt beim Erstellen des Segments erstellt haben.

## Schritt 6: Konfigurieren der personenbasierten Plattformauthentifizierung {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Wenn Sie bereits eine Integration mit einer sozialen Plattform konfiguriert haben, sollte diese auf dieser Seite aufgeführt sein. Andernfalls ist die Seite leer.
   ![People-based-integration](assets/pbd-config.png)
1. Klicken Sie auf **[!UICONTROL Add Account]**.
1. Wählen Sie im Dropdown-Menü **[!UICONTROL People-Based Platform]** die Plattform aus, mit der Sie die Integration konfigurieren möchten.
   ![personenbasierte Plattform](assets/pbd-add.png)
1. Klicken Sie auf **[!UICONTROL Confirm]** , um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
1. Nachdem Sie sich bei Ihrem Social-Plattform-Konto authentifiziert haben, werden Sie zu dem Audience Manager weitergeleitet, in dem Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das Advertiser-Konto aus, das Sie verwenden möchten, und klicken Sie auf **[!UICONTROL Confirm]**.
1. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Sie darüber zu informieren, ob das Konto erfolgreich hinzugefügt wurde. Mit der Benachrichtigung können Sie auch eine Kontakt-E-Mail-Adresse hinzufügen, um Benachrichtigungen zu erhalten, wenn die Authentifizierung der sozialen Plattform bald abläuft.

>[!IMPORTANT]
>
>Audience Manager verarbeitet die Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Weitere Informationen zur Verlängerung der abgelaufenen Token finden Sie unter Erneuerung des Authentifizierungstokens .

## Schritt 7: Erstellen eines personenbasierten Ziels {#create-destination}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** und klicken Sie auf **[!UICONTROL Create Destination]**.
1. Geben Sie im Abschnitt **[!UICONTROL Basic Information]** einen **[!UICONTROL Name]** und einen **[!UICONTROL Description]** für die neue Datenquelle ein und verwenden Sie die folgenden Einstellungen:
   * **[!UICONTROL Category]**: Integrierte Plattformen;
   * **[!UICONTROL Type]**: Personenbasiert;
   * **[!UICONTROL Platform]**: Wählen Sie die personenbasierte Plattform aus, an die Sie Zielgruppensegmente senden möchten.
   * **[!UICONTROL Account]**: Wählen Sie das gewünschte Advertiser-Konto aus, das mit der ausgewählten Plattform verknüpft ist.
     ![create-destination](assets/pbd-create-destination.png)
1. Klicken Sie auf **[!UICONTROL Next]**.
1. Wählen Sie die **[!UICONTROL Data Export Labels]** aus, die Sie für dieses Ziel festlegen möchten.
1. Wählen Sie im Abschnitt **[!UICONTROL Configuration]** die Datenquelle aus, die Ihre Hash-Datenquellen enthält.
1. Wählen Sie im Abschnitt **[!UICONTROL Segment Mappings]** die Segmente aus, die Sie an dieses Ziel senden möchten. Dies wären die Segmente, die Sie unter [Schritt 5 - Zielgruppensegmente erstellen](people-based-destinations-workflow-offline.md#create-audience-segments) erstellt haben.
1. Speichern Sie das Ziel.
