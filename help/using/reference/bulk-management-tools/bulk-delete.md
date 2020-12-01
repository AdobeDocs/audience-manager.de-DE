---
description: Durch das Löschen von Stapeln können Sie mehrere Segmente, Eigenschaften, Ordner, abgeleitete Signale, Datenquellen, Modelle und Ziele mit einem einzigen Vorgang entfernen. Befolgen Sie diese Anweisungen, um eine Massenlöschanforderung durchzuführen.
seo-description: Durch das Löschen von Stapeln können Sie mehrere Segmente, Eigenschaften, Ordner, abgeleitete Signale, Datenquellen, Modelle und Ziele mit einem einzigen Vorgang entfernen. Befolgen Sie diese Anweisungen, um eine Massenlöschanforderung durchzuführen.
seo-title: Massenlöschungen
solution: Audience Manager
title: Massenlöschungen
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---


# Massenlöschungen{#bulk-delete}

Durch das Löschen von Stapeln können Sie mehrere Segmente, Eigenschaften, Ordner, abgeleitete Signale, Datenquellen, Modelle und Ziele mit einem einzigen Vorgang entfernen. Befolgen Sie diese Anweisungen, um eine Massenlöschanforderung durchzuführen.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[In der ](../../features/administration/administration-overview.md) Benutzeroberfläche zugewiesene  [!DNL Audience Manager] RBAC-Gruppenberechtigungen werden berücksichtigt  [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Ein Massenlöschvorgang für Zielzuordnungen schlägt fehl, wenn dem Ziel Segmente zugeordnet sind. Entfernen Sie Ihre Segmente aus diesem Ziel in der Benutzeroberfläche, bevor Sie versuchen, Ziele per Massen-Löschvorgang zu löschen. Eigenschaften- und Segmentordner müssen außerdem leer sein, bevor Sie sie löschen können.

Um mehrere Elemente zu löschen, öffnen Sie das Arbeitsblatt [!UICONTROL Bulk Management Tools] und:

1. Klicken Sie auf die Registerkarte **[!UICONTROL Headers]** und kopieren Sie die Kopfzeilen für das Element, das Sie hinzufügen möchten.
2. Klicken Sie auf die Registerkarte **[!UICONTROL Delete]**.
3. Fügen Sie die Header zum Löschen in die erste Zeile des Aktualisierungsarbeitsblatts ein.
4. Fügen Sie die IDs für die Objekte, die Sie löschen möchten, in die Spalte unter der Kopfzeile ein oder geben Sie sie ein.
5. Geben Sie die erforderlichen [Anmeldeangaben](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ein und klicken Sie auf **[!UICONTROL Submit]**.

   Das Arbeitsblatt erstellt eine Spalte [!UICONTROL Results]. Die Spalte [!UICONTROL Results] gibt eine Meldung zurück, die angibt, ob das Element gelöscht wurde, oder eine Fehlermeldung.
Bevor Sie Daten eingeben, sollte Ihr Bulk Update-Arbeitsblatt wie folgt aussehen:

![](assets/delete.png)

Wenn Ihr Massenupdate einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Massenverwaltungstools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
