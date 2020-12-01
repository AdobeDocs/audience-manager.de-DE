---
description: 'Diese Seite enthält Anleitungen zum Konfigurieren und Verwalten der Integration zwischen Audience Manager- und benutzerbasierten Plattformen. '
seo-description: 'Diese Seite enthält Anleitungen zum Konfigurieren und Verwalten der Integration zwischen Audience Manager- und benutzerbasierten Plattformen. '
seo-title: Authentifizierung mit benutzerbezogenen Plattformen
solution: Audience Manager
title: Authentifizierung mit benutzerbezogenen Plattformen
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 2%

---


# Authentifizierung mit benutzerbezogenen Plattformen {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Dieser Artikel enthält eine Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist eine Rechtsberatung. Bitte konsultieren Sie Ihren eigenen Rechtsbeistand für Rechtsberatung.

Diese Seite enthält Anleitungen zum Konfigurieren und Verwalten Ihrer Integration.
zwischen Audience Manager- und Personalplattformen.

>[!NOTE]
>Dies ist ein obligatorischer Schritt für benutzerspezifische Ziele, unabhängig von Ihrem Implementierungsszenario.

## Personenbasierte Plattformauthentifizierung konfigurieren {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer sozialen Plattform haben, sollte diese auf dieser Seite aufgeführt werden. Andernfalls ist die Seite leer.
   ![people-based-integration](assets/pbd-config.png)
2. Klicken **[!UICONTROL Add Account]**.
3. Verwenden Sie das Dropdownmenü **[!UICONTROL People-Based Platform]**, um die Plattform auszuwählen, mit der Sie die Integration konfigurieren möchten.
   ![people-based-platform](assets/pbd-add.png)
4. Klicken Sie auf **[!UICONTROL Confirm]**, um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
5. Nachdem Sie sich bei Ihrem Social-Plattform-Konto authentifiziert haben, werden Sie an den Audience Manager weitergeleitet, wo Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das gewünschte Advertiser-Konto aus und klicken Sie auf **[!UICONTROL Confirm]**.
6. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Sie darüber zu informieren, ob das Konto erfolgreich hinzugefügt wurde. Mit der Benachrichtigung können Sie auch eine E-Mail-Adresse hinzufügen, um Benachrichtigungen von der Adobe zu erhalten, wenn die Social-Plattform-Authentifizierung demnächst abläuft.

## Ablauf und Benachrichtigungsverwaltung für Authentifizierungstoken {#token-expiration-notification}

Audience Manager verwaltet Ihre Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Die Gültigkeitsdauer des Tokens unterliegt den Integrationsregeln jeder sozialen Plattform. Nach Ablauf des Authentifizierungstokens kann Audience Manager Ihre Audiencen nicht mehr an Ihr Ziel senden. Um dieses Szenario zu vermeiden, sollten Sie mindestens eine Kontakt-E-Mail-Adresse zu Ihrer Integration hinzufügen, damit Sie benachrichtigt werden, sobald das Authentifizierungstoken abläuft. In diesem Fall können Sie sich erneut authentifizieren, um sicherzustellen, dass das Ziel weiterhin Ihre Audiencen erhält.

So fügen Sie vorhandenen Integrationen E-Mail-Adressen hinzu:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifizieren Sie die Integration, für die Sie Token-Ablaufbenachrichtigungen erhalten möchten, und klicken Sie auf das Symbol **[!UICONTROL Edit]**.
1. Geben Sie die E-Mail-Adressen ein, an die Sie Benachrichtigungen zum Ablauf von Token erhalten möchten, getrennt durch Kommas.
1. Klicken **[!UICONTROL Save]**.

## Erneuerung des Authentifizierungstokens {#token-renewal}

Wenn ein Authentifizierungstoken abläuft, wird die Integration zwischen Audience Manager und der entsprechenden sozialen Plattform unterbrochen, sodass Audience Manager keine Audiencen mehr an das Ziel senden kann. Die Seite [!UICONTROL Integrated Accounts] zeigt den Ablaufstatus jeder Integration in der Spalte [!UICONTROL Expiration] an und ermöglicht es Ihnen, die Authentifizierung jederzeit zu verlängern.

So verlängern Sie eine abgelaufene oder kurz vor Ablauf vergangene Authentifizierung:
1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifizieren Sie die Integration, für die Sie die Authentifizierung erneuern müssen. Abgelaufene Authentifizierungen werden als [!UICONTROL Expired] markiert, während bei bald ablaufenden Authentifizierungen die verbleibende Anzahl authentifizierter Tage angezeigt wird.
1. Klicken Sie auf das entsprechende **[!UICONTROL Renew]**-Symbol in der Spalte [!UICONTROL Expiration]. Dadurch wird der **[!UICONTROL Renew Account]**-Arbeitsablauf ausgelöst, der Sie zurück durch die Authentifizierungsseite der sozialen Plattform führt. Nach der Authentifizierung wird das Token mit dem neuen Ablaufdatum erneuert.
   ![pbd-renew](assets/pbd-renew.png)
