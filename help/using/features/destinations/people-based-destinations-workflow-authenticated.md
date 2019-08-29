---
description: 'Diese Seite enthält schrittweise Anleitungen zum Kombinieren von Offline-CRM-Daten mit Echtzeit-Verhaltensdaten für authentifizierte Benutzer, um Zielgruppensegmente zu erstellen und diese Zielgruppensegmente an benutzerbasierte Ziele zu senden. '
seo-description: 'Diese Seite enthält schrittweise Anleitungen zum Kombinieren von Offline-CRM-Daten mit Echtzeit-Verhaltensdaten für authentifizierte Benutzer, um Zielgruppensegmente zu erstellen und diese Zielgruppensegmente an benutzerbasierte Ziele zu senden.  '
seo-title: Arbeitsablauf C - Personalisierung basierend auf authentifizierten Aktivitäten mit Offline-Daten
solution: Audience Manager
title: Arbeitsablauf C - Personalisierung basierend auf authentifizierten Aktivitäten mit Offline-Daten
translation-type: tm+mt
source-git-commit: 11663e962254bbcab90105d72af003b2a7056744

---


# Arbeitsablauf C - Personalisierung basierend auf authentifizierten Aktivitäten mit Offline-Daten {#workflow-c}

Diese Seite enthält schrittweise Anleitungen zum Kombinieren von Offline [!DNL CRM] -Daten mit Echtzeit-Verhaltensdaten für authentifizierte Benutzer, um Zielgruppensegmente zu erstellen und diese Zielgruppensegmente zu [!DNL People-Based Destinations]senden.

## Schritt 1: Konfigurieren der Datenquelleneinstellungen {#configure-data-source-settings}

Je nachdem, ob Ihre [dpuuids](../../reference/ids-in-aam.md) klein sind, können Hash-E-Email-Adressen die Datenquelle konfigurieren, die die Hash-E-Email-Adressen speichert.

**Szenario 1: Ihre[dpuuids](../../reference/ids-in-aam.md)sind bereits Kleinbuchstaben, Hash-E-Email-Adressen.**

Überspringen Sie in diesem Fall [Schritt 5 - Benutzerbasierte Plattformauthentifizierung konfigurieren](#configure-authentication).

**Szenario 2: Ihre[dpuuids](../../reference/ids-in-aam.md)sind nicht Kleinbuchstaben, Hash-E-Email-Adressen.**

In diesem Fall müssen Sie eine neue geräteübergreifende Datenquelle erstellen, die Ihre Hash-E-Mail-Adressen speichert. Gehen Sie wie folgt vor:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und wechseln **[!UICONTROL Audience Data]** Sie zu -&gt; **[!UICONTROL Data Sources]** und klicken **[!UICONTROL Add New]** Sie auf.
1. Geben Sie einen **[!UICONTROL Name]** und **[!UICONTROL Description]** für Ihre neue Datenquelle ein.
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

## Schritt 2: Deklarierte IDs verwenden, um dpuuids in Hash E-Mail-Adressen über Echtzeit-HTTP-Aufrufe abzugleichen {#match-email-addresses}

Um authentifizierte Benutzer für regelbasierte Eigenschaften qualifizieren zu können, müssen Sie die Eigenschaft Eigenschaften über [deklarierte IDs senden](../declared-ids.md).

### Beispiel 

Nehmen wir an, Sie haben die beiden folgenden Datenquellen erstellt.

| Datenquellen-ID | Inhalt der Datenquelle |
|---|---|
| 999999 | Vorhandene dpuuids (CRM-IDs) |
| 987654 | Hash-E-Email-Adressen |

Anschließend möchten Sie die folgenden CRM-IDs für die Eigenschaft in der Tabelle qualifizieren.

| DPUUID (CRM-ID) | E-Mail-Adresse | Hash-E-Email-Adresse | Trait- |
|---|---|---|---|
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

Ihre deklarierte ID sollte mit der folgenden Syntax übereinstimmen:

`https://yourDomain.demdex.net/event?d_cid_ic=myHashedEmailDataSourceID%01myHashedEmail&d_cid_ic=myCrmDataSourceID%01myCRMID&key=value`

Im obigen Beispiel sollte der deklarierte ID-Aufruf wie folgt aussehen:

`https://yourDomain.demdex.net/event?d_cid_ic=987654%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=999999%0168079982765673198504052656074456196039&location=US`

## Schritt 3: Erstellen einer Regel zur Profilzusammenführung für die Segmentierung {#create-profile-merge-rule-segmentation}

Im nächsten Schritt wird eine neue Zusammenführungsregel erstellt, die Ihnen dabei hilft, die Zielgruppensegmente zu erstellen, [!DNL People-Based Destinations]die an Sie gesendet werden sollen.

>[!IMPORTANT]
>
>Wenn Sie bereits eine Regel mit den **[!UICONTROL Current Authenticated Profiles]** Optionen **[!UICONTROL Last Authenticated Profiles]** definiert haben, können Sie mit [Schritt 4 überspringen - Zielgruppensegmente erstellen](#create-audience-segments).

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Klicken Sie auf **[!UICONTROL Add New Rule]**.
3. Geben Sie eine Regel für die Profilzusammenführung **[!UICONTROL Name]** ein und **[!UICONTROL Description]**.
4. Wählen Sie im **[!UICONTROL Profile Merge Rule Setup]** Abschnitt die **[!UICONTROL All Cross-Device Profiles]** Regel aus der **[!UICONTROL Cross-Device Options]** Liste aus.
5. Wählen Sie in der **[!UICONTROL Cross-Device Profile Options]** Liste die Datenquellen aus, auf denen die Segmentierung ausgeführt werden soll. Dies sollten die Datenquellen sein, die Ihre vorhandenen dpuuids enthalten.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Schritt 4: Erstellen von Zielgruppensegmenten {#create-audience-segments}

Verwenden Sie zum Erstellen neuer Segmente den [Segmentaufbau](../segments/segment-builder.md). Wenn Sie über vorhandene Zielgruppensegmente verfügen, an [!DNL People-Based Destinations]die Sie senden möchten, gehen Sie zu [Schritt 5 - Konfigurieren Sie die benutzerbasierte Plattformauthentifizierung](#configure-authentication).

## Schritt 5: Authentifizierung auf der Benutzerbasierten Plattform konfigurieren {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und wechseln Sie zu **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer sozialen Plattform haben, sollten Sie diese auf dieser Seite auflisten. Andernfalls ist die Seite leer.
   ![personenbasierte Integration](assets/pbd-config.png)
2. Klicken Sie auf **[!UICONTROL Add Account]**.
3. Verwenden Sie das **[!UICONTROL People-Based Platform]** Dropdownmenü, um die Plattform auszuwählen, mit der Sie die Integration konfigurieren möchten.
   ![personenbasierte Plattform](assets/pbd-add.png)
4. Klicken **[!UICONTROL Confirm]** Sie auf, um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
5. Sobald Sie sich für Ihr Social-Plattform-Konto authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie Ihre zugeordneten Advertiserkonten sehen sollten. Wählen Sie das gewünschte Advertiserkonto aus und klicken **[!UICONTROL Confirm]** Sie auf.
6. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Ihnen mitzuteilen, ob das Konto erfolgreich hinzugefügt wurde. Die Benachrichtigung ermöglicht Ihnen außerdem, eine E-Mail-Adresse zu erhalten, um Benachrichtigungen zu erhalten, wenn die Authentifizierung der sozialen Plattform läuft.

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
1. Wählen Sie im **[!UICONTROL Segment Mappings]** Abschnitt die Segmente aus, die Sie an dieses Ziel senden möchten. Dies wären die Segmente, die Sie in [Schritt 4 erstellt haben - Erstellen von Zielgruppensegmenten](#create-audience-segments).
1. Speichern Sie das Ziel.
