---
description: 'Diese Seite enthält schrittweise Anleitungen zum Kombinieren von Offline-CRM-Daten mit Verhaltensdaten, die Sie bereits in Audience Manager haben, um neue Zielgruppensegmente zu erstellen, und diese Zielgruppensegmente an benutzerbasierte Ziele senden.  '
seo-description: 'Diese Seite enthält schrittweise Anleitungen zum Kombinieren von Offline-CRM-Daten mit Verhaltensdaten, die Sie bereits in Audience Manager haben, um neue Zielgruppensegmente zu erstellen, und diese Zielgruppensegmente an benutzerbasierte Ziele senden.   '
seo-title: Arbeitsablauf A - Personalisierung basierend auf allen Online-Aktivitäten zusammen mit Offline-Daten
solution: Audience Manager
title: Arbeitsablauf A - Personalisierung basierend auf allen Online-Aktivitäten zusammen mit Offline-Daten
translation-type: tm+mt
source-git-commit: 3fd24d4006ccbb14dad5cad10a66749a1cb97f47

---


# Arbeitsablauf A - Personalisierung basierend auf allen Online-Aktivitäten zusammen mit Offline-Daten {#workflow-a}

Diese Seite enthält Schritt-für-Schritt-Anleitungen zum Kombinieren von Offline [!DNL CRM] -Daten mit Verhaltensdaten, die Sie bereits in Audience Manager haben, um neue Zielgruppensegmente zu erstellen und diese Zielgruppensegmente zu [!DNL People-Based Destinations]senden.

## Schritt 1: Konfigurieren der Datenquelleneinstellungen {#configure-data-source-settings}

Je nachdem, ob Ihre [dpuuids](../../reference/ids-in-aam.md) klein sind, können Hash-E-Email-Adressen die Datenquelle konfigurieren, die die Hash-E-Email-Adressen speichert.

**Szenario 1: Ihre[dpuuids](../../reference/ids-in-aam.md)sind bereits Kleinbuchstaben, Hash-E-Email-Adressen.**

In diesem Fall müssen Sie die entsprechende Datenquelle als solche bezeichnen:

1. Wechseln Sie zu [!UICONTROL Audience Data] -&gt; [!UICONTROL Data Sources].
1. Suchen Sie die Datenquelle, die Ihre [dpuuids enthält](../../reference/ids-in-aam.md), und klicken Sie darauf.
1. Vergewissern Sie sich, dass die Option [!UICONTROL Cannot be tied to personally identifiable information] deaktiviert ist.
1. Speichern Sie die Datenquelleneinstellungen.

**Szenario 2: Ihre[dpuuids](../../reference/ids-in-aam.md)sind nicht Kleinbuchstaben, Hash-E-Email-Adressen.**

In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen, die Ihre Hash-E-Mail-Adressen speichert. Gehen Sie wie folgt vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und wechseln Sie zu **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]** und klicken **[!UICONTROL Add New]** Sie auf.
1. Geben Sie einen [!UICONTROL Name] und [!UICONTROL Description] für Ihre neue Datenquelle ein.
1. Wählen Sie im **[!UICONTROL ID Type]** Dropdown-Menü **[!UICONTROL Cross Device]** die Option.
1. Wählen Sie im **[!UICONTROL Data Source Settings]** Abschnitt die **[!UICONTROL Inbound]** Optionen und **[!UICONTROL Outbound]** Optionen aus und aktivieren Sie die **[!UICONTROL Share associated cross-device IDs in people-based destinations]** Option.
1. Verwenden Sie das Dropdownmenü, um die **[!UICONTROL Emails(SHA256, lowercased)]** Bezeichnung für diese Datenquelle auszuwählen.
   >[!IMPORTANT]
   >
   >Diese Option kennzeichnet nur die Datenquelle, die Daten enthält, die Daten mit diesem spezifischen Algorithmus enthalten. Audience Manager verhasst die Daten in diesem Schritt nicht. Stellen Sie sicher, dass die E-Mail-Adressen, die Sie in dieser Datenquelle speichern möchten, bereits mit dem [!DNL SHA256] Algorithmus hashing. Andernfalls können Sie es [!DNL People-Based Destinations]nicht verwenden.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

>[!NOTE]
>
> Häufig gestellte Fragen dazu, wie Sie Ihre Offline-Daten für benutzerbasierte Ziele in Audience Manager übernehmen, finden Sie unter [Datenonboarding](people-based-destinations-prerequisites.md#data-onboarding) .

## Schritt 2: Übereinstimmung mit dpuuids in Hash E-Mail-Adressen über dateibasierte ID-Synchronisierung {#match-ids-emails}

>[!IMPORTANT]
>
> Dieser Schritt gilt nur für [Szenario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) . Wenn Ihre vorhandenen [dpuuids](../../reference/ids-in-aam.md) bereits Hash-E-Email-Adressen sind, fahren Sie mit [Schritt 3 fort - Erstellen Sie eine Regel zum Profilzusammenführen für die Segmentierung](people-based-destinations-workflow-combined.md#create-merge-rule).

Nehmen wir an, Sie möchten Ihren vorhandenen [dpuuids](../../reference/ids-in-aam.md) den Hash-E-Email-Adressen aus der Tabelle unten zuordnen (rechts Spalte) und die Hash-E-Email-Adressen in der neuen Datenquelle speichern, die Sie in [Schritt 1 erstellt haben - Datenquelleneinstellungen konfigurieren](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (CRM-ID) | E-Mail-Adresse | Hash-E-Email-Adresse |
| --- | --- | --- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

Sie können bis zu 10 Hash-E-Email-Adressen zu einer einzelnen [DPUUID verknüpfen](../../reference/ids-in-aam.md). Trennen Sie dazu die Hash-E-Mail-Adressen durch ein Komma in der Synchronisierungsdatei.

In unserem Beispiel würden Sie jetzt zwei Datenquellen haben.

| Datenquellen-ID | Inhalt der Datenquelle |
| --- | --- |
| 999999 | Vorhandene dpuuids (CRM-IDs) |
| 987654 | Hash-E-Email-Adressen |

Ihre [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) hat folgende Inhalte:

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

Die [ID-Synchronisierungsdatei](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) muss diese Benennungsstruktur befolgen:

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

Im obigen Beispiel würde der Dateiname wie folgt aussehen:`c2c_id_999999_987654_1560431657.sync`


[Download-Beispieldatei hier](https://marketing.adobe.com/resources/help/en_US/aam/downloads/c2c_id_999999_987654_1560431657.sync)herunterladen.

## Schritt 3: Erstellen einer Regel zur Profilzusammenführung für die Segmentierung {#create-merge-rule}

Im nächsten Schritt wird eine neue Zusammenführungsregel erstellt, mit der Sie die Zielgruppensegmente erstellen können, die an Ihre persönlichen Ziele gesendet werden sollen.

>[!IMPORTANT]
>
> Wenn Sie bereits eine Regel mit den [!UICONTROL Current Authenticated Profiles] Optionen [!UICONTROL Last Authenticated Profiles] definiert haben, können Sie mit [Schritt 4 überspringen - Zielgruppensegmente erstellen](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und wechseln Sie zu **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Profile Merge Rules]**.
1. Klicken Sie auf **[!UICONTROL Add New Rule]**.
1. Geben Sie eine Regel für die Profilzusammenführung **[!UICONTROL Name]** ein und **[!UICONTROL Description]**.
1. Wählen Sie im **[!UICONTROL Profile Merge Rule Setup]** Abschnitt die **[!UICONTROL Current Authenticated Profiles]** Optionen **[!UICONTROL Last Authenticated Profiles]** aus.
1. Wählen Sie in der **[!UICONTROL Cross-Device Profile Options]** Liste die Datenquellen aus, auf denen die Segmentierung ausgeführt werden soll. Dies sollten die Datenquellen sein, die Ihre vorhandenen [dpuuids enthalten](../../reference/ids-in-aam.md).

## Schritt 4: Erstellen von Zielgruppensegmenten {#create-audience-segments}

Verwenden Sie zum Erstellen neuer Zielgruppensegmente den [Segmentaufbau](../segments/segment-builder.md). Wenn Sie über vorhandene Zielgruppensegmente verfügen, an [!DNL People-Based Destinations]die Sie senden möchten, gehen Sie zu [Schritt 5 - Konfigurieren Sie die benutzerbasierte Plattformauthentifizierung](people-based-destinations-workflow-combined.md#configure-authentication).

## Schritt 5: Authentifizierung auf der Benutzerbasierten Plattform konfigurieren {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und wechseln Sie zu **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer sozialen Plattform haben, sollten Sie diese auf dieser Seite auflisten. Andernfalls ist die Seite leer.
   ![personenbasierte Integration](assets/pbd-config.png)
1. Klicken Sie auf **[!UICONTROL Add Account]**.
1. Verwenden Sie das **[!UICONTROL People-Based Platform]** Dropdownmenü, um die Plattform auszuwählen, mit der Sie die Integration konfigurieren möchten.
   ![personenbasierte Plattform](assets/pbd-add.png)
1. Klicken **[!UICONTROL Confirm]** Sie auf, um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
1. Sobald Sie sich für Ihr Social-Plattform-Konto authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie Ihre zugeordneten Advertiserkonten sehen sollten. Wählen Sie das gewünschte Advertiserkonto aus und klicken **[!UICONTROL Confirm]** Sie auf.
1. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Ihnen mitzuteilen, ob das Konto erfolgreich hinzugefügt wurde. Die Benachrichtigung ermöglicht Ihnen außerdem, eine E-Mail-Adresse zu erhalten, um Benachrichtigungen zu erhalten, wenn die Authentifizierung der sozialen Plattform läuft.

>[!IMPORTANT]
>
>Ein Udience Manager nutzt die Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Weitere Informationen zum Verlängern abgelaufener Token finden Sie unter Erneuerung der Authentifizierungstoken.

## Schritt 6: Erstellen eines benutzerbasierten Ziels {#create-destination}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an, wechseln Sie zu **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Destinations]** und klicken **[!UICONTROL Create Destination]** Sie auf.
1. Geben Sie im **[!UICONTROL Basic Information]** Abschnitt einen **[!UICONTROL Name]** und **[!UICONTROL Description]** für Ihre neue Datenquelle ein und verwenden Sie die folgenden Einstellungen:
   * **[!UICONTROL Category]**: Integrierte Plattformen;
   * **[!UICONTROL Type]**: Personenbasiert;
   * **[!UICONTROL Platform]**: Wählen Sie die benutzerbasierte Plattform, an die Sie Zielgruppensegmente senden möchten.
   * **[!UICONTROL Account]**: Wählen Sie das gewünschte Advertiserkonto aus, das der ausgewählten Plattform zugeordnet ist.
      ![create-destination](assets/pbd-create-destination.png)
1. Klicken Sie auf **[!UICONTROL Next]**.
1. Wählen **[!UICONTROL Data Export Labels]** Sie die gewünschte Einstellung für dieses Ziel aus.
1. Wählen Sie im **[!UICONTROL Configuration]** Abschnitt die Datenquelle aus, die Ihre Hash-Datenquellen enthält.
1. Wählen Sie im **[!UICONTROL Segment Mappings]** Abschnitt die Segmente aus, die Sie an dieses Ziel senden möchten. Dies wären die Segmente, die Sie in [Schritt 4 erstellt haben - Erstellen von Zielgruppensegmenten](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Speichern Sie das Ziel.
