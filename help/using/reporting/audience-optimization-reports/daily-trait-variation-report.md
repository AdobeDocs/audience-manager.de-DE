---
description: Dieser Bericht gibt eine Liste der Eigenschaften zurück, die mindestens 10.000 Mal in den letzten 30 Tagen vor dem (n) ausgewählten Datum (n) lokalisiert wurden und eine Standardabweichung größer oder gleich 1.7 in beiden Richtungen im selben Zeitintervall haben. Mit dem Bericht können Sie bewerten, wie viele Impressionen von Unique Users in einer Eigenschaftsvariablen im Laufe der Zeit schwanken.
seo-description: Dieser Bericht gibt eine Liste der Eigenschaften zurück, die mindestens 10.000 Mal in den letzten 30 Tagen vor dem (n) ausgewählten Datum (n) lokalisiert wurden und eine Standardabweichung größer oder gleich 1.7 in beiden Richtungen im selben Zeitintervall haben. Mit dem Bericht können Sie bewerten, wie viele Impressionen von Unique Users in einer Eigenschaftsvariablen im Laufe der Zeit schwanken.
seo-title: Bericht zu täglichen Eigenschaften
solution: Audience Manager
title: Bericht zu täglichen Eigenschaften
uuid: 4 e 82 bb 17-d 447-4 ed 1-a 4 fc-e 15 b 0 f 1 b 47 f 0
translation-type: tm+mt
source-git-commit: 8f2ec880cbbe2f516ebc240a712337dc09c4e7f7

---


# Daily Trait Variation Report {#daily-trait-variation-report}

Dieser Bericht gibt eine Liste der Eigenschaften zurück, die mindestens 10.000 Mal in den letzten 30 Tagen vor dem (n) ausgewählten Datum (n) lokalisiert wurden und eine Standardabweichung größer oder gleich 1.7 in beiden Richtungen im selben Zeitintervall haben. Mit dem Bericht können Sie bewerten, wie viele Impressionen von Unique Users in einer Eigenschaftsvariablen im Laufe der Zeit schwanken.

>[!NOTE]
>
>Der Bericht "Tägliche Eigenschaften" in Audience Manager erfüllt RBAC-Prinzipien. You can only see traits from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

Standardabweichung misst die Größe oder Streuung aus dem arithmetischen Mittel (oder den durchschnittlichen/erwarteten Wert). Eine niedrige Standardabweichung bedeutet, dass die Datenpunkte tendenziell sehr nah am arithmetischen Mittel liegen. Eine hohe Standardabweichung zeigt an, dass die Datenpunkte über einen breiten Wertebereich verteilt sind.

![](assets/daily_trait_variation.png)

Use the [!UICONTROL Date] list to select one or more dates for your report. Am unteren Rand der Liste wird ein farbcodiertes Balkendiagramm angezeigt, das einen visuellen Vertreter für den Bereich der Standardabweichung für alle ausgewählten Daten bereitstellt. Die schwarze vertikale Linie zeigt das arithmetische Mittel an.

The middle column contains a list of traits, identified by [!UICONTROL Trait ID] and [!UICONTROL Trait Name]. Klicken Sie auf eine beliebige Eigenschaft, um ein Popup-Dialogfeld aufzurufen, mit dem Sie aus den folgenden Optionen auswählen können:

* **Nur beibehalten:** Entfernt alle anderen Eigenschaften aus dem Bericht und zeigt nur Daten für diese Eigenschaft an.
* **Ausschließen:** Entfernt diese Eigenschaft aus dem Bericht und zeigt Daten zu allen anderen Eigenschaften an. Sie können mehrere Eigenschaften ausschließen.
* **Daten anzeigen:** Ermöglicht die Anzeige von Daten für diese Zeile. Sie können auch alle Zeilen als Textdatei herunterladen.

The [!UICONTROL Standard Deviation] column displays color-coded bar charts that display the standard deviation for each trait over the selected interval. Rote Balken weisen auf Eigenschaften mit einer negativen Standardabweichung hin (Datenpunkte sind tendenziell unter dem arithmetischen Mittel). Grüne Balken weisen auf Eigenschaften mit einer positiven Standardabweichung hin (Datenpunkte reichen tendenziell über dem Mittelwert). Bewegen Sie den Mauszeiger über eine Leiste, um ein Popup-Dialogfeld mit weiteren Informationen und Optionen anzuzeigen, um diese Eigenschaft beizubehalten oder auszuklammern und weitere Informationen anzuzeigen.

Die Symbole werden unten im Bericht angezeigt, mit dem Sie Daten in verschiedenen Formaten exportieren können, alle Änderungen zurücksetzen können, die Sie am Bericht vorgenommen haben (z. B. Eigenschaften ausschließen), automatische Aktualisierungen aktivieren oder deaktivieren und die Daten des Berichts aktualisieren. See [Report Icons and Tools Explained](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Nutzungsszenarios {#use-cases}

**Beispiel 1**: Dieser Bericht kann in Situationen mit einer hohen Saisonalität sehr nützlich sein. Nehmen wir an, Ihr Online-Shop testet Saisonpromotions verschiedener Typen und Preise. You have the following traits defined in [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Say you run the [!UICONTROL Daily Trait Variation] report on the 20th of December and you notice a solid positive deviation on the above mentioned traits in the past 30 days. Dies kann empfehlen, dass Ihre Besucher nach den Produkten suchen, die in Ihrer Saisonpromotion erwähnt werden. Um diesen Trend nutzen zu können, können Sie mehr Bemühungen in das Targeting kreativer Elemente für diese spezifische Produktkategorie für Besucher investieren, die daran interessiert sind.

**Beispiel 2**: Dieser Bericht kann Ihnen helfen, Targeting-Anomalien in Bezug auf Tagging-Probleme oder fehlerhafte Fehlermeldungen zu identifizieren. Angenommen, Sie haben die folgende Eigenschaft basierend auf den Kategorien Ihres Online-Shops definiert:

* `productPage == "smartphones"`

Aufgrund einer Neukonfiguration Ihres Speichers teilen Sie die Smartphone-Seite auf Grundlage von Markennamen in mehrere Seiten auf. However, you forget to update the traits defined in [!DNL Audience Manager].

One month later, you run the [!UICONTROL Daily Trait Variation] report and notice a large negative deviation on the `productPage == "smartphones"` trait, although your visitor number has increased, according to your site analytics. Based on this information, you realize that you haven't updated the traits in [!DNL Audience Manager] for your new product pages, so you know that you need to create the following traits:

* Productpage = = "samsung"
* Productpage = = "apple"
* Productpage = = "huawei"

Anschließend sehen Sie die Zielgruppe, die für die neu erstellten Eigenschaften qualifiziert ist.
