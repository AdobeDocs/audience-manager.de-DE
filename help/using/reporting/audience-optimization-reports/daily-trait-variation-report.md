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


# Bericht zu täglichen Eigenschaften {#daily-trait-variation-report}

Dieser Bericht gibt eine Liste der Eigenschaften zurück, die mindestens 10.000 Mal in den letzten 30 Tagen vor dem (n) ausgewählten Datum (n) lokalisiert wurden und eine Standardabweichung größer oder gleich 1.7 in beiden Richtungen im selben Zeitintervall haben. Mit dem Bericht können Sie bewerten, wie viele Impressionen von Unique Users in einer Eigenschaftsvariablen im Laufe der Zeit schwanken.

>[!NOTE]
>
>Der Bericht &quot;Tägliche Eigenschaften&quot; in Audience Manager erfüllt RBAC-Prinzipien. Sie können nur Eigenschaften aus Datenquellen anzeigen, auf die Sie Zugriff auf die [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md) haben, zu der Sie gehören.

Standardabweichung misst die Größe oder Streuung aus dem arithmetischen Mittel (oder den durchschnittlichen/erwarteten Wert). Eine niedrige Standardabweichung bedeutet, dass die Datenpunkte tendenziell sehr nah am arithmetischen Mittel liegen. Eine hohe Standardabweichung zeigt an, dass die Datenpunkte über einen breiten Wertebereich verteilt sind.

![](assets/daily_trait_variation.png)

Wählen Sie in der [!UICONTROL Date] Liste einen oder mehrere Datumsangaben für den Bericht aus. Am unteren Rand der Liste wird ein farbcodiertes Balkendiagramm angezeigt, das einen visuellen Vertreter für den Bereich der Standardabweichung für alle ausgewählten Daten bereitstellt. Die schwarze vertikale Linie zeigt das arithmetische Mittel an.

Die mittlere Spalte enthält eine Liste mit Eigenschaften, die durch [!UICONTROL Trait ID] und [!UICONTROL Trait Name]identifiziert werden. Klicken Sie auf eine beliebige Eigenschaft, um ein Popup-Dialogfeld aufzurufen, mit dem Sie aus den folgenden Optionen auswählen können:

* **Nur beibehalten:** Entfernt alle anderen Eigenschaften aus dem Bericht und zeigt nur Daten für diese Eigenschaft an.
* **Ausschließen:** Entfernt diese Eigenschaft aus dem Bericht und zeigt Daten zu allen anderen Eigenschaften an. Sie können mehrere Eigenschaften ausschließen.
* **Daten anzeigen:** Ermöglicht die Anzeige von Daten für diese Zeile. Sie können auch alle Zeilen als Textdatei herunterladen.

In der [!UICONTROL Standard Deviation] Spalte werden farbcodierte Balkendiagramme angezeigt, die die Standardabweichung für jede Eigenschaft über das ausgewählte Intervall anzeigen. Rote Balken weisen auf Eigenschaften mit einer negativen Standardabweichung hin (Datenpunkte sind tendenziell unter dem arithmetischen Mittel). Grüne Balken weisen auf Eigenschaften mit einer positiven Standardabweichung hin (Datenpunkte reichen tendenziell über dem Mittelwert). Bewegen Sie den Mauszeiger über eine Leiste, um ein Popup-Dialogfeld mit weiteren Informationen und Optionen anzuzeigen, um diese Eigenschaft beizubehalten oder auszuklammern und weitere Informationen anzuzeigen.

Die Symbole werden unten im Bericht angezeigt, mit dem Sie Daten in verschiedenen Formaten exportieren können, alle Änderungen zurücksetzen können, die Sie am Bericht vorgenommen haben (z. B. Eigenschaften ausschließen), automatische Aktualisierungen aktivieren oder deaktivieren und die Daten des Berichts aktualisieren. Siehe [Berichtsymbole und Erläuterung der Tools](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Nutzungsszenarios {#use-cases}

**Beispiel 1**: Dieser Bericht kann in Situationen mit einer hohen Saisonalität sehr nützlich sein. Nehmen wir an, Ihr Online-Shop testet Saisonpromotions verschiedener Typen und Preise. Sie haben die folgenden Eigenschaften definiert in [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Angenommen, Sie führen den [!UICONTROL Daily Trait Variation] Bericht am 20. Dezember aus und bemerken eine solide positive Abweichung bei den oben genannten Eigenschaften in den letzten 30 Tagen. Dies kann empfehlen, dass Ihre Besucher nach den Produkten suchen, die in Ihrer Saisonpromotion erwähnt werden. Um diesen Trend nutzen zu können, können Sie mehr Bemühungen in das Targeting kreativer Elemente für diese spezifische Produktkategorie für Besucher investieren, die daran interessiert sind.

**Beispiel 2**: Dieser Bericht kann Ihnen helfen, Targeting-Anomalien in Bezug auf Tagging-Probleme oder fehlerhafte Fehlermeldungen zu identifizieren. Angenommen, Sie haben die folgende Eigenschaft basierend auf den Kategorien Ihres Online-Shops definiert:

* `productPage == "smartphones"`

Aufgrund einer Neukonfiguration Ihres Speichers teilen Sie die Smartphone-Seite auf Grundlage von Markennamen in mehrere Seiten auf. Sie vergessen jedoch, die in [!DNL Audience Manager]festgelegten Eigenschaften zu aktualisieren.

Ein Monat später führen Sie den [!UICONTROL Daily Trait Variation] Bericht aus und beachten eine große negative Abweichung der `productPage == "smartphones"` Eigenschaft, obwohl die Besucherzahl gemäß Ihrer Site-Analyse angestiegen ist. Anhand dieser Informationen können Sie erkennen, dass Sie die Eigenschaften [!DNL Audience Manager] für Ihre neuen Produktseiten nicht aktualisiert haben. Sie wissen daher, dass Sie die folgenden Eigenschaften erstellen müssen:

* Productpage = = &quot;samsung&quot;
* Productpage = = &quot;apple&quot;
* Productpage = = &quot;huawei&quot;

Anschließend sehen Sie die Zielgruppe, die für die neu erstellten Eigenschaften qualifiziert ist.
