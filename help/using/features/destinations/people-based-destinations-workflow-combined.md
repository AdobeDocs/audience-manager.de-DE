---
description: 'Diese Seite enthält eine schrittweise Anleitung dazu, wie Sie Offline-CRM-Daten mit Verhaltensdaten kombinieren, die Sie bereits im Audience Manager haben, um neue Zielgruppensegmente zu erstellen, und diese Zielgruppensegmente dann an People-basierte Ziele senden.  '
seo-description: 'Diese Seite enthält eine schrittweise Anleitung dazu, wie Sie Offline-CRM-Daten mit Verhaltensdaten kombinieren, die Sie bereits im Audience Manager haben, um neue Zielgruppensegmente zu erstellen, und diese Zielgruppensegmente dann an People-basierte Ziele senden.   '
seo-title: Workflow A – Personalisierung basierend auf allen Online-Aktivitäten in Kombination mit Offline-Daten
solution: Audience Manager
title: Workflow A – Personalisierung basierend auf allen Online-Aktivitäten in Kombination mit Offline-Daten
feature: Benutzerbasierte Ziele
exl-id: 1f906955-8fe7-4cce-95d6-0e4275d523e8
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1181'
ht-degree: 7%

---

# Workflow A – Personalisierung basierend auf allen Online-Aktivitäten in Kombination mit Offline-Daten {#workflow-a}

>[!IMPORTANT]
>Dieser Artikel enthält die Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um rechtliche Hinweise zu erhalten.

Auf dieser Seite finden Sie eine schrittweise Anleitung dazu, wie Sie Offline-[!DNL CRM]-Daten mit Verhaltensdaten kombinieren, die Sie bereits im Audience Manager haben, um neue Zielgruppensegmente zu erstellen, und diese Zielgruppensegmente dann an [!DNL People-Based Destinations] senden.

## Schritt 1: Konfigurieren der Datenquelleneinstellungen {#configure-data-source-settings}

Je nachdem, ob Ihre [DPUUIDs](../../reference/ids-in-aam.md) in Kleinbuchstaben und Hash-E-Mail-Adressen enthalten, müssen Sie möglicherweise die Datenquelle konfigurieren, in der die Hash-E-Mail-Adressen gespeichert werden.

 

**Szenario 1: Ihre  [](../../reference/ids-in-aam.md) DPUUIDs sind bereits in Kleinbuchstaben, gehashte E-Mail-Adressen.**

In diesem Fall müssen Sie die entsprechende Datenquelle als solche beschriften:

1. Gehen Sie zu [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Suchen Sie die Datenquelle, die Ihre [DPUUIDs](../../reference/ids-in-aam.md) enthält, und klicken Sie darauf.
1. Wählen Sie im Dropdown-Menü **[!UICONTROL ID Type]** die Option **[!UICONTROL Cross Device]** aus.
1. Stellen Sie sicher, dass die Option [!UICONTROL Cannot be tied to personally identifiable information] deaktiviert ist.
1. Wählen Sie im Abschnitt **[!UICONTROL Data Source Settings]** die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Wählen Sie im Dropdown-Menü die **[!UICONTROL Emails(SHA256, lowercased)]**-Beschriftung für diese Datenquelle aus.
   >[!IMPORTANT]
   >
   >Diese Option bezeichnet die Datenquelle nur als die mit diesem spezifischen Algorithmus gehashten Daten. In diesem Schritt werden die Daten von Audience Manager nicht gehasht. Stellen Sie sicher, dass die E-Mail-Adressen, die Sie in dieser Datenquelle speichern möchten, bereits mit dem Algorithmus [!DNL SHA256] gehasht sind. Andernfalls können Sie es nicht für [!DNL People-Based Destinations] verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Speichern Sie die Datenquelleneinstellungen.

 

**Szenario 2: Ihre  [](../../reference/ids-in-aam.md) DPUUIDs sind keine E-Mail-Adressen mit Hash-Zeichen in Kleinbuchstaben.**

In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen, in der Ihre Hash-E-Mail-Adressen gespeichert werden. Gehen Sie wie folgt vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, navigieren Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** und klicken Sie auf **[!UICONTROL Add New]**.
1. Geben Sie für Ihre neue Datenquelle [!UICONTROL Name] und [!UICONTROL Description] ein.
1. Wählen Sie im Dropdown-Menü **[!UICONTROL ID Type]** die Option **[!UICONTROL Cross Device]** aus.
1. Wählen Sie im Abschnitt **[!UICONTROL Data Source Settings]** die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die Option **[!UICONTROL Share associated cross-device IDs in people-based destinations]** .
1. Wählen Sie im Dropdown-Menü die **[!UICONTROL Emails(SHA256, lowercased)]**-Beschriftung für diese Datenquelle aus.
   >[!IMPORTANT]
   >
   >Diese Option bezeichnet die Datenquelle nur als die mit diesem spezifischen Algorithmus gehashten Daten. In diesem Schritt werden die Daten von Audience Manager nicht gehasht. Stellen Sie sicher, dass die E-Mail-Adressen, die Sie in dieser Datenquelle speichern möchten, bereits mit dem Algorithmus [!DNL SHA256] gehasht sind. Andernfalls können Sie es nicht für [!DNL People-Based Destinations] verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Speichern Sie die Datenquelleneinstellungen.

Sehen Sie sich das Video unten an, um ein Video-Tutorial zum Erstellen einer Datenquelle für [!UICONTROL People-Based Destinations] anzuzeigen.

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Unter [Daten-Onboarding](people-based-destinations-prerequisites.md#data-onboarding) finden Sie häufig gestellte Fragen dazu, wie Sie Ihre Offline-Daten für personenbasierte Ziele in den Audience Manager einbringen sollten.

## Schritt 2: Abgleichen von DPUUIDs mit Hash-E-Mail-Adressen über dateibasierte ID-Synchronisierung {#match-ids-emails}

>[!IMPORTANT]
>
> Dieser Schritt gilt nur für das oben beschriebene [Szenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings). Wenn Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) bereits Hash-E-Mail-Adressen sind, gehen Sie zu [Schritt 3 - Erstellen einer Profilzusammenführungsregel für die Segmentierung](people-based-destinations-workflow-combined.md#create-merge-rule).

Angenommen, Sie möchten Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) mit den Hash-E-Mail-Adressen aus der unten stehenden Tabelle (rechte Spalte) abgleichen und die Hash-E-Mail-Adressen in der neuen Datenquelle speichern, die Sie unter [Schritt 1 - Einstellungen für die Datenquelle konfigurieren](people-based-destinations-workflow-combined.md#configure-data-source-settings) erstellt haben.

| DPUUID (CRM ID) | E-Mail-Adresse | Hash-E-Mail-Adresse |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f11625093a19bc32fff15041 149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Sie können bis zu 10 Hash-E-Mail-Adressen mit einer einzelnen [DPUUID](../../reference/ids-in-aam.md) verknüpfen. Trennen Sie dazu die Hash-E-Mail-Adressen in der Synchronisierungsdatei durch `<TAB>`.

In unserem Beispiel hätten Sie nun zwei Datenquellen.

| Datenquellen-ID | Datenquelleninhalte |
| -------------- | -------------------------- |
| 999999 | Vorhandene DPUUIDs (CRM-IDs) |
| 987654 | Hash-E-Mail-Adressen |

 

Ihre [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) würde den folgenden Inhalt haben:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Die [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) muss dieser Namensstruktur entsprechen:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Im obigen Beispiel würde der Dateiname wie folgt aussehen:
`c2c_id_999999_987654_1560431657.sync`

[Beispieldatei hier herunterladen](assets/c2c_id_999999_987654_1560431657.sync).

Nachdem Sie Ihre ID-Synchronisierungsdatei erstellt haben, müssen Sie sie in einen [!DNL Amazon S3]-Bucket hochladen. Informationen zum Hochladen von ID-Synchronisierungsdateien finden Sie unter [Senden von Batch-Daten an Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Schritt 3: Erstellen einer Profilzusammenführungsregel für die Segmentierung {#create-merge-rule}

Der nächste Schritt besteht darin, eine neue Zusammenführungsregel zu erstellen, mit der Sie die Zielgruppensegmente erstellen können, die an Ihre personenbasierten Ziele gesendet werden.

>[!IMPORTANT]
>
> Wenn Sie bereits eine Regel mit den Optionen [!UICONTROL Current Authenticated Profiles] oder [!UICONTROL Last Authenticated Profiles] definiert haben, können Sie zu [Schritt 4 - Zielgruppensegmente erstellen](people-based-destinations-workflow-combined.md#create-audience-segments) überspringen.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Klicken **[!UICONTROL Add New Rule]**.
1. Geben Sie eine Profilzusammenführungsregel **[!UICONTROL Name]** und **[!UICONTROL Description]** ein.
1. Wählen Sie im Abschnitt **[!UICONTROL Profile Merge Rule Setup]** die Optionen **[!UICONTROL Current Authenticated Profiles]** oder **[!UICONTROL Last Authenticated Profiles]** aus.
1. Wählen Sie in der Liste **[!UICONTROL Cross-Device Profile Options]** die Datenquellen aus, für die Sie die Segmentierung ausführen möchten. Dies sollten die Datenquellen sein, die Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md) enthalten.

## Schritt 4: Erstellen von Zielgruppensegmenten {#create-audience-segments}

Verwenden Sie zum Erstellen neuer Zielgruppensegmente den [Segment Builder](../segments/segment-builder.md). Wenn Sie bereits über Zielgruppensegmente verfügen, die Sie an [!DNL People-Based Destinations] senden möchten, gehen Sie zu [Schritt 5: Konfigurieren der personenbasierten Plattformauthentifizierung](people-based-destinations-workflow-combined.md#configure-authentication).

## Schritt 5: Konfigurieren der personenbasierten Plattformauthentifizierung {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Wenn Sie bereits eine Integration mit einer sozialen Plattform konfiguriert haben, sollte diese auf dieser Seite aufgeführt sein. Andernfalls ist die Seite leer.
   ![People-based-integration](assets/pbd-config.png)
1. Klicken **[!UICONTROL Add Account]**.
1. Wählen Sie im Dropdown-Menü **[!UICONTROL People-Based Platform]** die Plattform aus, mit der Sie die Integration konfigurieren möchten.
   ![people-based-platform](assets/pbd-add.png)
1. Klicken Sie auf **[!UICONTROL Confirm]** , um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
1. Nachdem Sie sich bei Ihrem Social-Plattform-Konto authentifiziert haben, werden Sie zu dem Audience Manager weitergeleitet, in dem Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das Advertiser-Konto aus, das Sie verwenden möchten, und klicken Sie auf **[!UICONTROL Confirm]**.
1. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Sie darüber zu informieren, ob das Konto erfolgreich hinzugefügt wurde. Mit der Benachrichtigung können Sie auch eine Kontakt-E-Mail-Adresse hinzufügen, um Benachrichtigungen zu erhalten, wenn die Authentifizierung der sozialen Plattform bald abläuft.

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
1. Wählen Sie im Abschnitt **[!UICONTROL Segment Mappings]** die Segmente aus, die Sie an dieses Ziel senden möchten. Dies wären die Segmente, die Sie unter [Schritt 4 - Erstellen von Zielgruppensegmenten](people-based-destinations-workflow-combined.md#create-audience-segments) erstellt haben.
1. Speichern Sie das Ziel.
