---
description: Durch Massenlöschung können Sie mehrere Segmente, Eigenschaften, Ordner, abgeleitete Signale, Datenquellen, Modelle und Ziele mit einem einzigen Vorgang entfernen. Befolgen Sie diese Anweisungen, um eine Massenlöschanfrage durchzuführen.
seo-description: Durch Massenlöschung können Sie mehrere Segmente, Eigenschaften, Ordner, abgeleitete Signale, Datenquellen, Modelle und Ziele mit einem einzigen Vorgang entfernen. Befolgen Sie diese Anweisungen, um eine Massenlöschanfrage durchzuführen.
seo-title: Massenlöschungen
solution: Audience Manager
title: Massenlöschungen
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Massenlöschungen{#bulk-delete}

Durch Massenlöschung können Sie mehrere Segmente, Eigenschaften, Ordner, abgeleitete Signale, Datenquellen, Modelle und Ziele mit einem einzigen Vorgang entfernen. Befolgen Sie diese Anweisungen, um eine Massenlöschanfrage durchzuführen.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[In der ](../../features/administration/administration-overview.md) Benutzeroberfläche zugewiesene RBAC-Gruppenberechtigungen werden in der berücksichtigt  [!DNL Audience Manager]   [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Eine Massenlöschung für Zielzuordnungen schlägt fehl, wenn dem Ziel Segmente zugeordnet sind. Entfernen Sie Ihre Segmente aus diesem Ziel in der Benutzeroberfläche, bevor Sie versuchen, Ziele per Massenlöschung zu löschen. Außerdem müssen Eigenschaften- und Segmentordner leer sein, bevor Sie sie löschen können.

Um mehrere Elemente zu löschen, öffnen Sie das Arbeitsblatt [!UICONTROL Bulk Management Tools] und:

1. Klicken Sie auf die Registerkarte **[!UICONTROL Headers]** und kopieren Sie die Kopfzeilen zum Erstellen des Elements, das Sie hinzufügen möchten.
2. Klicken Sie auf die Registerkarte **[!UICONTROL Delete]** .
3. Fügen Sie die Header zum Löschen in die erste Zeile des Aktualisierungsarbeitsblatts ein.
4. Fügen Sie die IDs für die Objekte, die Sie löschen möchten, in die Spalte unter der Kopfzeile ein oder geben Sie sie ein.
5. Geben Sie die erforderlichen [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ein und klicken Sie auf **[!UICONTROL Submit]**.

   Das Arbeitsblatt erstellt eine [!UICONTROL Results] -Spalte. Die Spalte [!UICONTROL Results] gibt eine Meldung zurück, die angibt, ob das Element gelöscht wurde oder eine Fehlermeldung angezeigt wurde.
Vor der Eingabe von Daten sollte Ihr Bulk Update-Arbeitsblatt wie folgt aussehen:

![](assets/delete.png)

Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Massenverwaltungswerkzeuge](../../reference/bulk-management-tools/bulk-troubleshooting.md).
