---
description: 'Diese Seite enthält eine schrittweise Anleitung zum Kombinieren von Offline-CRM-Daten mit Verhaltensdaten, die Sie bereits im Audience Manager haben, um neue Audiencen zu erstellen, und zum anschließenden Senden dieser Audiencen an benutzerbasierte Ziele.  '
seo-description: 'Diese Seite enthält eine schrittweise Anleitung zum Kombinieren von Offline-CRM-Daten mit Verhaltensdaten, die Sie bereits im Audience Manager haben, um neue Audiencen zu erstellen, und zum anschließenden Senden dieser Audiencen an benutzerbasierte Ziele.   '
seo-title: Arbeitsablauf A - Personalisierung auf der Grundlage aller Online-Aktivitäten in Kombination mit Offline-Daten
solution: Audience Manager
title: Arbeitsablauf A - Personalisierung auf der Grundlage aller Online-Aktivitäten in Kombination mit Offline-Daten
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Arbeitsablauf A - Personalisierung auf der Grundlage aller Online-Aktivitäten in Kombination mit Offline-Daten {#workflow-a}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Diese Seite enthält eine schrittweise Anleitung zum Kombinieren von Offline- [!DNL CRM] Daten mit Verhaltensdaten, die Sie bereits in Audience Manager haben, um neue Audiencen zu erstellen, und zum Senden dieser Audiencen an [!DNL People-Based Destinations].

## Schritt 1: Konfigurieren der Datenquelleneinstellungen {#configure-data-source-settings}

Je nachdem, ob es sich bei Ihren [DPUUIDs](../../reference/ids-in-aam.md) um Kleinbuchstaben und Hash-E-Mail-Adressen handelt, müssen Sie möglicherweise die Datenquelle konfigurieren, in der die Hash-E-Mail-Adressen gespeichert werden.

 

**Szenario 1: Ihre[DPUUIDs](../../reference/ids-in-aam.md)sind bereits in Kleinbuchstaben, mit Hash-E-Mail-Adressen.**

In diesem Fall müssen Sie die entsprechende Datenquelle als solche kennzeichnen:

1. Gehen Sie zu [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Suchen Sie die Datenquelle, die Ihre [DPUUIDs](../../reference/ids-in-aam.md)enthält, und klicken Sie darauf.
1. Wählen Sie im **[!UICONTROL ID Type]** Dropdownmenü die Option **[!UICONTROL Cross Device]**.
1. Stellen Sie sicher, dass die Option deaktiviert [!UICONTROL Cannot be tied to personally identifiable information] ist.
1. Wählen Sie im **[!UICONTROL Data Source Settings]** Abschnitt die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die **[!UICONTROL Share associated cross-device IDs in people-based destinations]** Option.
1. Verwenden Sie das Dropdown-Menü, um die **[!UICONTROL Emails(SHA256, lowercased)]** Bezeichnung für diese Datenquelle auszuwählen.
   >[!IMPORTANT]
   >
   >Diese Option bezeichnet die Datenquelle nur als mit diesem spezifischen Algorithmus Hash-Daten. Audience Manager stellt die Daten in diesem Schritt nicht in Hashing dar. Vergewissern Sie sich, dass die E-Mail-Adressen, die Sie bei der Speicherung in dieser Datenquelle planen, bereits mit dem [!DNL SHA256] Algorithmus Hashing ausgeführt wurden. Andernfalls können Sie es nicht für [!DNL People-Based Destinations]die Anwendung verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Speichern Sie die Datenquelleneinstellungen.

 

**Szenario 2: Ihre[DPUUIDs](../../reference/ids-in-aam.md)sind nicht in Kleinbuchstaben, sondern Hash-E-Mail-Adressen.**

In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen, in der Ihre Hash-E-Mail-Adressen gespeichert werden. So geht das:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**, und klicken Sie auf **[!UICONTROL Add New]**.
1. Geben Sie ein [!UICONTROL Name] und [!UICONTROL Description] für Ihre neue Datenquelle ein.
1. Wählen Sie im **[!UICONTROL ID Type]** Dropdownmenü die Option **[!UICONTROL Cross Device]**.
1. Wählen Sie im **[!UICONTROL Data Source Settings]** Abschnitt die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die **[!UICONTROL Share associated cross-device IDs in people-based destinations]** Option.
1. Verwenden Sie das Dropdown-Menü, um die **[!UICONTROL Emails(SHA256, lowercased)]** Bezeichnung für diese Datenquelle auszuwählen.
   >[!IMPORTANT]
   >
   >Diese Option bezeichnet die Datenquelle nur als mit diesem spezifischen Algorithmus Hash-Daten. Audience Manager stellt die Daten in diesem Schritt nicht in Hashing dar. Vergewissern Sie sich, dass die E-Mail-Adressen, die Sie bei der Speicherung in dieser Datenquelle planen, bereits mit dem [!DNL SHA256] Algorithmus Hashing ausgeführt wurden. Andernfalls können Sie es nicht für [!DNL People-Based Destinations]die Anwendung verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Speichern Sie die Datenquelleneinstellungen.

Sehen Sie sich das Video unten an, in dem Sie erfahren, wie Sie eine Datenquelle erstellen [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Häufig gestellte Fragen dazu, wie Sie Ihre Offlinedaten in den Audience Manager für personenbasierte Ziele einbeziehen sollten, finden Sie unter [DatenOnboarding](people-based-destinations-prerequisites.md#data-onboarding) .

## Schritt 2: Zuordnen von DPUUIDs zu Hash-E-Mail-Adressen über dateibasierte ID-Synchronisierung {#match-ids-emails}

>[!IMPORTANT]
>
> Dieser Schritt gilt nur für das oben beschriebene [Szenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) . Wenn Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) bereits mit Hashing-E-Mail-Adressen versehen sind, fahren Sie mit [Schritt 3 - Eine Profil-Merge-Regel für die Segmentierung](people-based-destinations-workflow-combined.md#create-merge-rule)erstellen fort.

Angenommen, Sie möchten Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) mit den Hash-E-Mail-Adressen aus der Tabelle unten (rechte Spalte) abgleichen und die Hash-E-Mail-Adressen in der neuen Datenquelle speichern, die Sie in [Schritt 1 - Datenquelleneinstellungen](people-based-destinations-workflow-combined.md#configure-data-source-settings)konfigurieren erstellt haben.

| DPUUID (CRM-ID) | E-Mail-Adresse | Hash-E-Mail-Adresse |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Sie können bis zu 10 Hash-E-Mail-Adressen mit einer einzigen [DPUUID](../../reference/ids-in-aam.md)verknüpfen. Dazu trennen Sie die Hash-E-Mail-Adressen durch ein Komma in der Synchronisierungsdatei.

In unserem Beispiel würden Sie nun über zwei Datenquellen verfügen.

| Datenquellen-ID | Datenquelleninhalte |
| -------------- | -------------------------- |
| 999999 | Vorhandene DPUUIDs (CRM-IDs) |
| 987654 | Hash-E-Mail-Adressen |

 

Ihre [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) enthält den folgenden Inhalt:

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

<!-- Victor/Vlad: Please check the above link. Any way you can move this download to Git? I'm concerned about the plans to decommission marketing.adobe.com -Bob -->

Nachdem Sie die ID-Synchronisierungsdatei erstellt haben, müssen Sie sie in einen [!DNL Amazon S3] Behälter hochladen. Informationen zum Hochladen von ID-Synchronisierungsdateien finden Sie unter Stapeldaten an Audience Manager [senden](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Schritt 3: Erstellen einer Profil Merge Rule for Segmentation {#create-merge-rule}

Im nächsten Schritt erstellen Sie eine neue Zusammenführungsregel, mit der Sie die Audiencen erstellen können, die an Ihre benutzerspezifischen Ziele gesendet werden.

>[!IMPORTANT]
>
> Wenn Sie bereits eine Regel mit den [!UICONTROL Current Authenticated Profiles] bzw. [!UICONTROL Last Authenticated Profiles] Optionen definiert haben, können Sie zu [Schritt 4 - Segmente](people-based-destinations-workflow-combined.md#create-audience-segments)erstellen überspringen.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Klicken **[!UICONTROL Add New Rule]**.
1. Geben Sie eine Profil Merge-Regel ein **[!UICONTROL Name]** und **[!UICONTROL Description]**.
1. Wählen Sie im **[!UICONTROL Profile Merge Rule Setup]** Abschnitt die **[!UICONTROL Current Authenticated Profiles]** bzw. die **[!UICONTROL Last Authenticated Profiles]** Optionen aus.
1. Wählen Sie in der **[!UICONTROL Cross-Device Profile Options]** Liste die Datenquellen aus, für die Sie die Segmentierung ausführen möchten. Dies sollten die Datenquellen sein, die Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md)enthalten.

## Schritt 4: Erstellen von Segmenten für Audiencen {#create-audience-segments}

Verwenden Sie den [Segmentaufbau](../segments/segment-builder.md), um neue Segmentsegmente zu erstellen. Wenn Sie bereits Audiencen haben, an die Sie senden möchten, fahren Sie mit [!DNL People-Based Destinations]Schritt 5 - [Personenbasierte Plattformauthentifizierung](people-based-destinations-workflow-combined.md#configure-authentication)konfigurieren fort.

## Schritt 5: Konfiguration der Authentifizierung für benutzerbasierte Plattformen {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer sozialen Plattform haben, sollte diese auf dieser Seite aufgeführt werden. Andernfalls ist die Seite leer.
   ![people-based-integration](assets/pbd-config.png)
1. Klicken **[!UICONTROL Add Account]**.
1. Verwenden Sie das **[!UICONTROL People-Based Platform]** Dropdownmenü, um die Plattform auszuwählen, mit der Sie die Integration konfigurieren möchten.
   ![people-based-platform](assets/pbd-add.png)
1. Klicken Sie auf **[!UICONTROL Confirm]** , um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
1. Nachdem Sie sich bei Ihrem Social-Plattformkonto authentifiziert haben, werden Sie zum Audience-Manager weitergeleitet, wo Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das gewünschte Advertiser-Konto aus und klicken Sie auf **[!UICONTROL Confirm]**.
1. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Sie darüber zu informieren, ob das Konto erfolgreich hinzugefügt wurde. Mit der Benachrichtigung können Sie auch eine E-Mail-Adresse hinzufügen, um Benachrichtigungen zu erhalten, wenn die Social-Plattform-Authentifizierung demnächst abläuft.

>[!IMPORTANT]
>
>Ein Audience Manager verarbeitet die Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Weitere Informationen zur Verlängerung der abgelaufenen Token finden Sie unter Erneuerung des Authentifizierungstokens.

## Schritt 6: Erstellen eines benutzerbasierten Ziels {#create-destination}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]** und klicken Sie auf **[!UICONTROL Create Destination]**.
1. Geben Sie **[!UICONTROL Basic Information]** im Abschnitt eine **[!UICONTROL Name]** und **[!UICONTROL Description]** für die neue Datenquelle ein und verwenden Sie die folgenden Einstellungen:
   * **[!UICONTROL Category]**: Integrierte Plattformen;
   * **[!UICONTROL Type]**: Volksansässige;
   * **[!UICONTROL Platform]**: Wählen Sie die personalisierte Plattform aus, an die Sie Audiencen senden möchten.
   * **[!UICONTROL Account]**: Wählen Sie das gewünschte Advertiser-Konto aus, das mit der ausgewählten Plattform verknüpft ist.
      ![create-destination](assets/pbd-create-destination.png)
1. Klicken **[!UICONTROL Next]**.
1. Wählen Sie **[!UICONTROL Data Export Labels]** das Ziel aus, das Sie für dieses Ziel festlegen möchten.
1. Wählen Sie im **[!UICONTROL Configuration]** Abschnitt die Datenquelle aus, die Ihre Hash-Datenquellen enthält.
1. Wählen Sie im **[!UICONTROL Segment Mappings]** Abschnitt die Segmente aus, die Sie an dieses Ziel senden möchten. Dies sind die Segmente, die Sie unter [Schritt 4 - Segmente](people-based-destinations-workflow-combined.md#create-audience-segments)erstellen erstellt haben.
1. Speichern Sie das Ziel.
