---
description: Eine Massenanforderung gibt Daten zurück, die Sie mit den verschiedenen Headern in den Arbeitsblättern "Aktualisieren", "Erstellen", "Schätzung"und "Löschen"verwenden können.
seo-description: Eine Massenanforderung gibt Daten zurück, die Sie mit den verschiedenen Headern in den Arbeitsblättern "Aktualisieren", "Erstellen", "Schätzung"und "Löschen"verwenden können.
seo-title: Massenanforderungen
solution: Audience Manager
title: Massenanforderungen
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Massenanforderungen{#bulk-requests}

Eine Massenanforderung gibt Daten zurück, die Sie mit den verschiedenen Headern in den Arbeitsblättern "Aktualisieren", "Erstellen", "Schätzung"und "Löschen"verwenden können.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>Die [!UICONTROL Bulk Management Tools] werden *nicht* von unterstützt [!DNL Audience Manager]. Dieses Tool wird nur aus praktischen Gründen und als Höflichkeit zur Verfügung gestellt. Bei Massenänderungen sollten Sie stattdessen mit den [Audience Manager-APIs](../../api/rest-api-main/aam-api-getting-started.md) arbeiten. [In der Benutzeroberfläche zugewiesene RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) werden berücksichtigt [!DNL Audience Manager] [!UICONTROL Bulk Management Tools].

Das [!UICONTROL Request] Arbeitsblatt hat keinen eigenen Satz von Spaltenüberschriften und Sie müssen keine IDs in eine der Spalten kopieren. Stattdessen werden Daten basierend auf der Aktionsschaltfläche zurückgegeben, auf die Sie in der Symbolleiste klicken. Außerdem gibt eine optionale Berichterstellungsfunktion eine Frequenz-Anzahl für Pixelfeuer und eine eindeutige Benutzeranzahl für mehrere feste Zeitintervalle zurück.

Um Massenanforderungen zu erstellen, öffnen Sie das [!UICONTROL Bulk Management Tools] Arbeitsblatt und:

1. Click the **[!UICONTROL Request]** tab.
2. Klicken Sie in der Symbolleiste oben im Arbeitsblatt auf eine Anforderungsschaltfläche, die den Daten entspricht, mit denen Sie arbeiten möchten. Sie können Folgendes anfordern:

   * Datenanbieter-IDs
   *  Abgeleitete Signale
   * Zielzuordnungen
   * Regelbasierte und an Bord befindliche Eigenschaften
   * Segmente
   * Eigenschaften- und Segmentordner-IDs
   Die [!DNL Audience Manager] API schreibt Massendaten zurück in das [!UICONTROL Request] Arbeitsblatt.

>[!NOTE]
>
>In Ihren Ergebnissen geben die `createTime` und die `updateTime` Spalten Daten in exponentieller Notation zurück. Die zugrunde liegenden Datums-/Uhrzeitstempel werden in UNIX UTC-Zeit aufgezeichnet. Derzeit kann das Arbeitsblatt keine Datums-/Uhrzeitstempel in lesbarer Form zurückgeben.

Wenn Ihr Massenupdate einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Massenverwaltungstools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
