---
description: Eine Massenanforderung gibt Daten zurück, die Sie mit den verschiedenen Headern in den Arbeitsblättern "Aktualisieren", "Erstellen", "Schätzung"und "Löschen"verwenden können.
seo-description: Eine Massenanforderung gibt Daten zurück, die Sie mit den verschiedenen Headern in den Arbeitsblättern "Aktualisieren", "Erstellen", "Schätzung"und "Löschen"verwenden können.
seo-title: Massenanforderungen
solution: Audience Manager
title: Massenanforderungen
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---


# Massenanforderungen{#bulk-requests}

Eine Massenanforderung gibt Daten zurück, die Sie mit den verschiedenen Headern in den Arbeitsblättern &quot;Aktualisieren&quot;, &quot;Erstellen&quot;, &quot;Schätzung&quot;und &quot;Löschen&quot;verwenden können.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[In der Benutzeroberfläche zugewiesene RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) werden berücksichtigt [!DNL Audience Manager] [!UICONTROL Bulk Management Tools].

Das [!UICONTROL Request] Arbeitsblatt hat keinen eigenen Satz von Spaltenüberschriften und Sie müssen keine IDs in eine der Spalten kopieren. Stattdessen werden Daten basierend auf der Aktionsschaltfläche zurückgegeben, auf die Sie in der Symbolleiste klicken. Eine optionale Berichte-Funktion gibt außerdem eine Frequenzzahl für Pixelfeuer und eine eindeutige Benutzeranzahl für mehrere feste Zeitintervalle zurück.

Um Massenanforderungen zu erstellen, öffnen Sie das [!UICONTROL Bulk Management Tools] Arbeitsblatt und:

1. Click the **[!UICONTROL Request]** tab.
2. Klicken Sie in der Symbolleiste oben im Arbeitsblatt auf eine Anforderungsschaltfläche, die den Daten entspricht, mit denen Sie arbeiten möchten. Sie können Folgendes anfordern:

   * Algorithmische Modelle
   * Datenquellen
   * Abgeleitete Signale
   * Zielzuordnungen
   * Algorithmische, regelbasierte und nicht an Bord befindliche Eigenschaften
   * Segmente
   * Eigenschaften- und Segmentordner-IDs
   Die [!DNL Audience Manager] API schreibt Massendaten zurück in das [!UICONTROL Request] Arbeitsblatt.

>[!NOTE]
>
>In Ihren Ergebnissen geben die `createTime` und die `updateTime` Spalten Daten in exponentieller Notation zurück. Die zugrunde liegenden Datums-/Uhrzeitstempel werden in UNIX UTC-Zeit aufgezeichnet. Derzeit kann das Arbeitsblatt keine Datums-/Uhrzeitstempel in lesbarer Form zurückgeben.

Wenn Ihr Massenupdate einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Massenverwaltungstools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
