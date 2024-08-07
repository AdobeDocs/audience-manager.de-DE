---
description: Durch Massenlöschung können Sie mehrere Segmente, Eigenschaften, Ordner, abgeleitete Signale, Datenquellen, Modelle und Ziele mit einem einzigen Vorgang entfernen. Befolgen Sie diese Anweisungen, um eine Massenlöschanfrage durchzuführen.
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, data sources, models, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: Massenlöschung
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---

# Massenlöschung{#bulk-delete}

Durch Massenlöschung können Sie mehrere Segmente, Eigenschaften, Ordner, abgeleitete Signale, Datenquellen, Modelle und Ziele mit einem einzigen Vorgang entfernen. Befolgen Sie diese Anweisungen, um eine Massenlöschanfrage durchzuführen.

>[!IMPORTANT]
>
>Die Tools für die Massenverwaltung sind kein offiziell unterstütztes Adobe-Angebot. Die Fehlerbehebung und der Support durch die Kundenunterstützung werden von Fall zu Fall durchgeführt.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[In der Benutzeroberfläche von [!DNL Audience Manager] zugewiesene RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) werden in der [!UICONTROL Bulk Management Tools] berücksichtigt.

>[!NOTE]
>
>Eine Massenlöschung für Zielzuordnungen schlägt fehl, wenn dem Ziel Segmente zugeordnet sind. Entfernen Sie Ihre Segmente aus diesem Ziel in der Benutzeroberfläche, bevor Sie versuchen, Ziele per Massenlöschung zu löschen. Außerdem müssen Eigenschaften- und Segmentordner leer sein, bevor Sie sie löschen können.

Um mehrere Elemente zu löschen, öffnen Sie das [!UICONTROL Bulk Management Tools] -Arbeitsblatt und:

1. Klicken Sie auf die Registerkarte **[!UICONTROL Headers]** und kopieren Sie die Kopfzeilen zum Erstellen des Elements, das Sie hinzufügen möchten.
2. Klicken Sie auf die Registerkarte **[!UICONTROL Delete]** .
3. Fügen Sie die Header zum Löschen in die erste Zeile des Aktualisierungsarbeitsblatts ein.
4. Fügen Sie die IDs für die Objekte, die Sie löschen möchten, in die Spalte unter der Kopfzeile ein oder geben Sie sie ein.
5. Geben Sie die erforderlichen [Anmeldedaten ](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) an und klicken Sie auf **[!UICONTROL Submit]**.

   Das Arbeitsblatt erstellt eine [!UICONTROL Results] -Spalte. Die Spalte [!UICONTROL Results] gibt eine Meldung zurück, die angibt, ob das Element gelöscht wurde oder eine Fehlermeldung angezeigt wurde.
Vor der Eingabe von Daten sollte das Bulk Update-Arbeitsblatt in etwa wie folgt aussehen:

![](assets/delete.png)

Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Tools für die Massenverwaltung](../../reference/bulk-management-tools/bulk-troubleshooting.md).
