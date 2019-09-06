---
description: 'Diese Seite enthält Anleitungen zum Konfigurieren und Verwalten der Integration zwischen Audience Manager und benutzerbasierten Plattformen. '
seo-description: 'Diese Seite enthält Anleitungen zum Konfigurieren und Verwalten der Integration zwischen Audience Manager und benutzerbasierten Plattformen. '
seo-title: Authentifizierung mit benutzerbasierten Plattformen
solution: Audience Manager
title: Authentifizierung mit benutzerbasierten Plattformen
translation-type: tm+mt
source-git-commit: 05f334dc3d975a0fe18b93c844889e3edb2dfafa

---


# Authentifizierung mit benutzerbasierten Plattformen {#authentication-with-people-based-platforms}

Diese Seite enthält Anleitungen zum Konfigurieren und Verwalten der Integration zwischen Audience Manager und benutzerbasierten Plattformen.

>[!NOTE]
>Dies ist ein obligatorischer Schritt für benutzerbasierte Ziele, unabhängig vom Implementierungsszenario.

## Benutzerbasierte Plattformauthentifizierung konfigurieren {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und wechseln Sie zu **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer sozialen Plattform haben, sollten Sie diese auf dieser Seite auflisten. Andernfalls ist die Seite leer.
   ![personenbasierte Integration](assets/pbd-config.png)
1. Klicken Sie auf **[!UICONTROL Add Account]**.
1. Verwenden Sie das **[!UICONTROL People-Based Platform]** Dropdownmenü, um die Plattform auszuwählen, mit der Sie die Integration konfigurieren möchten.
   ![personenbasierte Plattform](assets/pbd-add.png)
1. Klicken **[!UICONTROL Confirm]** Sie auf, um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
1. Sobald Sie sich für Ihr Social-Plattform-Konto authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie Ihre zugeordneten Advertiserkonten sehen sollten. Wählen Sie das gewünschte Advertiserkonto aus und klicken **[!UICONTROL Confirm]** Sie auf.
1. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Ihnen mitzuteilen, ob das Konto erfolgreich hinzugefügt wurde. Die Benachrichtigung ermöglicht Ihnen außerdem, eine E-Mail-Adresse zu erhalten, um Benachrichtigungen zu erhalten, wenn die Authentifizierung der sozialen Plattform läuft.

## Authentifizierungs- und Benachrichtigungsverwaltung für Authentifizierungstoken {#token-expiration-notification}

Audience Manager verarbeitet die Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Die Gültigkeitsdauer von Token unterliegt den Integrationsregeln jeder sozialen Plattform. Nach Ablauf des Authentifizierungstokens kann Audience Manager Ihre Zielgruppensegmente nicht an Ihr Ziel senden. Um dieses Szenario zu vermeiden, empfehlen wir, Ihrer Integration mindestens eine Kontakt-E-Mail-Adresse hinzuzufügen, damit Sie benachrichtigt werden, sobald das Authentifizierungstoken läuft. In diesem Fall können Sie erneut authentifizieren, um sicherzustellen, dass das Ziel weiterhin Ihre Zielgruppensegmente erhält.

So fügen Sie vorhandenen Integrationen E-Mail-Adressen hinzu:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und wechseln Sie zu **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifizieren Sie die Integration, für die Sie Token-Ablaufbenachrichtigungen erhalten möchten, und klicken Sie auf das **[!UICONTROL Edit]** Symbol.
1. Geben Sie die E-Mail-Adressen ein, die durch Kommas getrennt werden sollen.
1. Klicken Sie auf **[!UICONTROL Save]**.

## Verlängerung des Authentifizierungstokens {#token-renewal}

Wenn ein Authentifizierungstoken abläuft, wird die Integration zwischen Audience Manager und der entsprechenden sozialen Plattform unterbrochen, sodass Audience Manager keine Zielgruppensegmente mehr an das Ziel senden kann. Die [!UICONTROL Integrated Accounts] Seite zeigt den Ablaufstatus jeder Integration in der [!UICONTROL Expiration] Spalte an und ermöglicht Ihnen, die Authentifizierung jederzeit zu verlängern.

So wird eine abgelaufene oder abgelaufene Authentifizierung verlängert:
1. Melden Sie sich bei Ihrem Audience Manager-Konto an und wechseln Sie zu **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifizieren Sie die Integration, für die Sie die Authentifizierung erneuern müssen. Abgelaufene Authentifizierungen sind markiert, [!UICONTROL Expired]während Authentifizierungen, die demnächst ablaufen sollen, die verbleibende Anzahl authentifizierter Tage anzeigen.
1. Klicken Sie in der Spalte auf das entsprechende **[!UICONTROL Renew]**[!UICONTROL Expiration] Symbol. Dadurch wird der **[!UICONTROL Renew Account]** Workflow ausgelöst, der Sie zurück durch die Authentifizierungsseite der sozialen Plattform führt. Nach der Authentifizierung wird das Token mit dem neuen Ablaufdatum erneuert.
   ![pbd-renew](assets/pbd-renew.png)
