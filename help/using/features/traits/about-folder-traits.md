---
description: Mit Ordnereigenschaften können Sie Eigenschaften, die sich im selben Ordner und in allen untergeordneten Ordnern befinden, automatisch in ein Zielgruppensegment Aggregat.
keywords: Schätzung der Segmentgröße;Auswahl
seo-description: Mit Ordnereigenschaften können Sie Eigenschaften, die sich im selben Ordner und in allen untergeordneten Ordnern befinden, automatisch in ein Zielgruppensegment Aggregat.
seo-title: Ordnereigenschaften
solution: Audience Manager
title: Ordnereigenschaften
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 1%

---


# Ordnereigenschaften: Info {#folder-traits-about}

[!UICONTROL Folder traits] können Sie Eigenschaften, die sich im selben Ordner und in allen untergeordneten Ordnern befinden, automatisch in ein Zielgruppensegment Aggregat setzen.

## Vorteile der Verwendung von Ordnereigenschaften {#benefits}

Ein [!UICONTROL folder trait] enthält alle Eigenschaften in einem übergeordneten Ordner und die zugehörigen untergeordneten Ordner. Auf diese Weise können Sie Ihre Benutzer automatisch auf verschiedenen Ordnerebenen segmentieren und Zielgruppen vornehmen. Angenommen, Sie haben eine Ordnerstruktur wie die folgende:

`*` Elektronik (übergeordnet)

    `*` Laptops (untergeordnet)

        `*` Marken (Enkel)

[!UICONTROL Folder traits] alle Benutzer in diesen Ordnern in einem automatisch erstellten Ordner qualifizieren  [!DNL Electronics] [!UICONTROL Folder Trait] (basierend auf dem Namen des übergeordneten Ordners). Und dieser Prozess wiederholt sich selbst, wenn Sie die Dateistruktur nach unten verschieben. In diesem Fall erfassen Ordnereigenschaften alle Benutzer in den Ordnern Laptops und Marken in einem automatisch erstellten Laptop [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] sind in Segmentwerten auswählbar. Die Auswahl von [!UICONTROL folder trait] entspricht der Auswahl aller Eigenschaften in diesem Ordner und dessen Unterordnern mit einer [!UICONTROL OR]-Gruppierung.

![](assets/folder-traits-compare-border.jpg)

## Ordnereigenschaften - Neuigkeit und Häufigkeit {#folder-traits-realization}

Die Häufigkeit eines Ordnermerkmals ist die Summe der Realisierungen der Eigenschaften in seinem Ordner und seinen untergeordneten Ordnern. Die folgende Abbildung zeigt die Eigenschaften A, B und C, die im Ordner &quot;Automobile&quot;leben. Beachten Sie, dass alle Eigenschaften die folgenden Realisierungen aufweisen:

* Eigenschaft A: 5
* Eigenschaft B: 1
* Eigenschaft C: 3

In diesem Fall hat das [!DNL Automobile Folder Trait] 7 Realisierungen.

![](assets/folder_traits_rollup_border.png)

## Ordnereigenschaften-Berichte {#folder-traits-reporting}

[!UICONTROL Folder traits] erfasst alle Benutzer aus den Eigenschaften in der Ordnerstruktur darunter. Wenn Sie eine Eigenschaft aus einem Ordner in einen anderen Ordner verschieben, wird die Änderung genau wie bei einer Änderung der Eigenschaftsregel auf unsere [Datenerfassungsserver](../../reference/system-components/components-data-collection.md) übertragen. Die Berichte-Aktualisierungen im nächsten Berichte werden ausgeführt, um diese Änderung über die Datumsbereiche des Berichte (1, 7, 14, 30, 60, 90) hinweg widerzuspiegeln. Die alten Berichte aus den Vortagen bleiben unverändert.

## Rollenbasierte Zugriffskontrollen (RBAC) - Berechtigungen {#role-based-access-controls}

Bei Firmen mit [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) können Ihre Benutzer mit den entsprechenden [!UICONTROL RBAC]-Berechtigungen die Datenquelle ändern, die mit [!UICONTROL folder trait] verknüpft ist. Ein Benutzer muss zu einer Gruppe mit einer der folgenden Komponenten gehören:

* `READ` und  `WRITE` Gruppenberechtigungen für eine Eigenschaftsdatenquelle.
* `VIEW_ALL_TRAITS` und  `EDIT_ALL_TRAITS` Platzhalterberechtigungen für Eigenschaftendatenquellen.

Erfahren Sie, wie Sie [!UICONTROL RBAC] Berechtigungen in unserer [Administrationsdokumentation](../../features/administration/administration-overview.md#create-group) zuweisen.

## Beschränkungen und sonstige Erwägungen {#limits}

| Element | Beschreibung |
|---|---|
| Eigenschaftstyp | [!UICONTROL Onboarded traits] und  [!UICONTROL algorithmic traits] tragen maximal 1 Realisierung zu einer  [!UICONTROL folder trait]Frequenz bei. |
| Eigenschaften zwischen Ordnern verschieben | Wenn Sie eine Eigenschaft aus einem Ordner in einen anderen verschieben, wird diese Eigenschaft aus der ersten Ordnereigenschaft ausgeschlossen und für die zweite [!UICONTROL folder trait] qualifiziert. Wenn Sie also eine Eigenschaft aus dem Ausdruck löschen oder verschieben, werden die Benutzer in der Eigenschaftspopulation mithilfe der Ordnereigenschaft nicht segmentiert. <br> Beim Zuordnen von Adobe Analytics-Segmenten oder Report Suites zu Ihrer Experience Cloud-Organisation erstellt Audience Manager automatisch neue, zugehörige, schreibgeschützte Segmente und Eigenschaften. Sie können die Position der Datenspeicherung dieser Eigenschaften nicht von Audience Manager aus bearbeiten oder ändern. Änderungen, die Sie an Ihren zugeordneten Adobe Analytics-Segmenten oder Report Suites vornehmen, werden jedoch in Audience Manager übernommen. |
| Systemvariablen | [!UICONTROL Folder traits] kann nicht in Ereignis-Aufrufen mithilfe des  `d_sid` Parameters ausgeführt werden. |
| Berichterstellung | [!UICONTROL Folder traits] sind automatisch berechnete Eigenschaften und werden nicht in angezeigt  **[!UICONTROL Overlap Reports]**. |