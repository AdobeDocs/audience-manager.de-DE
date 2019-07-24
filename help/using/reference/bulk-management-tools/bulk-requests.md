---
description: Eine Massenanforderung gibt Daten zurück, die Sie mit den verschiedenen Kopfzeilen in den Arbeitsblättern "Aktualisieren" ," Erstellen" , "Schätzung" und" Löschen" verwenden können.
seo-description: Eine Massenanforderung gibt Daten zurück, die Sie mit den verschiedenen Kopfzeilen in den Arbeitsblättern "Aktualisieren" ," Erstellen" , "Schätzung" und" Löschen" verwenden können.
seo-title: Massenanforderungen
solution: Audience Manager
title: Massenanforderungen
uuid: 0192 d 26 a -4 cea -4 e 12-9 fea -388 b 92 b 382 f 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Requests{#bulk-requests}

Eine Massenanforderung gibt Daten zurück, die Sie mit den verschiedenen Kopfzeilen in den Arbeitsblättern "Aktualisieren" ," Erstellen" , "Schätzung" und" Löschen" verwenden können.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

The [!UICONTROL Request] worksheet does not have its own set of column headers and you don't need to copy IDs to any of the columns. Stattdessen werden Daten basierend auf der Aktionsschaltfläche zurückgegeben, auf die Sie in der Symbolleiste klicken. Außerdem gibt eine optionale Berichterstellungsfunktion eine Häufigkeitsanzahl für Pixel und eine eindeutige Benutzeranzahl für mehrere feste Zeitintervalle zurück.

To make bulk requests, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Request]** tab.
2. Klicken Sie in der Symbolleiste oben im Arbeitsblatt auf eine Anforderungsschaltfläche entsprechend den Daten, mit denen Sie arbeiten möchten. Sie können Folgendes abrufen:

   * Datenanbieter-IDs
   * Abgeleitete Signale
   * Zielzuordnungen
   * Regelbasierte und voreingestellte Eigenschaften
   * Segmente
   * Eigenschaften für Eigenschaften und Segmentordner
   The [!DNL Audience Manager] API writes bulk data back to the [!UICONTROL Request] worksheet.

>[!NOTE]
>
>In your results, the `createTime` and `updateTime` columns return data in exponential notation. Die zugrunde liegenden Datums-/Uhrzeitstempel werden in der UNIX UTC-Zeit aufgezeichnet. Derzeit kann das Arbeitsblatt Datums-/Zeitstempel nicht in lesbarer Form wiedergeben.

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
