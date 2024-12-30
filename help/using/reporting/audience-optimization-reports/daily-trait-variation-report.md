---
description: Dieser Bericht gibt eine Liste von Eigenschaften zurück, die in den 30 Tagen vor dem/den ausgewählten Datum(en) mindestens 10.000-mal realisiert wurden und eine Standardabweichung von 1,7 in beiden Richtungen im selben Zeitintervall haben. Der Bericht hilft Ihnen dabei zu bewerten, wie die Anzahl der Impressionen von eindeutigen Benutzern in einer Eigenschaft im Laufe der Zeit schwankt.
seo-description: This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.
seo-title: Daily Trait Variation Report
solution: Audience Manager
title: Täglicher Bericht zu Eigenschaftsvarianten
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization Reports
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 0%

---

# Täglicher Bericht zu Eigenschaftsvarianten {#daily-trait-variation-report}

Dieser Bericht gibt eine Liste von Eigenschaften zurück, die in den 30 Tagen vor dem/den ausgewählten Datum(en) mindestens 10.000-mal realisiert wurden und eine Standardabweichung von 1,7 in beiden Richtungen im selben Zeitintervall haben. Der Bericht hilft Ihnen dabei zu bewerten, wie die Anzahl der Impressionen von eindeutigen Benutzern in einer Eigenschaft im Laufe der Zeit schwankt.

>[!NOTE]
>
>Der Bericht „Tägliche Eigenschaftsvariation“ in Audience Manager entspricht den RBAC-Prinzipien. Sie können nur Eigenschaften aus Datenquellen sehen, auf die Sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md), der Sie angehören.

Die Standardabweichung misst den Grad der Abweichung oder Streuung vom Mittelwert (oder dem Durchschnitt/erwarteten Wert). Eine geringe Standardabweichung bedeutet, dass die Datenpunkte tendenziell sehr nahe am Mittelwert liegen. Eine hohe Standardabweichung bedeutet, dass die Datenpunkte über einen großen Wertebereich verteilt sind.

![](assets/daily_trait_variation.png)

In der [!UICONTROL Date] können Sie ein oder mehrere Daten für Ihren Bericht auswählen. Unten in der Liste wird ein farbcodiertes Balkendiagramm angezeigt, das den Bereich der Standardabweichung für alle Eigenschaften über alle ausgewählten Datumsangaben hinweg visuell darstellt. Die schwarze senkrechte Linie zeigt den Mittelwert an.

Die mittlere Spalte enthält eine Liste von Eigenschaften, die durch [!UICONTROL Trait ID] und [!UICONTROL Trait Name] gekennzeichnet sind. Klicken Sie auf eine Eigenschaft, um auf ein Popup-Dialogfeld zuzugreifen, in dem Sie aus den folgenden Optionen auswählen können:

* **Nur beibehalten** Entfernt alle anderen Eigenschaften aus dem Bericht und zeigt nur Daten für diese Eigenschaft an.
* **Ausschließen:** Entfernt diese Eigenschaft aus dem Bericht und zeigt Daten für alle anderen Eigenschaften an. Sie können mehrere Eigenschaften ausschließen.
* **Daten anzeigen:** Ermöglicht das Anzeigen von Daten für diese Zeile. Sie können auch alle Zeilen als Textdatei herunterladen.

Die Spalte [!UICONTROL Standard Deviation] zeigt farbcodierte Balkendiagramme an, die die Standardabweichung für jedes Merkmal über das ausgewählte Intervall anzeigen. Rote Balken zeigen Merkmale mit einer negativen Standardabweichung an (Datenpunkte liegen tendenziell unter dem Mittelwert). Grüne Balken zeigen Merkmale mit einer positiven Standardabweichung an (Datenpunkte liegen tendenziell über dem Mittelwert). Bewegen Sie den Mauszeiger über eine beliebige Leiste, um ein Popup-Dialogfeld mit weiteren Informationen und Optionen zum Beibehalten oder Ausschließen dieser Eigenschaft und zum Anzeigen weiterer Informationen anzuzeigen.

Unten im Bericht werden Symbole angezeigt, mit denen Sie Daten in verschiedenen Formaten exportieren, alle Änderungen rückgängig machen können, die Sie am Bericht vorgenommen haben (z. B. Eigenschaften ausschließen), automatische Aktualisierungen aktivieren oder deaktivieren und die Berichtsdaten aktualisieren können. Siehe [Berichtssymbole und -werkzeuge - Erklärung](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Nutzungsszenarios {#use-cases}

**Beispiel #1**: Dieser Bericht kann in Situationen, in denen Sie Merkmale mit einem hohen Saisongrad haben, äußerst nützlich sein. Nehmen wir beispielsweise an, Ihr Online-Store testet saisonale Werbeaktionen verschiedener Art und Preise. In [!DNL Audience Manager] sind folgende Eigenschaften definiert:

* `productPage == "December Promotion"`
* `price > "500"`

Angenommen, Sie führen den [!UICONTROL Daily Trait Variation] am 20. Dezember aus und bemerken in den letzten 30 Tagen eine solide positive Abweichung bei den oben genannten Eigenschaften. Dies kann darauf hindeuten, dass Ihre Besucher nach den Produkten suchen, die in Ihrer saisonalen Promotion erwähnt werden. Um diesen Trend zu nutzen, können Sie sich stärker bemühen, Kreative für diese bestimmte Produktkategorie auf Besucher abzustimmen, die an ihnen interessiert sind.

**Beispiel #2**: Dieser Bericht kann Ihnen dabei helfen, Anomalien beim Targeting im Zusammenhang mit Tagging-Problemen oder falschen Eigenschaftskonfigurationen zu identifizieren. Angenommen, Sie haben die folgende Eigenschaft basierend auf den Kategorien Ihres Online-Shops definiert:

* `productPage == "smartphones"`

Aufgrund einer Neukonfiguration Ihres Geschäfts teilen Sie die Smartphones-Seite basierend auf Markennamen in mehrere Seiten auf. Sie vergessen jedoch, die in [!DNL Audience Manager] definierten Eigenschaften zu aktualisieren.

Einen Monat später führen Sie den [!UICONTROL Daily Trait Variation] aus und bemerken eine große negative Abweichung vom `productPage == "smartphones"` Merkmal, obwohl die Besucherzahl laut Website-Analyse gestiegen ist. Basierend auf diesen Informationen stellen Sie fest, dass Sie die Eigenschaften in [!DNL Audience Manager] für Ihre neuen Produktseiten nicht aktualisiert haben, sodass Sie wissen, dass Sie die folgenden Eigenschaften erstellen müssen:

* productPage == „samsung“
* productPage == „apple“
* productPage == „huawei“

In diesem Fall stellt Ihre Zielgruppe fest, dass sie sich für die neu erstellten Eigenschaften qualifiziert.
