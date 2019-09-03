---
description: Mit Ordnereigenschaften können Sie Eigenschaften, die sich innerhalb desselben Ordners befinden, und alle untergeordneten Ordner in einem zielgruppenbasierten Segment zusammenfassen.
keywords: segmentgrößenschätzung; sse
seo-description: Mit Ordnereigenschaften können Sie Eigenschaften, die sich innerhalb desselben Ordners befinden, und alle untergeordneten Ordner in einem zielgruppenbasierten Segment zusammenfassen.
seo-title: Ordnereigenschaften über
solution: Audience Manager
title: Ordnereigenschaften über
uuid: e 561 ce 8 f -6 c 90-44 a 7-b 034-685533 f 29030
translation-type: tm+mt
source-git-commit: 263c55e6bd2c9ad7159306fc889b048d800c59da

---


# Ordnereigenschaften: Info {#folder-traits-about}

[!UICONTROL Folder traits] ermöglicht es Ihnen, Eigenschaften, die sich innerhalb desselben Ordners und alle untergeordneten Ordner befinden, in einem zielgruppenbasierten Segment automatisch zu aggregieren.

## Vorteile der Verwendung von Ordnereigenschaften {#benefits}

A [!UICONTROL folder trait] enthält alle Eigenschaften in einem übergeordneten Ordner und den zugehörigen untergeordneten Ordnern. Dadurch können Sie Ihre Benutzer automatisch auf unterschiedlichen Ordnerebenen segmentieren und ansprechen. Angenommen, Sie haben eine Ordnerstruktur wie das Folgende:

`*` Elektronik (übergeordnetes Element)

`*` Laptops (untergeordnetes Element)

`*` Marken (untergeordnetes Element)

[!UICONTROL Folder traits] alle Benutzer in diesen Ordnern automatisch erstellen [!DNL Electronics][!UICONTROL Folder Trait] (basierend auf dem Namen des übergeordneten Ordners). Und dieser Prozess wiederholt sich, wenn Sie die Dateistruktur nach unten verschieben. In diesem Fall erfassen die Ordnereigenschaften alle Benutzer in den Ordnern Laptops und Marken in einem automatisch erstellten Laptops [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] in Segmentausdrücken auswählbar. Die Auswahl von a [!UICONTROL folder trait] entspricht der Auswahl aller Eigenschaften in diesem Ordner und der zugehörigen Unterordner mit einer [!UICONTROL OR] Gruppierung.

![](assets/folder-traits-compare-border.jpg)

## Neugestaltung des Ordners - Neuigkeit und Häufigkeit {#folder-traits-realization}

Die Häufigkeitsanzahl einer Ordnereigenschaft ist die Summe der Neuausgaben der Eigenschaften im Ordner und dessen untergeordneten Ordnern. Die folgende Abbildung zeigt Eigenschaften A, B und C, die im Automobilordner live sind. Beachten Sie, dass jede der Eigenschaften über die folgenden Realizisierungen verfügt:

* Merkmal A: 5
* Merkmal B: 1
* Merkmal C: 1

In diesem Fall hat das [!DNL ]Automobil [!UICONTROL Folder Trait] 7 Neuschnitte.

![](assets/folder_traits_rollup_border.png)

## Ordnereigenschaftsberichte {#folder-traits-reporting}

[!UICONTROL Folder traits] erfassen Sie alle Benutzer aus den Eigenschaften in der Ordnerstruktur darunter. Wenn Sie eine Eigenschaft aus einem Ordner in einen anderen Ordner verschieben, wird die Änderung an unsere [Datenerfassungsserver](../../reference/system-components/components-data-collection.md) genau wie die Änderung der Eigenschaftenregel übertragen. Die Berichterstellungsaktualisierungen werden in der nächsten Berichterstellung aktualisiert, um diese Änderung in den Berichtsdatumsbereichen (1, 7, 14, 30, 60, 90) widerzuspiegeln. Die alten Berichtszahlen aus den vorherigen Tagen werden sich nicht ändern.

## Berechtigungen für Rollenbasierte Zugriffssteuerung (RBAC) {#role-based-access-controls}

Für Unternehmen, die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) verwenden, können Ihre Benutzer mit den entsprechenden [!UICONTROL RBAC] Berechtigungen die mit [!UICONTROL folder trait]der Datei verknüpfte Datenquelle ändern. Ein Benutzer muss einer Gruppe angehören, die einer der folgenden Elemente angehört:

* `READ` und `WRITE` Gruppenberechtigungen zu einer Eigenschaftsdatenquelle.
* `VIEW_ALL_TRAITS` und `EDIT_ALL_TRAITS` Platzhalterberechtigungen für Eigenschaftsdatenquellen.

Erfahren Sie, wie [!UICONTROL RBAC] Sie in unserer [Administrationsdokumentation Berechtigungen zuweisen](../../features/administration/administration-overview.md#create-group).

## Beschränkungen und weitere Überlegungen {#limits}

| Element | Beschreibung |
|---|---|
| Eigenschaftstyp | [!UICONTROL Onboarded traits] und [!UICONTROL algorithmic traits] bei der höchsten 1-Transformation zu einer [!UICONTROL folder trait]Frequenz beitragen. |
| Verschieben von Eigenschaften zwischen Ordnern | Wenn Sie eine Eigenschaft aus einem Ordner in einen anderen verschieben, wird diese vom ersten Ordnermerkmal abgetrennt und für die zweite [!UICONTROL folder trait]Eigenschaft qualifiziert. Wenn Sie also eine Eigenschaft aus dem Ordner löschen oder verschieben, werden die Benutzer in der Zielgruppe der Eigenschaften mithilfe der Ordnereigenschaft als Segmentausdruck nicht segmentiert. <br> Wenn Sie Adobe Analytics-Segmente oder Report Suites Ihrer Experience Cloud-Organisation zuordnen, erstellt Audience Manager automatisch neue, entsprechende, schreibgeschützte Segmente und Eigenschaften. Sie können den Speicherort dieser Eigenschaften nicht aus Audience Manager bearbeiten oder ändern. Alle Änderungen, die Sie an Ihren zugeordneten Adobe Analytics-Segmenten oder Report Suites vornehmen, werden jedoch in Audience Manager übernommen. |
| Systemvariablen | [!UICONTROL Folder traits] kann in Ereignisaufrufen mithilfe des `d_sid` Parameters nicht lokalisiert werden. |
| Berichterstellung   | [!UICONTROL Folder traits] sind automatisch berechnete Eigenschaften und werden nicht in **[!UICONTROL Overlap Reports]** angezeigt. |