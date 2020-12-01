---
description: Aufstockung von Eigenschaftenrealisierungen, um historische Audiencen zu erfassen und den Verlust relevanter Daten vor dem Erstellungsdatum einer Eigenschaft zu vermeiden.
seo-description: Aufstockung von Eigenschaftenrealisierungen, um historische Audiencen zu erfassen und den Verlust relevanter Daten vor dem Erstellungsdatum einer Eigenschaft zu vermeiden.
seo-title: Aufstocken von Eigenschaftsrealisierungen
title: Aufstocken von Eigenschaftsrealisierungen
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---


# Aufstocken von Eigenschaftsrealisierungen {#backfill-trait-realizations}

Aufstockung von Eigenschaftenrealisierungen, um historische Audiencen zu erfassen und den Verlust relevanter Daten vor dem Erstellungsdatum einer Eigenschaft zu vermeiden.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] ist eine Premium-Funktion, die den Audience Manager durch die Erschließung zusätzlicher Nutzungsszenarien verbessert. Die Aufstockung erfordert zusätzliche Verarbeitungsleistung und steht allen Audience Manager zu inkrementellen Kosten zur Verfügung. Für weitere Informationen wenden Sie sich bitte an Ihren Vertriebsmitarbeiter in der Adobe.

Wenn Sie Eigenschaften aus nicht verwendeten Signalen erstellen, können Sie die Eigenschaften über einen bestimmten Zeitraum aufstocken. [!DNL Audience Manager] erfasst die Verlaufsdaten zu Audiencen, die für die neue Eigenschaft infrage kommen, und speichert sie im entsprechenden Profil. Sie können das **[!UICONTROL Backfill Options]** im Abschnitt [!UICONTROL Trait Expression] des **[Eigenschaften-Builders](../../features/traits/about-trait-builder.md)** sehen.

>[!NOTE]
>
>Sie können Eigenschaftenrealisierungen für regelbasierte und Onboarded-Eigenschaften aufstocken.

So stocken Sie Eigenschaftenrealisierungen auf:

1. Gehen Sie zu [!UICONTROL Audience Data > Signals > Search] und führen Sie eine Signalsuche aus oder verwenden Sie das [Signal-Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md), um die in der neuen Eigenschaft zu verwendenden Signale zu identifizieren.
1. Erstellen Sie eine neue Eigenschaft basierend auf den gewünschten Signalen.
1. Verwenden Sie das **[!UICONTROL Backfill Options]** im Abschnitt **[!UICONTROL Trait Expression]**, um das Zeitintervall auszuwählen, für das Sie Eigenschaftenrealisierungen aufstocken möchten. Vordefinierte Aufstockungsintervalle umfassen 1, 7, 14 und 30 Tage. Sie können auch einen benutzerdefinierten Datumsbereich von bis zu 30 Tagen auswählen.

   ![trait-backfill](assets/signals-trait-backfill.png)

1. (Optional) Klicken Sie im Abschnitt **[!UICONTROL Estimated Trait Realizations]** auf **[!UICONTROL Estimate Realizations]**, um die geschätzten Werte für [!UICONTROL Unique Trait Realizations] und [!UICONTROL Total Trait Population] für die hinterfüllten Eigenschaften der letzten 7 Tage anzuzeigen.

   ![Schätzung-Eigenschaften-Realisierungen](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Für Eigenschaften mit Ausdrücken, die die folgenden Operatoren verwenden, stehen keine Trait-Aufstockung und -Schätzung zur Verfügung:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Erstellen Sie die Eigenschaft.

Nachdem Sie die Eigenschaft erstellt haben, sehen Sie, wie die in der Realisierungsstatistik enthaltenen rückständigen Realisierungen aussehen.

Sehen Sie sich das unten stehende Video an, um sich einen Video mit einer Anleitung zum Aufstocken von Eigenschaften anzusehen.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Traffic-Aufstockungslatenz {#trait-backfilling-latency}

Neu erstellter Beginn Eigenschaften, der Audiencen zwei bis drei Stunden nach der Erstellung erfasst. Aufgrund des großen Datenvolumens, das [!DNL Audience Manager] täglich ausführt, wird die aufgestockte Population nicht sofort in den Diagrammen [!UICONTROL Unique Trait Realizations] und [!UICONTROL Total Trait Population] angezeigt.

Audience Manager aktualisiert das [!UICONTROL Trait Graph], wobei die aufgestockte Population innerhalb von 48 Stunden nach Erstellung der Eigenschaften aktualisiert wird.

## Maximal zulässige Traffic-Aufstockung {#trait-backfilling-limit}

[!UICONTROL Data Explorer] ermöglicht es Ihnen, bis zu 50 Eigenschaften pro Monat aufzustocken, wobei der Zähler für die Aufstockung am 1. Tag jedes Monats zurückgesetzt wird.

>[!NOTE]
>
>Die Quote für die Rückfüllung der Eigenschaften wird nicht von den Vormonaten übernommen. Wenn Sie z. B. diesen Monat 30 Eigenschaften aufstocken, wird das Eigenschafts-Aufstockungskontingent für den nächsten Monat auf 50, nicht auf 70 zurückgesetzt.

## Auswirkungen auf Berichte {#reporting-impact}

Rückgefüllte Eigenschaftenrealisierungen werden in den Metriken [!UICONTROL Unique Trait Realizations] und [!UICONTROL Total Trait Population] angezeigt, da [!DNL Audience Manager] historische Signale in Eigenschaftenrealisierungen umwandelt.

Die Variablen [!UICONTROL Trait Graph], [!UICONTROL General Reports] und [!UICONTROL Trend Reports] werden jedoch nicht nachträglich mit historischen Metriken aktualisiert, die vor dem Erstellungsdatum der Eigenschaft aufgestockt wurden.