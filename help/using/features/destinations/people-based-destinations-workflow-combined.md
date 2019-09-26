---
description: 'Diese Seite enthält eine schrittweise Anleitung dazu, wie Sie Offline-CRM-Daten mit Verhaltensdaten kombinieren, die Sie bereits in Audience Manager haben, um neue Zielgruppensegmente zu erstellen, und diese Zielgruppensegmente dann an benutzerbasierte Ziele senden.  '
seo-description: 'Diese Seite enthält eine schrittweise Anleitung dazu, wie Sie Offline-CRM-Daten mit Verhaltensdaten kombinieren, die Sie bereits in Audience Manager haben, um neue Zielgruppensegmente zu erstellen, und diese Zielgruppensegmente dann an benutzerbasierte Ziele senden.   '
seo-title: Arbeitsablauf A - Personalisierung auf der Grundlage aller Online-Aktivitäten in Kombination mit Offline-Daten
solution: Audience Manager
title: Arbeitsablauf A - Personalisierung auf der Grundlage aller Online-Aktivitäten in Kombination mit Offline-Daten
translation-type: tm+mt
source-git-commit: f500b4a763f1639392253b7e5f209395a978e45e

---


# Arbeitsablauf A - Personalisierung auf der Grundlage aller Online-Aktivitäten in Kombination mit Offline-Daten {#workflow-a}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Diese Seite enthält eine schrittweise Anleitung, wie Sie Offline- [!DNL CRM] Daten mit Verhaltensdaten kombinieren, die Sie bereits in Audience Manager haben, um neue Zielgruppensegmente zu erstellen, und diese Zielgruppensegmente dann an [!DNL People-Based Destinations]senden.

## Schritt 1: Konfigurieren der Datenquelleneinstellungen {#configure-data-source-settings}

Je nachdem, ob es sich bei Ihren [DPUUIDs](../../reference/ids-in-aam.md) um Kleinbuchstaben und Hash-E-Mail-Adressen handelt, müssen Sie möglicherweise die Datenquelle konfigurieren, in der die Hash-E-Mail-Adressen gespeichert werden.

 

**Szenario 1: Ihre[DPUUIDs](../../reference/ids-in-aam.md)sind bereits in Kleinbuchstaben, mit Hash-E-Mail-Adressen.**

In diesem Fall müssen Sie die entsprechende Datenquelle als solche kennzeichnen:

1. Gehen Sie zu [!UICONTROL Audience Data] -&gt; [!UICONTROL Data Sources].
1. Suchen Sie die Datenquelle, die Ihre [DPUUIDs](../../reference/ids-in-aam.md)enthält, und klicken Sie darauf.
1. Wählen Sie im **[!UICONTROL ID Type]** Dropdownmenü die Option **[!UICONTROL Cross Device]**.
1. Stellen Sie sicher, dass die Option deaktiviert [!UICONTROL Cannot be tied to personally identifiable information] ist.
1. Wählen Sie im **[!UICONTROL Data Source Settings]** Abschnitt die Optionen **[!UICONTROL Inbound]** und **[!UICONTROL Outbound]** aus und aktivieren Sie die **[!UICONTROL Share associated cross-device IDs in people-based destinations]** Option.
1. Verwenden Sie das Dropdownmenü, um die **[!UICONTROL Emails(SHA256, lowercased)]** Bezeichnung für diese Datenquelle auszuwählen.
   >[!IMPORTANT]
   >
   >Diese Option bezeichnet die Datenquelle nur als mit diesem spezifischen Algorithmus Hash-Daten. In Audience Manager werden die Daten in diesem Schritt nicht zwischengespeichert. Vergewissern Sie sich, dass die E-Mail-Adressen, die Sie bei der Speicherung in dieser Datenquelle planen, bereits mit dem [!DNL SHA256] Algorithmus Hashing ausgeführt wurden. Andernfalls können Sie es nicht für [!DNL People-Based Destinations]die Anwendung verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Speichern Sie die Datenquelleneinstellungen.

 

**Szenario 2: Ihre[DPUUIDs](../../reference/ids-in-aam.md)sind nicht in Kleinbuchstaben, sondern Hash-E-Mail-Adressen.**

In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen, in der Ihre Hash-E-Mail-Adressen gespeichert werden. So geht das:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**, und klicken Sie auf **[!UICONTROL Add New]**.
1. Geben Sie ein [!UICONTROL Name] und [!UICONTROL Description] für Ihre neue Datenquelle ein.
1. In the **[!UICONTROL ID Type]** drop-down menu, select **[!UICONTROL Cross Device]**.
1. In the **[!UICONTROL Data Source Settings]** section, select both the **[!UICONTROL Inbound]** and **[!UICONTROL Outbound]** options, and enable the **[!UICONTROL Share associated cross-device IDs in people-based destinations]** option.
1. Use the drop-down menu to select the **[!UICONTROL Emails(SHA256, lowercased)]** label for this data source.
   >[!IMPORTANT]
   >
   >This option only labels the data source as containing data hashed with that specific algorithm. Audience Manager does not hash the data at this step. Make sure the email addresses that you plan on storing in this data source are already hashed with the [!DNL SHA256] algorithm. Otherwise, you won't be able to use it for .[!DNL People-Based Destinations]

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Save the data source settings.

>[!NOTE]
>
> See Data Onboarding for frequently asked questions about how you should bring your offline data into Audience Manager for People-Based Destinations.[](people-based-destinations-prerequisites.md#data-onboarding)

## Step 2 - Match DPUUIDs to Hashed Email Addresses via File-Based ID Synchronization {#match-ids-emails}

>[!IMPORTANT]
>
> This step only applies to Scenario 2 described above. [](people-based-destinations-workflow-combined.md#configure-data-source-settings) If your existing DPUUIDs are already hashed email addresses, skip to Step 3 - Create a Profile Merge Rule for Segmentation.[](../../reference/ids-in-aam.md)[](people-based-destinations-workflow-combined.md#create-merge-rule)

Let's say you want to match your existing DPUUIDs to the hashed email addresses from the table below (right column), and store the hashed email addresses in the new data source that you created at Step 1 - Configure Data Source Settings.[](../../reference/ids-in-aam.md)[](people-based-destinations-workflow-combined.md#configure-data-source-settings)

| DPUUID (CRM ID) | E-Mail-Adresse | Hash-E-Mail-Adresse |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Sie können bis zu 10 Hash-E-Mail-Adressen mit einer einzigen [DPUUID](../../reference/ids-in-aam.md)verknüpfen. Dazu trennen Sie die Hash-E-Mail-Adressen durch ein Komma in der Synchronisierungsdatei.

In unserem Beispiel würden Sie nun über zwei Datenquellen verfügen.

| Datenquellen-ID | Datenquellinhalte |
| -------------- | -------------------------- |
| 999999 | Vorhandene DPUUIDs (CRM-IDs) |
| 987654 | Hash-E-Mail-Adressen |

 

Ihre [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) enthält folgenden Inhalt:

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

## Schritt 3: Erstellen einer Regel zur Profilzusammenführung für die Segmentierung {#create-merge-rule}

Der nächste Schritt ist die Erstellung einer neuen Zusammenführungsregel, mit der Sie die Zielgruppensegmente erstellen können, die an Ihre benutzerbasierten Ziele gesendet werden.

>[!IMPORTANT]
>
> Wenn Sie bereits über eine Regel verfügen, die mit den [!UICONTROL Current Authenticated Profiles] Optionen oder [!UICONTROL Last Authenticated Profiles] Optionen definiert wurde, können Sie zu [Schritt 4 - Zielgruppensegmente](people-based-destinations-workflow-combined.md#create-audience-segments)erstellen überspringen.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Profile Merge Rules]**.
1. Klicken Sie auf **[!UICONTROL Add New Rule]**.
1. Geben Sie eine Regel zum Zusammenführen des Profils ein **[!UICONTROL Name]** und **[!UICONTROL Description]**.
1. Wählen Sie im **[!UICONTROL Profile Merge Rule Setup]** Abschnitt die **[!UICONTROL Current Authenticated Profiles]** oder die **[!UICONTROL Last Authenticated Profiles]** Optionen aus.
1. Wählen Sie in der **[!UICONTROL Cross-Device Profile Options]** Liste die Datenquellen aus, für die Sie die Segmentierung ausführen möchten. Dies sollten die Datenquellen sein, die Ihre vorhandenen [DPUUIDs](../../reference/ids-in-aam.md)enthalten.

## Schritt 4: Zielgruppensegmente erstellen {#create-audience-segments}

Verwenden Sie zum Erstellen neuer Zielgruppensegmente den [Segmentaufbau](../segments/segment-builder.md). Wenn Sie bereits Zielgruppensegmente haben, an die Sie senden möchten, fahren Sie mit [!DNL People-Based Destinations]Schritt 5 - [Konfiguration der People-Based Platform-Authentifizierung](people-based-destinations-workflow-combined.md#configure-authentication)fort.

## Schritt 5: Konfiguration der Authentifizierung für benutzerbasierte Plattformen {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer sozialen Plattform haben, sollte diese auf dieser Seite aufgeführt werden. Andernfalls ist die Seite leer.
   ![people-based-integration](assets/pbd-config.png)
1. Klicken Sie auf **[!UICONTROL Add Account]**.
1. Verwenden Sie das **[!UICONTROL People-Based Platform]** Dropdownmenü, um die Plattform auszuwählen, mit der Sie die Integration konfigurieren möchten.
   ![people-based-platform](assets/pbd-add.png)
1. Click  to be redirected to the authentication page of the selected platform.**[!UICONTROL Confirm]**
1. Once you've authenticated to your social platform account, you are redirected to Audience Manager where you should see your associated advertiser accounts. Select the advertiser account that you want to use and click .**[!UICONTROL Confirm]**
1. Audience Manager displays a notification at the top of the page to let you know whether the account was successfully added. The notification also allows you to add a contact email address to receive notifications when the social platform authentication is about to expire.

>[!IMPORTANT]
>
>A udience Manager handles the integration with social platforms through authentication tokens that expire after a certain amount of time. See Authentication Token Renewal for details on how to renew the expired tokens.

## Step 6 - Create a People-Based Destination {#create-destination}

1. Log in to your Audience Manager account, go to  &gt; , and click .**[!UICONTROL Audience Data]****[!UICONTROL Destinations]****[!UICONTROL Create Destination]**
1. In the  section, enter a  and  for your new data source, and use the following settings:**[!UICONTROL Basic Information]****[!UICONTROL Name]****[!UICONTROL Description]**
   * **[!UICONTROL Category]**: Integrated Platforms;
   * **[!UICONTROL Type]**: People-Based;
   * **[!UICONTROL Platform]**: Wählen Sie die personalbasierte Plattform aus, an die Sie Zielgruppensegmente senden möchten.
   * **[!UICONTROL Account]**: select the desired advertiser account associated with the selected platform.
      ![create-destination](assets/pbd-create-destination.png)
1. Klicken Sie auf **[!UICONTROL Next]**.
1. Wählen Sie **[!UICONTROL Data Export Labels]** das Ziel aus, das Sie für dieses Ziel festlegen möchten.
1. In the  section, select the data source that contains your hashed data sources.**[!UICONTROL Configuration]**
1. Wählen Sie im **[!UICONTROL Segment Mappings]** Abschnitt die Segmente aus, die Sie an dieses Ziel senden möchten. Dies sind die Segmente, die Sie in [Schritt 4 - Zielgruppensegmente](people-based-destinations-workflow-combined.md#create-audience-segments)erstellen erstellt haben.
1. Speichern Sie das Ziel.
