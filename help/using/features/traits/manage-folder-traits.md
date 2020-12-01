---
description: Erstellen, bearbeiten und löschen Sie Ordnereigenschaften.
keywords: Folder Trait;Folder Traits;folder traits;folder trait
seo-description: Erstellen, bearbeiten und löschen Sie Ordnereigenschaften.
seo-title: Verwalten von Ordnereigenschaften
solution: Audience Manager
title: Verwalten von Ordnereigenschaften
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
translation-type: tm+mt
source-git-commit: 4ea5ba4ebd8cd4c13c99c8272f4b5733ab5fa125
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 9%

---


# Verwalten von Ordnereigenschaften {#manage-folder-traits}

Erstellen, bearbeiten und löschen Sie Ordnereigenschaften.

## Ordnereigenschaft {#create-folder-trait} erstellen

Ein [!UICONTROL folder trait] wird automatisch erstellt, wenn Sie einen neuen Ordner in Ihrer Taxonomie erstellen.

<!-- create-folder-trait.xml -->

1. Gehen Sie zu **[!UICONTROL Audience Data > Traits]**, um zum Dashboard **Eigenschaften** zu navigieren.
1. Bewegen Sie den Mauszeiger im Fenster [!UICONTROL Trait Storage] über:

   * &quot;Alle Eigenschaften&quot;Text, um einen neuen Stammordner hinzuzufügen.
   * Ein vorhandener übergeordneter Ordner zum Hinzufügen eines neuen Untergeordnet-Ordners.

   ![](assets/folder_traits_create.PNG)

1. Klicken Sie auf das Symbol +, um den Ordner zu erstellen. Beachten Sie, dass Sie in Ihrer Taxonomie maximal 2.000 Ordner erstellen können. Weitere Informationen finden Sie in der Dokumentation zu den [Nutzungsbeschränkungen](../../features/administration/usage-limits.md).
1. Benennen Sie den Ordner und klicken Sie auf **Speichern**. Ein Ordner mit dem Namen &quot;Elektronik&quot;verfügt beispielsweise über eine Ordnereigenschaft mit dem Namen &quot;Elektronik-Ordnereigenschaft&quot;. Sie können die neue Ordnereigenschaft im Dashboard Eigenschaften Ansicht und auswählen.
1. Die neue Ordnereigenschaft wird automatisch der generierten Datenquelle [!DNL Audience Manager] zugewiesen. Ihre Benutzer mit entsprechenden Berechtigungen für [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) können die Datenquelle im Arbeitsablauf für die Eigenschaften des Bearbeitungsordners ändern. Siehe [Ordnereigenschaft bearbeiten](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Ordnereigenschaft {#edit-folder-trait} bearbeiten

Beschreibt, wie Sie ein [!UICONTROL folder trait] bearbeiten können.

<!-- edit-folder-trait.xml -->

1. Bewegen Sie den Mauszeiger im Dashboard [!UICONTROL Traits] über die Spalte **[!UICONTROL Actions]** für die Ordnereigenschaft, die Sie bearbeiten möchten.
1. Klicken Sie auf den Stift, um die Eigenschaft zu bearbeiten.

   ![](assets/folder_traits_edit_border.png)

1. Mit dem Arbeitsablauf **[!UICONTROL Edit]** können Sie die Datenquelle für Ordnereigenschaften ändern. Wählen Sie die gewünschte Datenquelle aus und klicken Sie auf **[!UICONTROL Save]**. Datenquellen werden im Dropdown-Feld numerisch nach [!DNL DPID] sortiert.

   Wenn Ihre Firma [!UICONTROL Role-Based Access Rights (RBAC)] verwendet, benötigen Sie oder Ihre Benutzer [Zugriffsberechtigungen](../../features/traits/about-folder-traits.md#role-based-access-controls), um Datenquellen zu kennzeichnen.

>[!NOTE]
>
>Sie können eine Ordnereigenschaft nicht direkt umbenennen. [Benennen Sie den zugehörigen ](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) Ordnernamen um, um den Ordnernamen zu ändern.

## Ordnereigenschaft {#delete-folder-trait} löschen

Löschen Sie eine Ordnereigenschaft, indem Sie den Ordner &quot;Datenspeicherung&quot;löschen, zu dem die Eigenschaft gehört.

<!-- delete-folder-trait.xml -->

1. **Audience Data >** Eigenschaften, um zum  **** Traitsdashboard zu navigieren.
1. Löschen Sie im Fenster [!UICONTROL Trait Storage] einen Ordner, indem Sie den Mauszeiger darüber halten und auf das X-Symbol klicken.

   ![Schritt-Ergebnis](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Sie können eine Ordnereigenschaft nicht löschen, wenn sie in einem Segment-Ausdruck verwendet wird. Navigieren Sie zum Abschnitt [Eigenschafts-Ansicht](../../features/traits/trait-details-page.md), um zu sehen, welche Segmente die Ordnereigenschaft verwenden. Klicken Sie dann auf den Segmentnamen, um die Ansicht [Segmentzusammenfassung](../../features/segments/segment-summary-view.md) zu öffnen, mit der Sie Eigenschaften aus SegmentAusdrücken entfernen können.
