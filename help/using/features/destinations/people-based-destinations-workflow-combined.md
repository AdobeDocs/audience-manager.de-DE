---
description: 'Diese Seite enthält eine schrittweise Anleitung dazu, wie Sie Offline-CRM-Daten mit Verhaltensdaten kombinieren, die Sie bereits in Audience Manager haben, um neue Audiencen zu erstellen, und diese Audiencen dann an benutzerbasierte Ziele senden.  '
seo-description: 'Diese Seite enthält eine schrittweise Anleitung dazu, wie Sie Offline-CRM-Daten mit Verhaltensdaten kombinieren, die Sie bereits in Audience Manager haben, um neue Audiencen zu erstellen, und diese Audiencen dann an benutzerbasierte Ziele senden.   '
seo-title: Workflow A – Personalisierung basierend auf allen Online-Aktivitäten in Kombination mit Offline-Daten
solution: Audience Manager
title: Workflow A – Personalisierung basierend auf allen Online-Aktivitäten in Kombination mit Offline-Daten
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1180'
ht-degree: 7%

---


# Workflow A – Personalisierung basierend auf allen Online-Aktivitäten in Kombination mit Offline-Daten {#workflow-a}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Diese Seite enthält eine schrittweise Anleitung zum Kombinieren von Offline- [!DNL CRM]-Daten mit Verhaltensdaten, die Sie bereits in Audience Manager haben, um neue Audiencen zu erstellen, und zum Senden dieser Audiencen an [!DNL People-Based Destinations].

## Schritt 1: Konfigurieren der Datenquelleneinstellungen {#configure-data-source-settings}

Je nachdem, ob Ihre [DPUUIDs](../../reference/ids-in-aam.md) in Kleinbuchstaben und Hash-E-Mail-Adressen vorliegen, müssen Sie möglicherweise die Datenquelle konfigurieren, in der die Hash-E-Mail-Adressen gespeichert werden.

 

**Szenario 1: Ihre  [](../../reference/ids-in-aam.md) DPUUIDs sind bereits in Kleinbuchstaben, mit Hash-E-Mail-Adressen.**

In diesem Fall müssen Sie die entsprechende Datenquelle als solche kennzeichnen:

1. Gehen Sie zu [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Suchen Sie die Datenquelle, die Ihre [DPUUIDs](../../reference/ids-in-aam.md) enthält, und klicken Sie darauf.
1. Wählen Sie im Dropdownmenü **[!UICONTROL ID Type]** **[!UICONTROL Cross Device]**.
1. Stellen Sie sicher, dass die Option [!UICONTROL Cannot be tied to personally identifiable information] deaktiviert ist.
1. Wählen Sie im Abschnitt **[!UICONTROL Data Source Settings]** sowohl die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Verwenden Sie das Dropdown-Menü, um die Beschriftung **[!UICONTROL Emails(SHA256, lowercased)]** für diese Datenquelle auszuwählen.
   >[!IMPORTANT]
   >
   >Diese Option bezeichnet die Datenquelle nur als mit diesem spezifischen Algorithmus Hash-Daten. In diesem Schritt werden die Daten von Audience Manager nicht gehackt. Vergewissern Sie sich, dass die E-Mail-Adressen, die Sie in dieser Datenquelle speichern möchten, bereits mit dem Algorithmus [!DNL SHA256] Hashing arbeiten. Andernfalls können Sie es nicht für [!DNL People-Based Destinations] verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Speichern Sie die Datenquelleneinstellungen.

 

**Szenario 2: Ihre  [](../../reference/ids-in-aam.md) DPUUIDsare nicht in Kleinbuchstaben, Hash-E-Mail-Adressen.**

In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen, in der Ihre Hash-E-Mail-Adressen gespeichert werden. So geht das:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** und klicken Sie auf **[!UICONTROL Add New]**.
1. Geben Sie für Ihre neue Datenquelle [!UICONTROL Name] und [!UICONTROL Description] ein.
1. Wählen Sie im Dropdownmenü **[!UICONTROL ID Type]** **[!UICONTROL Cross Device]**.
1. Wählen Sie im Abschnitt **[!UICONTROL Data Source Settings]** sowohl die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Verwenden Sie das Dropdown-Menü, um die Beschriftung **[!UICONTROL Emails(SHA256, lowercased)]** für diese Datenquelle auszuwählen.
   >[!IMPORTANT]
   >
   >Diese Option bezeichnet die Datenquelle nur als mit diesem spezifischen Algorithmus Hash-Daten. In diesem Schritt werden die Daten von Audience Manager nicht gehackt. Vergewissern Sie sich, dass die E-Mail-Adressen, die Sie in dieser Datenquelle speichern möchten, bereits mit dem Algorithmus [!DNL SHA256] Hashing arbeiten. Andernfalls können Sie es nicht für [!DNL People-Based Destinations] verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Speichern Sie die Datenquelleneinstellungen.

Sehen Sie sich das folgende Video an, um einen Video-Lehrgang zum Erstellen einer Datenquelle für [!UICONTROL People-Based Destinations] anzuzeigen.

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Häufig gestellte Fragen dazu, wie Sie Ihre Offline-Daten in Audience Manager für People-Based Destination integrieren sollten, finden Sie unter [Data Onboarding](people-based-destinations-prerequisites.md#data-onboarding).

## Schritt 2: Zuordnen von DPUUIDs zu Hash-E-Mail-Adressen über dateibasierte ID-Synchronisierung {#match-ids-emails}

>[!IMPORTANT]
>
> Dieser Schritt gilt nur für das oben beschriebene [Szenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings). Wenn Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) bereits Hash-E-Mail-Adressen sind, gehen Sie zu [Schritt 3 - Eine Profil-Merge-Regel für die Segmentierung](people-based-destinations-workflow-combined.md#create-merge-rule) erstellen.

Angenommen, Sie möchten Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) mit den Hash-E-Mail-Adressen aus der Tabelle unten (rechte Spalte) abgleichen und die Hash-E-Mail-Adressen in der neuen Datenquelle speichern, die Sie unter [Schritt 1 - Konfigurieren der Datenquelleneinstellungen](people-based-destinations-workflow-combined.md#configure-data-source-settings) erstellt haben.

| DPUUID (CRM-ID) | E-Mail-Adresse | Hash-E-Mail-Adresse |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Sie können bis zu 10 Hash-E-Mail-Adressen mit einer einzigen [DPUUID](../../reference/ids-in-aam.md) verknüpfen. Dazu trennen Sie die Hash-E-Mail-Adressen durch ein Komma in der Synchronisierungsdatei.

In unserem Beispiel würden Sie nun über zwei Datenquellen verfügen.

| Datenquellen-ID | Datenquelleninhalte |
| -------------- | -------------------------- |
| 999999 | Vorhandene DPUUIDs (CRM-IDs) |
| 987654 | Hash-E-Mail-Adressen |

 

Ihre [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) würde folgenden Inhalt haben:

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

## Schritt 3: Erstellen einer Profil Merge Rule for Segmentation {#create-merge-rule}

Im nächsten Schritt erstellen Sie eine neue Zusammenführungsregel, mit der Sie die Audiencen erstellen können, die an Ihre benutzerspezifischen Ziele gesendet werden.

>[!IMPORTANT]
>
> Wenn Sie bereits eine Regel mit den Optionen [!UICONTROL Current Authenticated Profiles] oder [!UICONTROL Last Authenticated Profiles] definiert haben, können Sie zu [Schritt 4 - Audience-Segmente erstellen](people-based-destinations-workflow-combined.md#create-audience-segments) überspringen.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Klicken **[!UICONTROL Add New Rule]**.
1. Geben Sie eine Profil Mergeregel **[!UICONTROL Name]** und **[!UICONTROL Description]** ein.
1. Wählen Sie im Abschnitt **[!UICONTROL Profile Merge Rule Setup]** die Optionen **[!UICONTROL Current Authenticated Profiles]** oder **[!UICONTROL Last Authenticated Profiles]** aus.
1. Wählen Sie in der Liste **[!UICONTROL Cross-Device Profile Options]** die Datenquellen aus, für die Sie die Segmentierung ausführen möchten. Dies sollten die Datenquellen sein, die Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) enthalten.

## Schritt 4: Erstellen von Audiencen-Segmenten {#create-audience-segments}

Verwenden Sie zum Erstellen neuer Segmentsegmente den [Segmentaufbau](../segments/segment-builder.md). Wenn Sie bereits Audiencen haben, die Sie an [!DNL People-Based Destinations] senden möchten, gehen Sie zu [Schritt 5 - Personenbasierte Plattformauthentifizierung konfigurieren](people-based-destinations-workflow-combined.md#configure-authentication).

## Schritt 5: Personenbasierte Plattformauthentifizierung konfigurieren {#configure-authentication}

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
>Ein Audience Manager verarbeitet die Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Weitere Informationen zur Verlängerung der abgelaufenen Token finden Sie unter Erneuerung des Authentifizierungstokens.

## Schritt 6 - Erstellen eines benutzerbasierten Ziels {#create-destination}

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
1. Wählen Sie im Abschnitt **[!UICONTROL Segment Mappings]** die Segmente aus, die Sie an dieses Ziel senden möchten. Dies sind die Segmente, die Sie unter [Schritt 4 - Erstellen von Audiencen-Segmenten](people-based-destinations-workflow-combined.md#create-audience-segments) erstellt haben.
1. Speichern Sie das Ziel.
