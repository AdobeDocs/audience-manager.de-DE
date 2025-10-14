---
description: Mit dem Massenlöschen können Sie mit einem einzigen Vorgang mehrere Segmente, Eigenschaften, Ordner, abgeleitete Signale, Datenquellen, Modelle und Ziele entfernen. Befolgen Sie diese Anweisungen, um eine Massenlöschanfrage zu stellen.
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

Mit dem Massenlöschen können Sie mit einem einzigen Vorgang mehrere Segmente, Eigenschaften, Ordner, abgeleitete Signale, Datenquellen, Modelle und Ziele entfernen. Befolgen Sie diese Anweisungen, um eine Massenlöschanfrage zu stellen.

>[!IMPORTANT]
>
>Die Tools für die Massenverwaltung sind kein offiziell unterstütztes Adobe-Angebot. Die Fehlerbehebung und der Support über die Kundenunterstützung werden von Fall zu Fall durchgeführt.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md), die in der [!DNL Audience Manager]-Benutzeroberfläche zugewiesen sind, werden in der [!UICONTROL Bulk Management Tools] berücksichtigt.

>[!NOTE]
>
>Eine Massenlöschung für Zielzuordnungen schlägt fehl, wenn dem Ziel Segmente zugeordnet sind. Entfernen Sie Ihre Segmente aus diesem Ziel in der Benutzeroberfläche, bevor Sie versuchen, Massenlöschziele zu löschen. Außerdem müssen Eigenschafts- und Segmentordner leer sein, bevor Sie sie löschen können.

Um mehrere Elemente zu löschen, öffnen Sie das [!UICONTROL Bulk Management Tools] Arbeitsblatt und:

1. Klicken Sie auf die Registerkarte **[!UICONTROL Headers]** und kopieren Sie die Kopfzeilen für das Element, das Sie hinzufügen möchten.
2. Klicken Sie auf die Registerkarte **[!UICONTROL Delete]** .
3. Fügen Sie die Löschkopfzeilen in die erste Zeile des Aktualisierungsarbeitsblatts ein.
4. Fügen Sie die IDs für die Objekte, die Sie löschen möchten, in die Spalte unter der Kopfzeile ein oder geben Sie sie ein.
5. Geben Sie die erforderlichen [Anmeldeinformationen“ ein &#x200B;](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) klicken Sie auf **[!UICONTROL Submit]**.

   Das Arbeitsblatt erstellt eine [!UICONTROL Results]. Die Spalte [!UICONTROL Results] gibt eine Meldung zurück, die angibt, ob das Element gelöscht wurde, oder eine Fehlermeldung.
Vor der Dateneingabe sollte Ihr Massenaktualisierungsarbeitsblatt wie folgt aussehen:

![](assets/delete.png)

Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Tools für die Massenverwaltung](../../reference/bulk-management-tools/bulk-troubleshooting.md).
