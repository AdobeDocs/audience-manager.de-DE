---
description: 'Diese Seite enthält eine schrittweise Anleitung dazu, wie Offline-CRM-Daten mit Echtzeit-Verhaltensdaten für authentifizierte Benutzer kombiniert werden können, um Zielgruppensegmente zu erstellen, und diese Zielgruppensegmente dann an benutzerbasierte Ziele senden. '
seo-description: 'Diese Seite enthält eine schrittweise Anleitung dazu, wie Offline-CRM-Daten mit Echtzeit-Verhaltensdaten für authentifizierte Benutzer kombiniert werden können, um Zielgruppensegmente zu erstellen, und diese Zielgruppensegmente dann an benutzerbasierte Ziele senden.  '
seo-title: Arbeitsablauf C - Personalisierung basierend auf authentifizierter Aktivität in Kombination mit Offline-Daten
solution: Audience Manager
title: Arbeitsablauf C - Personalisierung basierend auf authentifizierter Aktivität in Kombination mit Offline-Daten
translation-type: tm+mt
source-git-commit: a2825f256364668abc4e6760a473713fec8626e3

---


# Arbeitsablauf C - Personalisierung basierend auf authentifizierter Aktivität in Kombination mit Offline-Daten {#workflow-c}

Diese Seite enthält eine schrittweise Anleitung, wie Offline- [!DNL CRM] Daten mit Echtzeit-Verhaltensdaten für authentifizierte Benutzer kombiniert werden können, um Zielgruppensegmente zu erstellen und diese Zielgruppensegmente dann an [!DNL People-Based Destinations]zu senden.

## Schritt 1: Konfigurieren der Datenquelleneinstellungen {#configure-data-source-settings}

Je nachdem, ob es sich bei Ihren [DPUUIDs](../../reference/ids-in-aam.md) um Kleinbuchstaben und Hash-E-Mail-Adressen handelt, müssen Sie möglicherweise die Datenquelle konfigurieren, in der die Hash-E-Mail-Adressen gespeichert werden.

 

**Szenario 1: Ihre[DPUUIDs](../../reference/ids-in-aam.md)sind bereits in Kleinbuchstaben, mit Hash-E-Mail-Adressen.**

In diesem Fall gehen Sie zu [Schritt 5 - Personenbasierte Plattformauthentifizierung](#configure-authentication)konfigurieren.

 

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

## Schritt 2: Verwenden Sie deklarierte IDs, um DPUUIDs mit Hash-E-Mail-Adressen über HTTP-Aufrufe in Echtzeit abzugleichen {#match-email-addresses}

Um authentifizierte Benutzer für regelbasierte Eigenschaften zu qualifizieren, müssen Sie die Eigenschaftenqualifikation über [deklarierte IDs](../declared-ids.md)senden.

### Beispiel 

Angenommen, Sie haben die folgenden beiden Datenquellen erstellt.

| Datenquellen-ID | Datenquellinhalte |
| -------------- | -------------------------- |
| 999999 | Vorhandene DPUUIDs (CRM-IDs) |
| 987654 | Hash-E-Mail-Adressen |

 

Anschließend sollten Sie die unten stehenden CRM-IDs für die Eigenschaft in der Tabelle qualifizieren.

| DPUUID (CRM-ID) | E-Mail-Adresse | Hash-E-Mail-Adresse | Trait- |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

Ihre deklarierte ID sollte der folgenden Syntax entsprechen:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

Im oben stehenden Beispiel sollte der deklarierte ID-Aufruf wie folgt aussehen:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Schritt 3: Erstellen einer Regel zur Profilzusammenführung für die Segmentierung {#create-profile-merge-rule-segmentation}

Der nächste Schritt ist die Erstellung einer neuen Zusammenführungsregel, mit der Sie die Zielgruppensegmente erstellen können, die an Ihre [!DNL People-Based Destinations]Benutzer gesendet werden.

>[!IMPORTANT]
>
>Wenn Sie bereits über eine Regel verfügen, die mit den **[!UICONTROL Current Authenticated Profiles]** Optionen oder **[!UICONTROL Last Authenticated Profiles]** Optionen definiert wurde, können Sie zu [Schritt 4 - Zielgruppensegmente](#create-audience-segments)erstellen überspringen.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Klicken Sie auf **[!UICONTROL Add New Rule]**.
3. Geben Sie eine Regel zum Zusammenführen des Profils ein **[!UICONTROL Name]** und **[!UICONTROL Description]**.
4. Wählen Sie im **[!UICONTROL Profile Merge Rule Setup]** Abschnitt die **[!UICONTROL All Cross-Device Profiles]** Regel aus der **[!UICONTROL Cross-Device Options]** Liste.
5. Wählen Sie in der **[!UICONTROL Cross-Device Profile Options]** Liste die Datenquellen aus, für die Sie die Segmentierung ausführen möchten. Dies sollten die Datenquellen sein, die Ihre vorhandenen DPUUIDs enthalten.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Schritt 4: Zielgruppensegmente erstellen {#create-audience-segments}

Verwenden Sie zum Erstellen neuer Segmente den [Segmentaufbau](../segments/segment-builder.md). Wenn Sie bereits Zielgruppensegmente haben, an die Sie senden möchten, fahren Sie mit [!DNL People-Based Destinations]Schritt 5 - [Konfiguration der People-Based Platform-Authentifizierung](#configure-authentication)fort.

## Schritt 5: Konfiguration der Authentifizierung für benutzerbasierte Plattformen {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer sozialen Plattform haben, sollte diese auf dieser Seite aufgeführt werden. Andernfalls ist die Seite leer.
   ![people-based-integration](assets/pbd-config.png)
2. Klicken Sie auf **[!UICONTROL Add Account]**.
3. Verwenden Sie das **[!UICONTROL People-Based Platform]** Dropdownmenü, um die Plattform auszuwählen, mit der Sie die Integration konfigurieren möchten.
   ![people-based-platform](assets/pbd-add.png)
4. Klicken Sie auf **[!UICONTROL Confirm]** , um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
5. Nachdem Sie sich bei Ihrem Social-Plattform-Konto authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das gewünschte Advertiser-Konto aus und klicken Sie auf **[!UICONTROL Confirm]**.
6. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Sie darüber zu informieren, ob das Konto erfolgreich hinzugefügt wurde. Mit der Benachrichtigung können Sie auch eine E-Mail-Adresse hinzufügen, um Benachrichtigungen zu erhalten, wenn die Social-Plattform-Authentifizierung demnächst abläuft.

>[!IMPORTANT]
>
>Audience Manager verarbeitet die Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Weitere Informationen zur Verlängerung der abgelaufenen Token finden Sie unter Erneuerung des Authentifizierungstokens.

## Schritt 6: Erstellen eines benutzerbasierten Ziels {#create-destination}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, gehen Sie zu **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** und klicken Sie auf **[!UICONTROL Create Destination]**.
1. Geben Sie im **[!UICONTROL Basic Information]** Abschnitt eine **[!UICONTROL Name]** und **[!UICONTROL Description]** für die neue Datenquelle ein und verwenden Sie die folgenden Einstellungen:
   * **[!UICONTROL Category]**: Integrierte Plattformen;
   * **[!UICONTROL Type]**: Volksansässige;
   * **[!UICONTROL Platform]**: Wählen Sie die personalbasierte Plattform aus, an die Sie Zielgruppensegmente senden möchten.
   * **[!UICONTROL Account]**: Wählen Sie das gewünschte Advertiser-Konto aus, das mit der ausgewählten Plattform verknüpft ist.
      ![create-destination](assets/pbd-create-destination.png)
1. Klicken Sie auf **[!UICONTROL Next]**.
1. Wählen Sie **[!UICONTROL Data Export Labels]** das Ziel aus, das Sie für dieses Ziel festlegen möchten.
1. Wählen Sie im **[!UICONTROL Configuration]** Abschnitt die Datenquelle aus, die Ihre Hash-Datenquellen enthält.
1. Wählen Sie im **[!UICONTROL Segment Mappings]** Abschnitt die Segmente aus, die Sie an dieses Ziel senden möchten. Dies sind die Segmente, die Sie in [Schritt 4 - Zielgruppensegmente](#create-audience-segments)erstellen erstellt haben.
1. Speichern Sie das Ziel.
