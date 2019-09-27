---
description: Mit Ordnereigenschaften können Sie Eigenschaften, die sich im selben Ordner und in allen untergeordneten Ordnern befinden, automatisch in einem Zielgruppensegment zusammenfassen.
keywords: Schätzung der Segmentgröße;Auswahl
seo-description: Mit Ordnereigenschaften können Sie Eigenschaften, die sich im selben Ordner und in allen untergeordneten Ordnern befinden, automatisch in einem Zielgruppensegment zusammenfassen.
seo-title: Ordnereigenschaften
solution: Audience Manager
title: Ordnereigenschaften
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 9fa5a558c839da89286b1abdf77e835a92747c87

---


# Ordnereigenschaften: Info {#folder-traits-about}

[!UICONTROL Folder traits] können Sie Eigenschaften, die sich im selben Ordner und in allen untergeordneten Ordnern befinden, automatisch in einem Zielgruppensegment zusammenfassen.

## Vorteile der Verwendung von Ordnereigenschaften {#benefits}

Eine [!UICONTROL folder trait] enthält alle Eigenschaften in einem übergeordneten Ordner und die zugehörigen untergeordneten Ordner. Dadurch können Sie Ihre Benutzer automatisch segmentieren und auf verschiedene Ordnerebenen ausrichten. Angenommen, Sie haben eine Ordnerstruktur wie die folgende:

`*` Elektronik (übergeordnet)

    `*` Laptops (Kinder)

        `*` Marken (Enkel)

[!UICONTROL Folder traits] alle Benutzer in diesen Ordnern in einem automatisch erstellten Ordner qualifizieren [!DNL Electronics] [!UICONTROL Folder Trait] (basierend auf dem Namen des übergeordneten Ordners). Und dieser Prozess wiederholt sich selbst, wenn Sie die Dateistruktur nach unten verschieben. In diesem Fall erfassen Ordnereigenschaften alle Benutzer der Ordner "Laptops und Marken"in einem automatisch erstellten Laptop [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] sind in Segmentausdrücken auswählbar. Die Auswahl eines [!UICONTROL folder trait] Ordners entspricht der Auswahl aller Eigenschaften in diesem Ordner und dessen Unterordnern mit einer [!UICONTROL OR] Gruppierung.

![](assets/folder-traits-compare-border.jpg)

## Ordnereigenschaften - Neuigkeit und Häufigkeit {#folder-traits-realization}

Die Häufigkeit eines Ordnermerkmals ist die Summe der Realisierungen der Eigenschaften in seinem Ordner und seinen untergeordneten Ordnern. Die folgende Abbildung zeigt die Eigenschaften A, B und C, die im Ordner "Automobile"leben. Beachten Sie, dass alle Eigenschaften die folgenden Realisierungen aufweisen:

* Eigenschaft A: 5
* Eigenschaft B: 1
* Eigenschaft C: 1

In diesem Fall [!DNL Automobile Folder Trait] hat die Kommission 7 Erkenntnissen.

![](assets/folder_traits_rollup_border.png)

## Berichte zu Ordnereigenschaften {#folder-traits-reporting}

[!UICONTROL Folder traits] erfasst alle Benutzer aus den Eigenschaften in der Ordnerstruktur darunter. If you move a trait from a folder to another folder, the change propagates to our data collection servers just like a trait rule change. [](../../reference/system-components/components-data-collection.md) The reporting updates in the next reporting run to reflect this change across the reporting date ranges (1, 7, 14, 30, 60, 90). The old reporting numbers from the previous days will not change.

## Role-Based Access Controls (RBAC) Permissions {#role-based-access-controls}

For companies using  (), your users with the appropriate  permissions are able to change the data source associated to the . [!UICONTROL Role-Based Access Controls][!UICONTROL RBAC][!UICONTROL RBAC][!UICONTROL folder trait] A user must belong to a group with either of the following:

* `READ` and `WRITE` group permissions to a trait data source.
* `VIEW_ALL_TRAITS` and `EDIT_ALL_TRAITS` wild card permissions for trait data sources.

Learn how to assign  permissions in our administration documentation.[!UICONTROL RBAC][](../../features/administration/administration-overview.md#create-group)

## Limits and Other Considerations {#limits}

| Element | Beschreibung |
|---|---|
| Trait type | [!UICONTROL Onboarded traits] and  contribute at most 1 realization to a 's frequency.[!UICONTROL algorithmic traits][!UICONTROL folder trait] |
| Moving traits between folders | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second . [!UICONTROL folder trait] This means that if you delete or move a trait from the folder, the users in the trait's population will be unsegmented from the segments using the folder trait as a segment expression. <br> Beim Zuordnen von Adobe Analytics-Segmenten oder Report Suites zu Ihrer Experience Cloud-Organisation erstellt Audience Manager automatisch neue, entsprechende, schreibgeschützte Segmente und Eigenschaften. Sie können den Speicherort dieser Eigenschaften nicht in Audience Manager bearbeiten oder ändern. Änderungen, die Sie an Ihren zugeordneten Adobe Analytics-Segmenten oder Report Suites vornehmen, werden jedoch in Audience Manager übernommen. |
| Systemvariablen | [!UICONTROL Folder traits] kann nicht in Ereignisaufrufen mithilfe des `d_sid` Parameters ausgeführt werden. |
| Berichterstellung   | [!UICONTROL Folder traits] sind automatisch berechnete Eigenschaften und werden nicht in angezeigt **[!UICONTROL Overlap Reports]**. |