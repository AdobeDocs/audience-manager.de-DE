---
description: Erstellen, bearbeiten und löschen Sie Ordnereigenschaften.
keywords: Ordnereigenschaft; Ordnereigenschaften; Ordnereigenschaften; Ordnereigenschaft
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

Erstellen, bearbeiten und löschen Sie Ordnereigenschaften.

## Erstellen einer Ordnereigenschaft {#create-folder-trait}

Ein [!UICONTROL folder trait] wird automatisch erstellt, wenn Sie einen neuen Ordner in Ihrer Taxonomie erstellen.

<!-- create-folder-trait.xml -->

1. Navigieren Sie zu **[!UICONTROL Audience Data > Traits]** , um zum Dashboard **Eigenschaften** zu navigieren.
1. Bewegen Sie im Fenster [!UICONTROL Trait Storage] den Mauszeiger über:

   * Text &quot;Alle Eigenschaften&quot;, um einen neuen Ordner auf der Stammebene hinzuzufügen.
   * Ein vorhandener übergeordneter Ordner zum Hinzufügen eines neuen untergeordneten Ordners.

   ![](assets/folder_traits_create.PNG)

1. Klicken Sie auf das Symbol +, um den Ordner zu erstellen. Beachten Sie, dass Sie in Ihrer Taxonomie maximal 2.000 Ordner erstellen können. Weitere Informationen finden Sie in der Dokumentation zu den [Nutzungsbeschränkungen](../../features/administration/usage-limits.md).
1. Benennen Sie den Ordner und klicken Sie auf **Speichern**. Beispiel: Ein Ordner namens &quot;Electronics&quot;weist eine Ordnereigenschaft mit dem Namen &quot;Electronics Folder Trait&quot;auf. Sie können die neue Ordnereigenschaft im Eigenschaften-Dashboard anzeigen und auswählen.
1. Die neue Ordnereigenschaft wird automatisch der [!DNL Audience Manager] generierten Datenquelle zugewiesen. Ihre Benutzer mit entsprechenden [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) Berechtigungen können die Datenquelle im Workflow für Eigenschaften von Bearbeitungsordnern ändern. Siehe [Bearbeiten einer Ordnereigenschaft](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Bearbeiten einer Ordnereigenschaft {#edit-folder-trait}

Beschreibt, wie Sie einen [!UICONTROL folder trait] bearbeiten können.

<!-- edit-folder-trait.xml -->

1. Bewegen Sie im Dashboard [!UICONTROL Traits] den Mauszeiger über die Spalte **[!UICONTROL Actions]** für die Ordnereigenschaft, die Sie bearbeiten möchten.
1. Klicken Sie auf den Stift, um die Eigenschaft zu bearbeiten.

   ![](assets/folder_traits_edit_border.png)

1. Mit dem Workflow **[!UICONTROL Edit]** können Sie die Datenquelle für Ordnereigenschaften ändern. Wählen Sie die gewünschte Datenquelle aus und klicken Sie auf **[!UICONTROL Save]**. Datenquellen werden in der Dropdown-Liste numerisch nach [!DNL DPID] sortiert.

   Wenn Ihr Unternehmen [!UICONTROL Role-Based Access Rights (RBAC)] verwendet, benötigen Sie oder Ihre Benutzer [Zugriffsberechtigungen](../../features/traits/about-folder-traits.md#role-based-access-controls), um Datenquellen zu kennzeichnen.

>[!NOTE]
>
>Sie können eine Ordnereigenschaft nicht direkt umbenennen. [Benennen Sie den zugehörigen Speicherordner um](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder), um den Namen der Ordnereigenschaft zu ändern.

## Ordnereigenschaft löschen {#delete-folder-trait}

Löschen Sie eine Ordnereigenschaft, indem Sie den Speicherordner löschen, zu dem die Eigenschaft gehört.

<!-- delete-folder-trait.xml -->

1. **Zielgruppendaten > Eigenschaften** zum Dashboard **Eigenschaften** navigieren.
1. Löschen Sie im Fenster [!UICONTROL Trait Storage] einen Ordner, indem Sie den Mauszeiger darüber bewegen und auf das X-Symbol klicken.

   ![Schrittergebnis](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Sie können eine Ordnereigenschaft nicht löschen, wenn sie in einem Segmentausdruck verwendet wird. Navigieren Sie zum Abschnitt [Eigenschaftenansicht](../../features/traits/trait-details-page.md) , um zu sehen, welche Segmente die Ordnereigenschaft verwenden. Klicken Sie dann auf den Segmentnamen, um die Ansicht [Segmentzusammenfassung](../../features/segments/segment-summary-view.md) zu öffnen, in der Sie Eigenschaften aus Segmentausdrücken entfernen können.
