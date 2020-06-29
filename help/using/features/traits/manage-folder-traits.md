---
description: Erstellen, bearbeiten und löschen Sie Ordnereigenschaften.
keywords: Folder Trait;Folder Traits;folder traits;folder trait
seo-description: Erstellen, bearbeiten und löschen Sie Ordnereigenschaften.
seo-title: Ordnereigenschaften verwalten
solution: Audience Manager
title: Ordnereigenschaften verwalten
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 7%

---


# Ordnereigenschaften verwalten {#manage-folder-traits}

Erstellen, bearbeiten und löschen Sie Ordnereigenschaften.

## Ordnereigenschaften erstellen {#create-folder-trait}

Eine [!UICONTROL folder trait] wird automatisch erstellt, wenn Sie einen neuen Ordner in Ihrer Taxonomie erstellen.

<!-- create-folder-trait.xml -->

1. Navigieren Sie **[!UICONTROL Audience Data > Traits]** zum Dashboard **Eigenschaften** .
1. Bewegen Sie den Mauszeiger im [!UICONTROL Trait Storage] Fenster über:

   * &quot;Alle Eigenschaften&quot;Text, um einen neuen Stammordner hinzuzufügen.
   * Ein vorhandener übergeordneter Ordner, um einen neuen untergeordneten Ordner hinzuzufügen.
   ![](assets/folder_traits_create.PNG)

1. Klicken Sie auf das Symbol +, um den Ordner zu erstellen. Beachten Sie, dass Sie in Ihrer Taxonomie maximal 2.000 Ordner erstellen können. Weitere Informationen finden Sie in der Dokumentation zu den [Nutzungsbeschränkungen](../../features/administration/usage-limits.md).
1. Benennen Sie den Ordner und klicken Sie auf **Speichern**. Ein Ordner mit dem Namen &quot;Elektronik&quot;verfügt beispielsweise über eine Ordnereigenschaft mit dem Namen &quot;Elektronik-Ordnereigenschaft&quot;. Sie können die neue Ordnereigenschaft im Dashboard Eigenschaften Ansicht und auswählen.
1. Die neue Ordnereigenschaft wird automatisch der [!DNL Audience Manager] generierten Datenquelle zugewiesen. Ihre Benutzer mit entsprechenden Berechtigungen für die [!UICONTROL Rollenbasierte Zugriffskontrolle ([!DNL RBAC])] können die Datenquelle im Arbeitsablauf für die Eigenschaften des Bearbeitungsordners ändern. Siehe Ordnereigenschaften [bearbeiten](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Ordnereigenschaften bearbeiten {#edit-folder-trait}

Beschreibt, wie Sie eine [!UICONTROL folder trait]Datei bearbeiten können.

<!-- edit-folder-trait.xml -->

1. Bewegen Sie den Mauszeiger im [!UICONTROL Traits] Dashboard über die **[!UICONTROL Actions]** Spalte für die Ordnereigenschaft, die Sie bearbeiten möchten.
1. Klicken Sie auf den Stift, um die Eigenschaft zu bearbeiten.

   ![](assets/folder_traits_edit_border.png)

1. Mit dem **[!UICONTROL Edit]** Arbeitsablauf können Sie die Datenquelle für Ordnereigenschaften ändern. Wählen Sie die gewünschte Datenquelle aus und klicken Sie auf **[!UICONTROL Save]**. Datenquellen werden in der Dropdown-Liste numerisch nach [!DNL DPID]sortiert.

   Wenn Ihre Firma verwendet [!UICONTROL Role-Based Access Rights (RBAC)], benötigen Sie oder Ihre Benutzer [Zugriffsberechtigungen](../../features/traits/about-folder-traits.md#role-based-access-controls) auf Datenquellen mit Eigenschaften.

>[!NOTE]
>
>Sie können eine Ordnereigenschaft nicht direkt umbenennen. [Benennen Sie den zugehörigen Ordnernamen](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) um, um den Ordnernamen zu ändern.

## Ordnereigenschaften löschen {#delete-folder-trait}

Löschen Sie eine Ordnereigenschaft, indem Sie den Ordner &quot;Datenspeicherung&quot;löschen, zu dem die Eigenschaft gehört.

<!-- delete-folder-trait.xml -->

1. **Audience Data > Traits** , um zum Dashboard **Eigenschaften** zu navigieren.
1. Löschen Sie im [!UICONTROL Trait Storage] Fenster einen Ordner, indem Sie den Mauszeiger darüber halten und auf das X-Symbol klicken.

   ![Schritt-Ergebnis](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Sie können eine Ordnereigenschaft nicht löschen, wenn sie in einem Segment-Ausdruck verwendet wird. Navigieren Sie zum Abschnitt [Eigenschafts-Ansicht](../../features/traits/trait-details-page.md) , um zu sehen, welche Segmente die Ordnereigenschaft verwenden. Klicken Sie dann auf den Segmentnamen, um die Ansicht [für die](../../features/segments/segment-summary-view.md)Segmentzusammenfassung zu öffnen, mit der Sie Eigenschaften aus SegmentAusdrücken entfernen können.