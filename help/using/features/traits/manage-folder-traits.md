---
description: Erstellen, Bearbeiten und Löschen von Ordnereigenschaften.
keywords: Ordnereigenschaft;Ordnereigenschaften;Ordnereigenschaften;Ordnereigenschaft
seo-description: Create, edit, and delete folder traits.
seo-title: Manage Folder Traits
solution: Audience Manager
title: Verwalten von Ordnereigenschaften
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
source-git-commit: f7a4478589f4af1d467f1045a97dbb7f5cd6f9e5
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---

# Verwalten von Ordnereigenschaften {#manage-folder-traits}

Erstellen, Bearbeiten und Löschen von Ordnereigenschaften.

## Erstellen einer Ordnereigenschaft {#create-folder-trait}

Ein [!UICONTROL folder trait] wird automatisch erstellt, wenn Sie einen neuen Ordner in Ihrer Taxonomie erstellen.

<!-- create-folder-trait.xml -->

1. Navigieren Sie zu **[!UICONTROL Audience Data > Traits]** , um zum Dashboard **Eigenschaften** zu gelangen.
1. Bewegen Sie im [!UICONTROL Trait Storage] den Mauszeiger über:

   * Text für „Alle Eigenschaften“, um einen neuen Stammordner hinzuzufügen.
   * Einen vorhandenen übergeordneten Ordner, um einen neuen untergeordneten Ordner hinzuzufügen.

   ![](assets/folder_traits_create.PNG)

1. Klicken Sie auf das Symbol +, um den Ordner zu erstellen. Beachten Sie, dass Sie maximal 2.000 Ordner in Ihrer Taxonomie erstellen können. Weitere Informationen finden Sie in der Dokumentation zu den [Nutzungsbeschränkungen](../../features/administration/usage-limits.md).
1. Benennen Sie den Ordner und klicken Sie auf **Speichern**. Beispielsweise weist ein Ordner mit dem Namen „Electronics“ eine Ordnereigenschaft mit dem Namen „Electronics Folder Trait“ auf. Sie können die neue Ordnereigenschaft im Eigenschaften-Dashboard anzeigen und auswählen.
1. Die neue Ordnereigenschaft wird automatisch der [!DNL Audience Manager] generierten Datenquelle zugewiesen. Benutzerinnen und Benutzer mit entsprechenden [!UICONTROL Role-Based Access Control] ([!DNL RBAC])-Berechtigungen können die Datenquelle im Workflow zum Bearbeiten von Ordnereigenschaften ändern. Siehe [Bearbeiten einer Ordnereigenschaft](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Bearbeiten einer Ordnereigenschaft {#edit-folder-trait}

Beschreibt, wie Sie eine [!UICONTROL folder trait] bearbeiten können.

<!-- edit-folder-trait.xml -->

1. Bewegen Sie im [!UICONTROL Traits]-Dashboard den Mauszeiger über die Spalte **[!UICONTROL Actions]** für die Ordnereigenschaft, die Sie bearbeiten möchten.
1. Klicken Sie auf den Stift, um die Eigenschaft zu bearbeiten.

   ![](assets/folder_traits_edit_border.png)

1. Der **[!UICONTROL Edit]** Workflow ermöglicht es Ihnen, die Datenquelle für Ordnereigenschaften zu ändern. Wählen Sie die gewünschte Datenquelle aus und klicken Sie auf **[!UICONTROL Save]**. Datenquellen werden numerisch nach [!DNL DPID] in der Dropdown-Liste sortiert.

   Wenn Ihr Unternehmen [!UICONTROL Role-Based Access Rights (RBAC)] verwendet, benötigen Sie bzw. Ihre Benutzer [Zugriffsberechtigungen](../../features/traits/about-folder-traits.md#role-based-access-controls) um Datenquellen zu kennzeichnen.

>[!NOTE]
>
>Eine Ordnereigenschaft kann nicht direkt umbenannt werden. [Benennen Sie den zugehörigen ](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) um, um den Namen der Ordnereigenschaft zu ändern.

## Löschen einer Ordnereigenschaft {#delete-folder-trait}

Löschen einer Ordnereigenschaft durch Löschen des Speicherordners, zu dem die Eigenschaft gehört.

<!-- delete-folder-trait.xml -->

1. **Zielgruppendaten > Eigenschaften**, um zum **Eigenschaften**-Dashboard zu navigieren.
1. Löschen Sie im [!UICONTROL Trait Storage] einen Ordner, indem Sie den Mauszeiger darüber bewegen und auf das X-Symbol klicken.

   ![Schrittergebnis](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Ordnereigenschaften können nicht gelöscht werden, wenn sie in einem Segmentausdruck verwendet werden. Navigieren Sie zum Abschnitt [Eigenschaftsansicht](../../features/traits/trait-details-page.md), um zu sehen, welche Segmente die Ordnereigenschaft verwenden. Klicken Sie dann auf den Segmentnamen, um die Ansicht [Segmentzusammenfassung“ zu öffnen](../../features/segments/segment-summary-view.md) in der Sie Eigenschaften aus Segmentausdrücken entfernen können.
