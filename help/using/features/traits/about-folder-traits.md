---
description: Mit Ordnereigenschaften können Sie Eigenschaften, die sich im selben Ordner und in allen untergeordneten Ordnern befinden, automatisch in einem Zielgruppensegment zusammenfassen.
keywords: Schätzung der Segmentgröße;Auswahl
seo-description: Mit Ordnereigenschaften können Sie Eigenschaften, die sich im selben Ordner und in allen untergeordneten Ordnern befinden, automatisch in einem Zielgruppensegment zusammenfassen.
seo-title: Ordnereigenschaften
solution: Audience Manager
title: Ordnereigenschaften
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 263c55e6bd2c9ad7159306fc889b048d800c59da

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

In diesem Fall hat das [!DNL ]Automobil [!UICONTROL Folder Trait] 7 Realisierungen.

![](assets/folder_traits_rollup_border.png)

## Berichte zu Ordnereigenschaften {#folder-traits-reporting}

[!UICONTROL Folder traits] erfasst alle Benutzer aus den Eigenschaften in der Ordnerstruktur darunter. Wenn Sie eine Eigenschaft aus einem Ordner in einen anderen Ordner verschieben, wird die Änderung genau wie eine Änderung der Eigenschaftsregel auf unsere [Datenerfassungsserver](../../reference/system-components/components-data-collection.md) übertragen. Die Berichterstellung im nächsten Berichtslauf spiegelt diese Änderung in den Berichtszeiträumen (1, 7, 14, 30, 60, 90) wider. Die alten Berichtszahlen der vorherigen Tage bleiben unverändert.

## Rollenbasierte Zugriffssteuerungsberechtigungen {#role-based-access-controls}

Bei Unternehmen, die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) verwenden, können Ihre Benutzer mit den entsprechenden [!UICONTROL RBAC] Berechtigungen die der Datenquelle zugeordnete Datenquelle ändern [!UICONTROL folder trait]. Ein Benutzer muss zu einer Gruppe mit einer der folgenden Komponenten gehören:

* `READ` und `WRITE` Gruppenberechtigungen für eine Eigenschaftsdatenquelle.
* `VIEW_ALL_TRAITS` und `EDIT_ALL_TRAITS` Platzhalterberechtigungen für Datenquellen mit Eigenschaften.

Erfahren Sie, wie Sie [!UICONTROL RBAC] Berechtigungen in unserer [Verwaltungsdokumentation](../../features/administration/administration-overview.md#create-group)zuweisen.

## Beschränkungen und sonstige Erwägungen {#limits}

| Element | Beschreibung |
|---|---|
| Eigenschaftstyp | [!UICONTROL Onboarded traits] und [!UICONTROL algorithmic traits] tragen maximal 1 Realisierung zur Häufigkeit eines [!UICONTROL folder trait]Ereignisses bei. |
| Eigenschaften zwischen Ordnern verschieben | Wenn Sie eine Eigenschaft aus einem Ordner in einen anderen verschieben, wird diese Eigenschaft aus der ersten Ordnereigenschaft deaktiviert und für die zweite qualifiziert [!UICONTROL folder trait]. Wenn Sie also eine Eigenschaft aus dem Ordner löschen oder verschieben, werden die Benutzer in der Eigenschaftspopulation mithilfe der Ordnereigenschaft als Segmentausdruck von den Segmenten getrennt. <br> Beim Zuordnen von Adobe Analytics-Segmenten oder Report Suites zu Ihrer Experience Cloud-Organisation erstellt Audience Manager automatisch neue, entsprechende, schreibgeschützte Segmente und Eigenschaften. Sie können den Speicherort dieser Eigenschaften nicht in Audience Manager bearbeiten oder ändern. Änderungen, die Sie an Ihren zugeordneten Adobe Analytics-Segmenten oder Report Suites vornehmen, werden jedoch in Audience Manager übernommen. |
| Systemvariablen | [!UICONTROL Folder traits] kann nicht in Ereignisaufrufen mithilfe des `d_sid` Parameters ausgeführt werden. |
| Berichterstellung   | [!UICONTROL Folder traits] sind automatisch berechnete Eigenschaften und werden nicht in angezeigt **[!UICONTROL Overlap Reports]**. |