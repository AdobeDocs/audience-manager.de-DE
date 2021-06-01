---
description: 'Diese Seite enthält Anleitungen zum Konfigurieren und Verwalten der Integration zwischen Audience Manager- und benutzerbezogenen Plattformen. '
seo-description: 'Diese Seite enthält Anleitungen zum Konfigurieren und Verwalten der Integration zwischen Audience Manager- und benutzerbezogenen Plattformen. '
seo-title: Authentifizierung mit benutzerbezogenen Plattformen
solution: Audience Manager
title: Authentifizierung mit benutzerbezogenen Plattformen
feature: Benutzerbasierte Ziele
exl-id: d3e136d0-2b06-412a-9b9b-75b661c9aa14
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 2%

---

# Authentifizierung mit benutzerbezogenen Plattformen {#authentication-with-people-based-platforms}

>[!IMPORTANT]
>Dieser Artikel enthält die Produktdokumentation, die Sie durch die Einrichtung und Nutzung dieser Funktion führen soll. Nichts in diesem Dokument ist Rechtsberatung. Wenden Sie sich an Ihren Rechtsbeistand, um rechtliche Hinweise zu erhalten.

Auf dieser Seite finden Sie Anleitungen zum Konfigurieren und Verwalten Ihrer Integration.
zwischen Audience Manager- und benutzerbezogenen Plattformen.

>[!NOTE]
>Dies ist ein obligatorischer Schritt für personenbasierte Ziele, unabhängig von Ihrem Implementierungsszenario.

## Konfigurieren der personenbasierten Plattformauthentifizierung {#configure-authentication}

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Wenn Sie bereits eine Integration mit einer sozialen Plattform konfiguriert haben, sollte diese auf dieser Seite aufgeführt sein. Andernfalls ist die Seite leer.
   ![People-based-integration](assets/pbd-config.png)
2. Klicken **[!UICONTROL Add Account]**.
3. Wählen Sie im Dropdown-Menü **[!UICONTROL People-Based Platform]** die Plattform aus, mit der Sie die Integration konfigurieren möchten.
   ![people-based-platform](assets/pbd-add.png)
4. Klicken Sie auf **[!UICONTROL Confirm]** , um zur Authentifizierungsseite der ausgewählten Plattform umgeleitet zu werden.
5. Nachdem Sie sich bei Ihrem Social-Plattform-Konto authentifiziert haben, werden Sie zu dem Audience Manager weitergeleitet, in dem Sie die zugehörigen Advertiser-Konten sehen sollten. Wählen Sie das Advertiser-Konto aus, das Sie verwenden möchten, und klicken Sie auf **[!UICONTROL Confirm]**.
6. Audience Manager zeigt oben auf der Seite eine Benachrichtigung an, um Sie darüber zu informieren, ob das Konto erfolgreich hinzugefügt wurde. Mit der Benachrichtigung können Sie auch eine Kontakt-E-Mail-Adresse hinzufügen, um Benachrichtigungen von Adobe zu erhalten, wenn die Social-Plattform-Authentifizierung bald abläuft.

## Gültigkeit und Benachrichtigungsverwaltung von Authentifizierungstoken {#token-expiration-notification}

Audience Manager verarbeitet Ihre Integration mit sozialen Plattformen über Authentifizierungstoken, die nach einer bestimmten Zeit ablaufen. Die Gültigkeitsdauer des Tokens unterliegt den Integrationsregeln jeder sozialen Plattform. Sobald das Authentifizierungstoken abläuft, kann Audience Manager Ihre Zielgruppensegmente nicht mehr an Ihr Ziel senden. Um dieses Szenario zu vermeiden, empfehlen wir, mindestens eine Kontakt-E-Mail-Adresse zu Ihrer Integration hinzuzufügen, damit Sie benachrichtigt werden, sobald das Authentifizierungstoken abläuft. In diesem Fall können Sie sich erneut authentifizieren, um sicherzustellen, dass das Ziel weiterhin Ihre Zielgruppensegmente erhält.

So fügen Sie vorhandenen Integrationen E-Mail-Adressen hinzu:

1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifizieren Sie die Integration, für die Sie Benachrichtigungen zum Ablauf von Token erhalten möchten, und klicken Sie auf das Symbol **[!UICONTROL Edit]**.
1. Geben Sie die E-Mail-Adressen ein, an die Sie Benachrichtigungen zum Ablauf von Token erhalten möchten, getrennt durch Kommas.
1. Klicken **[!UICONTROL Save]**.

## Authentifizierungstoken Erneuerung {#token-renewal}

Wenn ein Authentifizierungstoken abläuft, wird die Integration zwischen Audience Manager und der entsprechenden Social-Plattform unterbrochen, sodass Audience Manager keine Zielgruppensegmente mehr an das Ziel senden können. Die Seite [!UICONTROL Integrated Accounts] zeigt den Ablaufstatus jeder Integration in der Spalte [!UICONTROL Expiration] an und ermöglicht es Ihnen, die Authentifizierung jederzeit zu verlängern.

So verlängern Sie eine abgelaufene oder nahezu ablaufende Authentifizierung:
1. Melden Sie sich bei Ihrem Audience Manager-Konto an und gehen Sie zu **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**.
1. Identifizieren Sie die Integration, für die Sie die Authentifizierung erneuern müssen. Abgelaufene Authentifizierungen werden als [!UICONTROL Expired] markiert, während bei bald ablaufenden Authentifizierungen die verbleibende Anzahl authentifizierter Tage angezeigt wird.
1. Klicken Sie in der Spalte [!UICONTROL Expiration] auf das entsprechende **[!UICONTROL Renew]**-Symbol. Dadurch wird der Workflow **[!UICONTROL Renew Account]** Trigger, der Sie zurück zur Authentifizierungsseite der Social-Plattform bringt. Nach der Authentifizierung wird das Token mit dem neuen Ablaufdatum erneuert.
   ![pbd-renew](assets/pbd-renew.png)
