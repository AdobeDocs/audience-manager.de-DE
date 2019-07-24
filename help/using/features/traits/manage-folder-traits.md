---
description: Erstellen, bearbeiten und löschen Sie Ordnereigenschaften.
keywords: Ordnereigenschaften; Ordnereigenschaften; Ordnereigenschaften; Ordnereigenschaft
seo-description: Erstellen, bearbeiten und löschen Sie Ordnereigenschaften.
seo-title: Ordnereigenschaften verwalten
solution: Audience Manager
title: Ordnereigenschaften verwalten
uuid: 287 ac 280-bd 58-4985-85 bd-b 6501 eb 64 b 7 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Folder Traits {#manage-folder-traits}

Erstellen, bearbeiten und löschen Sie Ordnereigenschaften.

## Create a Folder Trait {#create-folder-trait}

A [!UICONTROL folder trait] is created automatically when you create a new folder in your taxonomy.

<!-- create-folder-trait.xml -->

1. Go to **[!UICONTROL Audience Data > Traits]** to navigate to the **Traits** dashboard.
1. In the [!UICONTROL Trait Storage] window, hover over:

   * Text für alle Eigenschaften, um einen neuen Stammordner für Ebenen hinzuzufügen.
   * Ein vorhandener übergeordneter Ordner, um einen neuen untergeordneten Ordner hinzuzufügen.
   ![](assets/folder_traits_create.PNG)

1. Klicken Sie auf das Symbol +, um den Ordner zu erstellen. Beachten Sie, dass Sie in Ihrer Taxonomie maximal 2.000 Ordner erstellen können. Weitere Informationen finden Sie in der Dokumentation zu den [Nutzungsbeschränkungen](../../features/administration/usage-limits.md).
1. Name the folder and click **Save**. Beispielsweise verfügt ein Ordner namens Electronics über eine Ordnereigenschaft mit dem Namen "Elektronikordnereigenschaften" . Sie können die neue Ordnereigenschaft im Eigenschaften-Dashboard anzeigen und auswählen.
1. The new folder trait is automatically assigned to the [!DNL Audience Manager] generated data source. Your users with appropriate [!UICONTROL Role-Based Access Control ([!DNL RBAC])] permissions can change the data source in the edit folder trait workflow. See [Edit a Folder Trait](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Edit a Folder Trait {#edit-folder-trait}

Describes how you can edit a [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the **[!UICONTROL Actions]** column for the folder trait you want to edit.
1. Klicken Sie auf den Stiftsymbol, um die Eigenschaft zu bearbeiten.

   ![](assets/folder_traits_edit_border.png)

1. The **[!UICONTROL Edit]** workflow allows you to change the data source for folder traits. Select your desired data source and click **[!UICONTROL Save]**. Data sources are sorted numerically, by [!DNL DPID], in the drop-down box.

   If your company uses [!UICONTROL Role-Based Access Rights (RBAC)], you or your users need [access permissions](../../features/traits/about-folder-traits.md#role-based-access-controls) to traits data sources.

>[!NOTE]
>
>Ordnereigenschaften können nicht direkt umbenannt werden. [Benennen Sie den zugehörigen Speicherordner](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) um, um den Namen der Ordnereigenschaft zu ändern.

## Delete a Folder Trait {#delete-folder-trait}

Löschen Sie ein Ordnermerkmal, indem Sie den Speicherordner löschen, zu dem die Eigenschaft gehört.

<!-- delete-folder-trait.xml -->

1. **Zielgruppendaten &gt; Eigenschaften** , um zum **Eigenschaften** -Dashboard zu navigieren.
1. In the [!UICONTROL Trait Storage] window, delete a folder by hovering over it and clicking the X icon.

   ![Schrittergebnis](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Sie können Ordnereigenschaften nicht löschen, wenn sie in einem Segmentausdruck verwendet werden. Navigate to the [trait view](../../features/traits/trait-details-page.md) section to see which segments use the folder trait. Then, click on the segment name to open the [segment summary view](../../features/segments/segment-summary-view.md), which allows you to remove traits from segment expressions.