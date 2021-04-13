---
description: 'Diese Seite enthält eine schrittweise Anleitung zum Kombinieren von Offline-CRM-Daten mit Echtzeit-Verhaltensdaten für authentifizierte Audiencen, um diese Audiencen zu erstellen, und zum anschließenden Senden dieser Segmente an benutzerbasierte Ziele. '
seo-description: 'Diese Seite enthält eine schrittweise Anleitung zum Kombinieren von Offline-CRM-Daten mit Echtzeit-Verhaltensdaten für authentifizierte Audiencen, um diese Audiencen zu erstellen, und zum anschließenden Senden dieser Segmente an benutzerbasierte Ziele.  '
seo-title: Workflow C - Personalisierung basierend auf authentifizierter Aktivität in Kombination mit Offline-Daten
solution: Audience Manager
title: Workflow C - Personalisierung basierend auf authentifizierter Aktivität in Kombination mit Offline-Daten
feature: Benutzerbasierte Ziele
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 5%

---

# Workflow C - Personalisierung basierend auf authentifizierter Aktivität in Kombination mit Offline-Daten {#workflow-c}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Diese Seite enthält eine schrittweise Anleitung zum Kombinieren von Offline- [!DNL CRM]-Daten mit Echtzeitverhaltensdaten für authentifizierte Audiencen zur Erstellung von Segmenten und zum Senden dieser Audiencen an [!DNL People-Based Destinations].

## Schritt 1: Konfigurieren der Datenquelleneinstellungen {#configure-data-source-settings}

Je nachdem, ob Ihre [DPUUIDs](../../reference/ids-in-aam.md) in Kleinbuchstaben und Hash-E-Mail-Adressen vorliegen, müssen Sie möglicherweise die Datenquelle konfigurieren, in der die Hash-E-Mail-Adressen gespeichert werden.

 

**Szenario 1: Ihre  [](../../reference/ids-in-aam.md) DPUUIDs sind bereits in Kleinbuchstaben, mit Hash-E-Mail-Adressen.**

In diesem Fall gehen Sie zu [Schritt 5 - Personenbasierte Plattformauthentifizierung konfigurieren](#configure-authentication).

 

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

## Schritt 2: Verwenden Sie deklarierte IDs, um DPUUIDs mit Hash-E-Mail-Adressen über HTTP-Aufrufe in Echtzeit abzugleichen. {#match-email-addresses}

Um authentifizierte Benutzer für regelbasierte Eigenschaften zu qualifizieren, müssen Sie die Eigenschaftenqualifikation über [deklarierte IDs](../declared-ids.md) senden.

### Beispiel

Angenommen, Sie haben die folgenden beiden Datenquellen erstellt.

| Datenquellen-ID | Datenquelleninhalte |
| -------------- | -------------------------- |
| 999999 | Vorhandene DPUUIDs (CRM-IDs) |
| 987654 | Hash-E-Mail-Adressen |

 

Anschließend sollten Sie die unten stehenden CRM-IDs für die Eigenschaft in der Tabelle qualifizieren.

| DPUUID (CRM-ID) | E-Mail-Adresse | Hash-E-Mail-Adresse | Eigenschaft |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041 149 | location = US |

 

Ihre deklarierte ID sollte der folgenden Syntax entsprechen:

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

Im oben stehenden Beispiel sollte der deklarierte ID-Aufruf wie folgt aussehen:

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Schritt 3: Erstellen einer Profil Merge Rule for Segmentation {#create-profile-merge-rule-segmentation}

Im nächsten Schritt erstellen Sie eine neue Zusammenführungsregel, die Ihnen hilft, die an Ihr [!DNL People-Based Destinations] zu sendenden Audiencen zu erstellen.

>[!IMPORTANT]
>
>Wenn Sie bereits eine Regel mit den Optionen **[!UICONTROL Current Authenticated Profiles]** oder **[!UICONTROL Last Authenticated Profiles]** definiert haben, können Sie zu [Schritt 4 - Audience-Segmente erstellen](#create-audience-segments) überspringen.

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Klicken **[!UICONTROL Add New Rule]**.
3. Geben Sie eine Profil Mergeregel **[!UICONTROL Name]** und **[!UICONTROL Description]** ein.
4. Wählen Sie im Abschnitt **[!UICONTROL Profile Merge Rule Setup]** die **[!UICONTROL Current Authenticated Profiles]**- oder **[!UICONTROL Last Authenticated Profiles]**-Regel aus der **[!UICONTROL Cross-Device Options]**-Liste.
5. Wählen Sie in der Liste **[!UICONTROL Cross-Device Profile Options]** die Datenquellen aus, für die Sie die Segmentierung ausführen möchten. Dies sollten die Datenquellen sein, die Ihre vorhandenen DPUUIDs enthalten.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Schritt 4: Erstellen von Audiencen-Segmenten {#create-audience-segments}

Verwenden Sie zum Erstellen neuer Segmente den [Segmentaufbau](../segments/segment-builder.md). Wenn Sie bereits Audiencen haben, die Sie an [!DNL People-Based Destinations] senden möchten, gehen Sie zu [Schritt 5 - Personenbasierte Plattformauthentifizierung konfigurieren](#configure-authentication).

## Schritt 5: Personenbasierte Plattformauthentifizierung konfigurieren {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer sozialen Plattform haben, sollte diese auf dieser Seite aufgeführt werden. Andernfalls ist die Seite leer.
   ![people-based-integration](assets/pbd-config.png)
2. Klicken **[!UICONTROL Add Account]**.
3. Verwenden Sie das Dropdownmenü **[!UICONTROL People-Based Platform]**, um die Plattform auszuwählen, mit der Sie die Integration konfigurieren möchten.
   ![people-based-platform](assets/pbd-add.png)
4. Klicken Sie auf **[!UICONTROL Confirm]**, um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
5. Nachdem Sie sich bei Ihrem Social-Plattform-Konto authentifiziert haben, werden Sie an den Audience Manager weitergeleitet, wo Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das gewünschte Advertiser-Konto aus und klicken Sie auf **[!UICONTROL Confirm]**.
6. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Sie darüber zu informieren, ob das Konto erfolgreich hinzugefügt wurde. Mit der Benachrichtigung können Sie auch eine E-Mail-Adresse hinzufügen, um Benachrichtigungen zu erhalten, wenn die Social-Plattform-Authentifizierung demnächst abläuft.

>[!IMPORTANT]
>
>Audience Manager verarbeitet die Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Weitere Informationen zur Verlängerung der abgelaufenen Token finden Sie unter Erneuerung des Authentifizierungstokens.

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
1. Wählen Sie im Abschnitt **[!UICONTROL Segment Mappings]** die Segmente aus, die Sie an dieses Ziel senden möchten. Dies sind die Segmente, die Sie unter [Schritt 4 - Erstellen von Audiencen-Segmenten](#create-audience-segments) erstellt haben.
1. Speichern Sie das Ziel.
