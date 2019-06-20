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


# Massenanforderungen{#bulk-requests}

Eine Massenanforderung gibt Daten zurück, die Sie mit den verschiedenen Kopfzeilen in den Arbeitsblättern &quot;Aktualisieren&quot; ,&quot; Erstellen&quot; , &quot;Schätzung&quot; und&quot; Löschen&quot; verwenden können.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>Die Variable [!UICONTROL Bulk Management Tools]*wird nicht* unterstützt [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. Für Massenänderungen wird empfohlen, stattdessen mit den [Audience Manager-apis](../../api/rest-api-main/aam-api-getting-started.md) zu arbeiten. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

Das [!UICONTROL Request] Arbeitsblatt hat keinen eigenen Spaltensatz und Sie müssen keine IDs in eine der Spalten kopieren. Stattdessen werden Daten basierend auf der Aktionsschaltfläche zurückgegeben, auf die Sie in der Symbolleiste klicken. Außerdem gibt eine optionale Berichterstellungsfunktion eine Häufigkeitsanzahl für Pixel und eine eindeutige Benutzeranzahl für mehrere feste Zeitintervalle zurück.

Um Massenanforderungen zu erstellen, öffnen Sie das [!UICONTROL Bulk Management Tools] Arbeitsblatt und:

1. Klicken Sie auf die **[!UICONTROL Request]** Registerkarte.
2. Klicken Sie in der Symbolleiste oben im Arbeitsblatt auf eine Anforderungsschaltfläche entsprechend den Daten, mit denen Sie arbeiten möchten. Sie können Folgendes abrufen:

   * Datenanbieter-IDs
   * Abgeleitete Signale
   * Zielzuordnungen
   * Regelbasierte und voreingestellte Eigenschaften
   * Segmente
   * Eigenschaften für Eigenschaften und Segmentordner
   Die [!DNL Audience Manager] API schreibt Massendaten zurück in das [!UICONTROL Request] Arbeitsblatt.

>[!NOTE]
>
>In Ihren Ergebnissen geben die `createTime` Spalten `updateTime` Daten in exponentiellen Notation zurück. Die zugrunde liegenden Datums-/Uhrzeitstempel werden in der UNIX UTC-Zeit aufgezeichnet. Derzeit kann das Arbeitsblatt Datums-/Zeitstempel nicht in lesbarer Form wiedergeben.

Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden [Sie weitere Informationen unter Fehlerbehebung für Massenverwaltungswerkzeuge](../../reference/bulk-management-tools/bulk-troubleshooting.md).
