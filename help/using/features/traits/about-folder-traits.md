---
description: Mit Ordnereigenschaften können Sie Eigenschaften, die sich innerhalb desselben Ordners befinden, und alle untergeordneten Ordner in einem zielgruppenbasierten Segment zusammenfassen.
keywords: segmentgrößenschätzung; sse
seo-description: Mit Ordnereigenschaften können Sie Eigenschaften, die sich innerhalb desselben Ordners befinden, und alle untergeordneten Ordner in einem zielgruppenbasierten Segment zusammenfassen.
seo-title: Ordnereigenschaften über
solution: Audience Manager
title: Ordnereigenschaften über
uuid: e 561 ce 8 f -6 c 90-44 a 7-b 034-685533 f 29030
translation-type: tm+mt
source-git-commit: c229bf71da5b07277811219cbf2794c3ca7bc89d

---


# Folder Traits: About {#folder-traits-about}

[!UICONTROL Folder traits] ermöglicht es Ihnen, Eigenschaften, die sich innerhalb desselben Ordners und alle untergeordneten Ordner befinden, in einem zielgruppenbasierten Segment automatisch zu aggregieren.

## Benefits of Using Folder Traits {#benefits}

A [!UICONTROL folder trait] contains all the traits in a parent folder and its associated child folders. Dadurch können Sie Ihre Benutzer automatisch auf unterschiedlichen Ordnerebenen segmentieren und ansprechen. Angenommen, Sie haben eine Ordnerstruktur wie das Folgende:

`*` Elektronik (übergeordnetes Element)

`*` Laptops (untergeordnetes Element)

`*` Marken (untergeordnetes Element)

[!UICONTROL Folder traits] alle Benutzer in diesen Ordnern automatisch erstellen [!DNL Electronics][!UICONTROL Folder Trait] (basierend auf dem Namen des übergeordneten Ordners). Und dieser Prozess wiederholt sich, wenn Sie die Dateistruktur nach unten verschieben. In this case, folder traits capture all of the users in the Laptops and Brands folders in an automatically created Laptops [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] in Segmentausdrücken auswählbar. Selecting a [!UICONTROL folder trait] is equivalent to selecting all the traits within that folder and its subfolders with an [!UICONTROL OR] grouping.

![](assets/folder-traits-compare-border.jpg)

## Folder Traits Realization - Recency and Frequency {#folder-traits-realization}

Die Häufigkeitsanzahl einer Ordnereigenschaft ist die Summe der Neuausgaben der Eigenschaften im Ordner und dessen untergeordneten Ordnern. Die folgende Abbildung zeigt Eigenschaften A, B und C, die im Automobilordner live sind. Beachten Sie, dass jede der Eigenschaften über die folgenden Realizisierungen verfügt:

* Merkmal A: 5
* Merkmal B: 1
* Merkmal C: 1

In this case, the [!DNL ]Automobile [!UICONTROL Folder Trait] has 7 realizations.

![](assets/folder_traits_rollup_border.png)

## Folder Trait Reporting {#folder-traits-reporting}

[!UICONTROL Folder traits] erfassen Sie alle Benutzer aus den Eigenschaften in der Ordnerstruktur darunter. If you move a trait from a folder to another folder, the change propagates to our [data collection servers](../../reference/system-components/components-data-collection.md) just like a trait rule change. Die Berichterstellungsaktualisierungen werden in der nächsten Berichterstellung aktualisiert, um diese Änderung in den Berichtsdatumsbereichen (1, 7, 14, 30, 60, 90, Lebensdauer) widerzuspiegeln. Die alten Berichtszahlen aus den vorherigen Tagen werden sich nicht ändern.

## Role-Based Access Controls (RBAC) Permissions {#role-based-access-controls}

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), your users with the appropriate [!UICONTROL RBAC] permissions are able to change the data source associated to the [!UICONTROL folder trait]. Ein Benutzer muss einer Gruppe angehören, die einer der folgenden Elemente angehört:

* `READ` und `WRITE` Gruppenberechtigungen zu einer Eigenschaftsdatenquelle.
* `VIEW_ALL_TRAITS` und `EDIT_ALL_TRAITS` Platzhalterberechtigungen für Eigenschaftsdatenquellen.

Learn how to assign [!UICONTROL RBAC] permissions in our [administration documentation](../../features/administration/administration-overview.md#create-group).

## Limits and Other Considerations {#limits}

| Element | Beschreibung |
|---|---|
| Eigenschaftstyp | [!UICONTROL Onboarded traits] und [!UICONTROL algorithmic traits] bei der höchsten 1-Transformation zu einer [!UICONTROL folder trait]Frequenz beitragen. |
| Verschieben von Eigenschaften zwischen Ordnern | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second [!UICONTROL folder trait]. Wenn Sie also eine Eigenschaft aus dem Ordner löschen oder verschieben, werden die Benutzer in der Zielgruppe der Eigenschaften mithilfe der Ordnereigenschaft als Segmentausdruck nicht segmentiert. <br> Wenn Sie Adobe Analytics-Segmente oder Report Suites Ihrer Experience Cloud-Organisation zuordnen, erstellt Audience Manager automatisch neue, entsprechende, schreibgeschützte Segmente und Eigenschaften. Sie können den Speicherort dieser Eigenschaften nicht aus Audience Manager bearbeiten oder ändern. Alle Änderungen, die Sie an Ihren zugeordneten Adobe Analytics-Segmenten oder Report Suites vornehmen, werden jedoch in Audience Manager übernommen. |
| Systemvariablen | [!UICONTROL Folder traits] kann in Ereignisaufrufen mithilfe des `d_sid` Parameters nicht lokalisiert werden. |
| Berichterstellung   | [!UICONTROL Folder traits] sind automatisch berechnete Eigenschaften und werden nicht in **[!UICONTROL Overlap Reports]** angezeigt. |