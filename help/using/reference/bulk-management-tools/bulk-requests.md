---
description: Eine Massenanfrage gibt Daten zurück, die Sie mit den verschiedenen Kopfzeilen in den Arbeitsblättern „Aktualisieren“, „Erstellen“, „Schätzung“ und „Löschen“ verwenden können.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Massenanfragen
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# Massenanfragen{#bulk-requests}

Eine Massenanfrage gibt Daten zurück, die Sie mit den verschiedenen Kopfzeilen in den Arbeitsblättern „Aktualisieren“, „Erstellen“, „Schätzung“ und „Löschen“ verwenden können.

>[!IMPORTANT]
>
>Die Tools für die Massenverwaltung sind kein offiziell unterstütztes Adobe-Angebot. Die Fehlerbehebung und der Support über die Kundenunterstützung werden von Fall zu Fall durchgeführt.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md), die in der [!DNL Audience Manager]-Benutzeroberfläche zugewiesen sind, werden in der [!UICONTROL Bulk Management Tools] berücksichtigt.

Das [!UICONTROL Request] Arbeitsblatt verfügt nicht über einen eigenen Satz von Spaltenüberschriften und Sie müssen keine IDs in eine der Spalten kopieren. Stattdessen werden Daten basierend auf der Aktionsschaltfläche zurückgegeben, auf die Sie in der Symbolleiste klicken. Eine optionale Berichtsfunktion gibt eine Häufigkeitsanzahl für Pixelfeuer und eine eindeutige Benutzeranzahl für mehrere feste Zeitintervalle zurück.

Um Massenanfragen durchzuführen, öffnen Sie das [!UICONTROL Bulk Management Tools] Arbeitsblatt und:

1. Klicken Sie auf die Registerkarte **[!UICONTROL Request]** .
2. Klicken Sie in der Symbolleiste am oberen Rand des Arbeitsblatts auf eine Anforderungsschaltfläche, die den Daten entspricht, mit denen Sie arbeiten möchten. Sie können Folgendes anfordern:

   * Algorithmische Modelle
   * Datenquellen
   * Abgeleitete Signale
   * Zielzuordnungen
   * Algorithmische, regelbasierte und integrierte Eigenschaften
   * Segmente
   * Eigenschaften- und Segmentordner-IDs

   Die [!DNL Audience Manager]-API schreibt Massendaten zurück in das [!UICONTROL Request] Arbeitsblatt.

>[!NOTE]
>
>In Ihren Ergebnissen geben die Spalten `createTime` und `updateTime` Daten in exponentieller Schreibweise zurück. Die zugrunde liegenden Datums-/Zeitstempel werden in der UTC-Zeit von UNIX aufgezeichnet. Derzeit kann das Arbeitsblatt keine Datums-/Zeitstempel in einem lesbaren Format zurückgeben.

Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Tools für die Massenverwaltung](../../reference/bulk-management-tools/bulk-troubleshooting.md).
