---
description: 'Diese Seite enthält Anleitungen zum Konfigurieren und Verwalten der Integration zwischen Audience Manager und benutzerbasierten Plattformen. '
seo-description: 'Diese Seite enthält Anleitungen zum Konfigurieren und Verwalten der Integration zwischen Audience Manager und benutzerbasierten Plattformen. '
seo-title: Authentifizierung mit benutzerbasierten Plattformen
solution: Audience Manager
title: Authentifizierung mit benutzerbasierten Plattformen
translation-type: tm+mt
source-git-commit: 6093def9c5853572c064a4e398d5e328bcb9d181

---


# Authentifizierung mit benutzerbasierten Plattformen {#authentication-with-people-based-platforms}

Diese Seite enthält Anleitungen zum Konfigurieren und Verwalten Ihrer Integration zwischen Audience Manager und benutzerbasierten Plattformen.

>[!NOTE]
>Dies ist ein obligatorischer Schritt für benutzerspezifische Ziele, unabhängig von Ihrem Implementierungsszenario.

## Personalisierte Plattformauthentifizierung konfigurieren {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**. Wenn Sie eine zuvor konfigurierte Integration mit einer sozialen Plattform haben, sollte diese auf dieser Seite aufgeführt werden. Andernfalls ist die Seite leer.
   ![people-based-integration](assets/pbd-config.png)
1. Klicken Sie auf **[!UICONTROL Add Account]**.
1. Verwenden Sie das **[!UICONTROL People-Based Platform]** Dropdownmenü, um die Plattform auszuwählen, mit der Sie die Integration konfigurieren möchten.
   ![people-based-platform](assets/pbd-add.png)
1. Klicken Sie auf **[!UICONTROL Confirm]** , um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
1. Nachdem Sie sich bei Ihrem Social-Plattform-Konto authentifiziert haben, werden Sie zu Audience Manager weitergeleitet, wo Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das gewünschte Advertiser-Konto aus und klicken Sie auf **[!UICONTROL Confirm]**.
1. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Sie darüber zu informieren, ob das Konto erfolgreich hinzugefügt wurde. Mit der Benachrichtigung können Sie auch eine E-Mail-Adresse für Kontaktpersonen hinzufügen, um Benachrichtigungen von Adobe zu erhalten, wenn die Social-Plattform-Authentifizierung demnächst abläuft.

## Ablauf und Benachrichtigungsverwaltung für Authentifizierungstoken {#token-expiration-notification}

Audience Manager verarbeitet Ihre Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Die Gültigkeitsdauer des Tokens unterliegt den Integrationsregeln jeder sozialen Plattform. Nach Ablauf des Authentifizierungstokens kann Audience Manager Ihre Zielgruppensegmente nicht mehr an Ihr Ziel senden. Um dieses Szenario zu vermeiden, sollten Sie mindestens eine Kontakt-E-Mail-Adresse zu Ihrer Integration hinzufügen, damit Sie benachrichtigt werden, sobald das Authentifizierungstoken abläuft. In diesem Fall können Sie sich erneut authentifizieren, um sicherzustellen, dass das Ziel weiterhin Ihre Zielgruppensegmente erhält.

So fügen Sie vorhandenen Integrationen E-Mail-Adressen hinzu:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifizieren Sie die Integration, für die Sie Token-Ablaufbenachrichtigungen erhalten möchten, und klicken Sie auf das **[!UICONTROL Edit]** Symbol.
1. Geben Sie die E-Mail-Adressen ein, an die Sie Benachrichtigungen zum Ablauf von Token erhalten möchten, getrennt durch Kommas.
1. Klicken Sie auf **[!UICONTROL Save]**.

## Erneuerung des Authentifizierungstokens {#token-renewal}

Wenn ein Authentifizierungstoken abläuft, wird die Integration zwischen Audience Manager und der entsprechenden sozialen Plattform unterbrochen, sodass Audience Manager keine Zielgruppensegmente mehr an das Ziel senden kann. Die [!UICONTROL Integrated Accounts] Seite zeigt Ihnen den Ablaufstatus jeder Integration in der [!UICONTROL Expiration] Spalte und ermöglicht Ihnen, die Authentifizierung jederzeit zu verlängern.

So verlängern Sie eine abgelaufene oder kurz vor Ablauf vergangene Authentifizierung:
1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** &gt; **[!UICONTROL Integrated Accounts]**.
1. Identifizieren Sie die Integration, für die Sie die Authentifizierung erneuern müssen. Abgelaufene Authentifizierungen werden als [!UICONTROL Expired]gekennzeichnet, während Authentifizierungen, die demnächst ablaufen, die verbleibende Anzahl authentifizierter Tage anzeigen.
1. Klicken Sie auf das entsprechende **[!UICONTROL Renew]** Symbol in der [!UICONTROL Expiration] Spalte. Dadurch wird der **[!UICONTROL Renew Account]** Workflow ausgelöst, der Sie durch die Authentifizierungsseite der sozialen Plattform zurückführt. Nach der Authentifizierung wird das Token mit dem neuen Ablaufdatum erneuert.
   ![pbd-renew](assets/pbd-renew.png)
