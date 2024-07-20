---
description: Mit Ordnereigenschaften können Sie Eigenschaften, die sich im selben Ordner und in allen untergeordneten Ordnern befinden, automatisch in ein Zielgruppensegment aggregieren.
keywords: Schätzung der Segmentgröße; verwenden
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: Ordnereigenschaften Info
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# Ordnereigenschaften: Info {#folder-traits-about}

Mit [!UICONTROL Folder traits] können Sie Eigenschaften, die sich im selben Ordner und in allen untergeordneten Ordnern befinden, automatisch in ein Zielgruppensegment aggregieren.

## Vorteile der Verwendung von Ordnereigenschaften {#benefits}

Ein [!UICONTROL folder trait] enthält alle Eigenschaften in einem übergeordneten Ordner und die zugehörigen untergeordneten Ordner. Auf diese Weise können Sie Ihre Benutzer automatisch segmentieren und auf unterschiedlichen Ordnerebenen ansprechen. Angenommen, Sie haben eine Ordnerstruktur wie die folgende:

`*` Elektronik (übergeordnet)

    `*` Laptops (untergeordnet)

        `*` Marken (Enkel)

[!UICONTROL Folder traits] qualifiziert alle Benutzer in diesen Ordnern in einem automatisch erstellten [!DNL Electronics] [!UICONTROL Folder Trait] (basierend auf dem Namen des übergeordneten Ordners). Und dieser Prozess wiederholt sich, während Sie die Dateistruktur nach unten verschieben. In diesem Fall erfassen Ordnereigenschaften alle Benutzer in den Ordnern Laptops und Marken in einem automatisch erstellten Laptop [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] kann in Segmentausdrücken ausgewählt werden. Die Auswahl von [!UICONTROL folder trait] entspricht der Auswahl aller Eigenschaften in diesem Ordner und dessen Unterordnern mit einer [!UICONTROL OR] -Gruppierung.

![](assets/folder-traits-compare-border.jpg)

## Realisierung von Ordnereigenschaften - Neuigkeit und Häufigkeit {#folder-traits-realization}

Die Häufigkeitsanzahl einer Ordnereigenschaft ist die Summe der Realisierungen der Eigenschaften in ihrem Ordner und den untergeordneten Ordnern. Die folgende Abbildung zeigt die Eigenschaften A, B und C, die sich im Ordner &quot;Automobile&quot;befinden. Beachten Sie, dass jede Eigenschaft die folgenden Realisierungen aufweist:

* Eigenschaft A: 5
* Eigenschaft B: 1
* Eigenschaft C: 1

In diesem Fall hat der [!DNL Automobile Folder Trait] 7 Realisierungen.

![](assets/folder_traits_rollup_border.png)

## Berichterstellung zu Ordnereigenschaften {#folder-traits-reporting}

[!UICONTROL Folder traits] erfasst alle Benutzer aus den Eigenschaften in der Ordnerstruktur darunter. Wenn Sie eine Eigenschaft aus einem Ordner in einen anderen Ordner verschieben, wird die Änderung wie bei einer Änderung der Eigenschaftsregel auf unsere [Datenerfassungsserver](../../reference/system-components/components-data-collection.md) übertragen. Die im nächsten Berichtablauf aktualisierten Berichte spiegeln diese Änderung in den Datumsbereichen der Berichterstellung wider (1, 7, 14, 30, 60, 90). Die alten Berichtszahlen aus den vorherigen Tagen werden sich nicht ändern.

## Rollenbasierte Zugriffssteuerungsberechtigungen (RBAC) {#role-based-access-controls}

Bei Unternehmen, die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) verwenden, können Ihre Benutzer mit den entsprechenden [!UICONTROL RBAC] -Berechtigungen die mit [!UICONTROL folder trait] verknüpfte Datenquelle ändern. Ein Benutzer muss zu einer Gruppe mit einer der folgenden Eigenschaften gehören:

* Gruppenberechtigungen für `READ` und `WRITE` für eine Eigenschaftsdatenquelle.
* `VIEW_ALL_TRAITS` - und `EDIT_ALL_TRAITS` Platzhalterberechtigungen für Eigenschaftsdatenquellen.

Erfahren Sie, wie Sie in unserer [Administrationsdokumentation](../../features/administration/administration-overview.md#create-group) [!UICONTROL RBAC] -Berechtigungen zuweisen.

## Beschränkungen und sonstige Aspekte {#limits}

| Element | Beschreibung |
|---|---|
| Eigenschaftstyp | [!UICONTROL Onboarded traits] und [!UICONTROL algorithmic traits] tragen maximal 1 Realisierung zur Häufigkeit eines [!UICONTROL folder trait] bei. |
| Verschieben von Eigenschaften zwischen Ordnern | Wenn Sie eine Eigenschaft aus einem Ordner in einen anderen verschieben, wird diese Eigenschaft aus der ersten Ordnereigenschaft ausgeschlossen und für die zweite [!UICONTROL folder trait] qualifiziert. Das bedeutet, dass beim Löschen oder Verschieben einer Eigenschaft aus dem Ordner die Benutzer in der Population der Eigenschaft nicht aus den Segmenten segmentiert werden, die die Ordnereigenschaft als Segmentausdruck verwenden. <br> Beim Zuordnen von Adobe Analytics-Segmenten oder Report Suites zu Ihrer Experience Cloud-Organisation erstellt Audience Manager automatisch neue, übereinstimmende, schreibgeschützte Segmente und Eigenschaften. Sie können den Speicherort dieser Eigenschaften nicht über Audience Manager bearbeiten oder ändern. Änderungen, die Sie jedoch an Ihren zugeordneten Adobe Analytics-Segmenten oder Report Suites vornehmen, werden in Audience Manager übernommen. |
| Systemvariablen | [!UICONTROL Folder traits] kann nicht in Ereignisaufrufen mit dem Parameter `d_sid` realisiert werden. |
| Berichterstellung   | [!UICONTROL Folder traits] sind automatisch berechnete Eigenschaften und werden nicht in **[!UICONTROL Overlap Reports]** angezeigt. |
