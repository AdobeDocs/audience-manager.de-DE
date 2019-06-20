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


# Ordnereigenschaften verwalten {#manage-folder-traits}

Erstellen, bearbeiten und löschen Sie Ordnereigenschaften.

## Erstellen eines Ordnermerkmals {#create-folder-trait}

A [!UICONTROL folder trait] wird automatisch erstellt, wenn Sie einen neuen Ordner in der Taxonomie erstellen.

<!-- create-folder-trait.xml -->

1. Navigieren Sie zum **[!UICONTROL Audience Data > Traits]****Eigenschaften** -Dashboard.
1. Bewegen Sie den Mauszeiger im [!UICONTROL Trait Storage] Fenster über:

   * Text für alle Eigenschaften, um einen neuen Stammordner für Ebenen hinzuzufügen.
   * Ein vorhandener übergeordneter Ordner, um einen neuen untergeordneten Ordner hinzuzufügen.
   ![](assets/folder_traits_create.PNG)

1. Klicken Sie auf das Symbol +, um den Ordner zu erstellen. Beachten Sie, dass Sie in Ihrer Taxonomie maximal 2.000 Ordner erstellen können. Weitere Informationen finden Sie in der Dokumentation zu den [Nutzungsbeschränkungen](../../features/administration/usage-limits.md).
1. Benennen Sie den Ordner und klicken Sie auf **Speichern**. Beispielsweise verfügt ein Ordner namens Electronics über eine Ordnereigenschaft mit dem Namen &quot;Elektronikordnereigenschaften&quot; . Sie können die neue Ordnereigenschaft im Eigenschaften-Dashboard anzeigen und auswählen.
1. Die neue Ordnereigenschaft wird automatisch der [!DNL Audience Manager] generierten Datenquelle zugewiesen. Ihre Benutzer mit entsprechenden [! UICONTROL rollenbasierte Zugriffssteuerungssteuerung ([!DNL RBAC])] kann die Datenquelle im Arbeitsablauf für den Bearbeitungsordner ändern. Siehe [Bearbeiten von Ordnereigenschaften](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Bearbeiten eines Ordnermerkmals {#edit-folder-trait}

Beschreibt, wie Sie A bearbeiten [!UICONTROL folder trait]können.

<!-- edit-folder-trait.xml -->

1. Bewegen Sie den Mauszeiger im [!UICONTROL Traits] Dashboard über die **[!UICONTROL Actions]** Spalte, die Sie bearbeiten möchten.
1. Klicken Sie auf den Stiftsymbol, um die Eigenschaft zu bearbeiten.

   ![](assets/folder_traits_edit_border.png)

1. Mit dem **[!UICONTROL Edit]** Workflow können Sie die Datenquelle für Ordnereigenschaften ändern. Wählen Sie die gewünschte Datenquelle aus und klicken **[!UICONTROL Save]** Sie auf. Datenquellen werden numerisch (in [!DNL DPID]der Dropdown-Liste) sortiert.

   Wenn Ihr Unternehmen verwendet [!UICONTROL Role-Based Access Rights (RBAC)]wird, benötigen Sie oder Ihre Benutzer [Zugriffsrechte](../../features/traits/about-folder-traits.md#role-based-access-controls) auf Datenquellen für die Eigenschaften.

>[!NOTE]
>
>Ordnereigenschaften können nicht direkt umbenannt werden. [Benennen Sie den zugehörigen Speicherordner](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) um, um den Namen der Ordnereigenschaft zu ändern.

## Löschen eines Ordnermerkmals {#delete-folder-trait}

Löschen Sie ein Ordnermerkmal, indem Sie den Speicherordner löschen, zu dem die Eigenschaft gehört.

<!-- delete-folder-trait.xml -->

1. **Zielgruppendaten &gt; Eigenschaften** , um zum **Eigenschaften** -Dashboard zu navigieren.
1. Löschen Sie im [!UICONTROL Trait Storage] Fenster einen Ordner, indem Sie ihn über ihn bewegen und auf das X-Symbol klicken.

   ![Schrittergebnis](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Sie können Ordnereigenschaften nicht löschen, wenn sie in einem Segmentausdruck verwendet werden. Navigieren Sie zum Abschnitt [Eigenschaften-Ansicht](../../features/traits/trait-details-page.md) , um zu sehen, welche Segmente die Ordnereigenschaft verwenden. Klicken Sie dann auf den Segmentnamen, um die [Segmentzusammenfassungsansicht](../../features/segments/segment-summary-view.md)zu öffnen. Dadurch können Sie Eigenschaften aus Segmentausdrücken entfernen.