---
description: Eine Massenanforderung gibt Daten zurück, die Sie mit den verschiedenen Headern in den Arbeitsblättern "Aktualisieren", "Erstellen", "Schätzung"und "Löschen"verwenden können.
seo-description: Eine Massenanforderung gibt Daten zurück, die Sie mit den verschiedenen Headern in den Arbeitsblättern "Aktualisieren", "Erstellen", "Schätzung"und "Löschen"verwenden können.
seo-title: Massenanfragen
solution: Audience Manager
title: Massenanfragen
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 3%

---

# Massenanfragen{#bulk-requests}

Eine Massenanforderung gibt Daten zurück, die Sie mit den verschiedenen Headern in den Arbeitsblättern &quot;Aktualisieren&quot;, &quot;Erstellen&quot;, &quot;Schätzung&quot;und &quot;Löschen&quot;verwenden können.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[In der ](../../features/administration/administration-overview.md) Benutzeroberfläche zugewiesene  [!DNL Audience Manager] RBAC-Gruppenberechtigungen werden berücksichtigt  [!UICONTROL Bulk Management Tools].

Das [!UICONTROL Request]-Arbeitsblatt hat keinen eigenen Satz von Spaltenüberschriften und Sie müssen keine IDs in eine der Spalten kopieren. Stattdessen werden Daten basierend auf der Aktionsschaltfläche zurückgegeben, auf die Sie in der Symbolleiste klicken. Eine optionale Berichte-Funktion gibt außerdem eine Frequenzzahl für Pixelfeuer und eine eindeutige Benutzeranzahl für mehrere feste Zeitintervalle zurück.

Um Massenanforderungen zu erstellen, öffnen Sie das Arbeitsblatt [!UICONTROL Bulk Management Tools] und:

1. Klicken Sie auf die Registerkarte **[!UICONTROL Request]**.
2. Klicken Sie in der Symbolleiste oben im Arbeitsblatt auf eine Anforderungsschaltfläche, die den Daten entspricht, mit denen Sie arbeiten möchten. Sie können Folgendes anfordern:

   * Algorithmische Modelle
   * Datenquellen
   * Abgeleitete Signale
   * Zielzuordnungen
   * Algorithmische, regelbasierte und nicht an Bord befindliche Eigenschaften
   * Segmente 
   * Eigenschaften- und Segmentordner-IDs

   Die [!DNL Audience Manager]-API schreibt Massendaten zurück in das [!UICONTROL Request]-Arbeitsblatt.

>[!NOTE]
>
>In Ihren Ergebnissen geben die Spalten `createTime` und `updateTime` Daten in exponentieller Notation zurück. Die zugrunde liegenden Datums-/Uhrzeitstempel werden in UNIX UTC-Zeit aufgezeichnet. Derzeit kann das Arbeitsblatt keine Datums-/Uhrzeitstempel in lesbarer Form zurückgeben.

Wenn Ihr Massenupdate einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Massenverwaltungstools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
