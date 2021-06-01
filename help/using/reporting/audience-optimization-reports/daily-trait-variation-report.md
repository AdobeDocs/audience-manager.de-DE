---
description: Dieser Bericht gibt eine Liste von Eigenschaften zurück, die in den 30 Tagen vor dem/den ausgewählten Datum(en) mindestens 10.000 Mal realisiert wurden und eine Standardabweichung aufweisen, die im selben Zeitintervall in beide Richtungen größer oder gleich 1,7 ist. Der Bericht hilft Ihnen bei der Beurteilung, wie die Anzahl der Impressionen von Unique Users in einer Eigenschaft im Laufe der Zeit schwankt.
seo-description: Dieser Bericht gibt eine Liste von Eigenschaften zurück, die in den 30 Tagen vor dem/den ausgewählten Datum(en) mindestens 10.000 Mal realisiert wurden und eine Standardabweichung aufweisen, die im selben Zeitintervall in beide Richtungen größer oder gleich 1,7 ist. Der Bericht hilft Ihnen bei der Beurteilung, wie die Anzahl der Impressionen von Unique Users in einer Eigenschaft im Laufe der Zeit schwankt.
seo-title: Täglicher Bericht zur Eigenschaftsvarianz
solution: Audience Manager
title: Täglicher Bericht zur Eigenschaftsvarianz
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Berichte zur Zielgruppenoptimierung
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 2%

---

# Täglicher Bericht zur Eigenschaftsvarianz {#daily-trait-variation-report}

Dieser Bericht gibt eine Liste von Eigenschaften zurück, die in den 30 Tagen vor dem/den ausgewählten Datum(en) mindestens 10.000 Mal realisiert wurden und eine Standardabweichung aufweisen, die im selben Zeitintervall in beide Richtungen größer oder gleich 1,7 ist. Der Bericht hilft Ihnen bei der Beurteilung, wie die Anzahl der Impressionen von Unique Users in einer Eigenschaft im Laufe der Zeit schwankt.

>[!NOTE]
>
>Der Bericht &quot;Tägliche Eigenschaftsvarianz&quot;im Audience Manager entspricht den RBAC-Grundsätzen. Sie können Eigenschaften nur aus Datenquellen sehen, auf die Sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md), zu der Sie gehören.

Standardabweichung misst die Menge der Abweichung oder Streuung vom Mittelwert (oder Durchschnitt/erwarteter Wert). Eine niedrige Standardabweichung zeigt an, dass die Datenpunkte sehr nahe am Mittelwert liegen. Eine hohe Standardabweichung zeigt an, dass die Datenpunkte über einen großen Wertebereich verteilt sind.

![](assets/daily_trait_variation.png)

Verwenden Sie die Liste [!UICONTROL Date] , um ein oder mehrere Daten für Ihren Bericht auszuwählen. Unten in der Liste wird ein farbkodiertes Balkendiagramm angezeigt, das den Bereich der Standardabweichung für alle Eigenschaften über alle ausgewählten Daten hinweg visuell darstellt. Die schwarze vertikale Linie zeigt den Mittelwert an.

Die mittlere Spalte enthält eine Liste von Eigenschaften, identifiziert durch [!UICONTROL Trait ID] und [!UICONTROL Trait Name]. Klicken Sie auf eine beliebige Eigenschaft, um auf ein Popup-Dialogfeld zuzugreifen, in dem Sie aus den folgenden Optionen auswählen können:

* **Nur beibehalten:** Entfernt alle anderen Eigenschaften aus dem Bericht und zeigt nur Daten für diese Eigenschaft an.
* **Ausschließen:** Entfernt diese Eigenschaft aus dem Bericht und zeigt Daten für alle anderen Eigenschaften an. Sie können mehrere Eigenschaften ausschließen.
* **Daten anzeigen:** Ermöglicht die Anzeige der Daten für diese Zeile. Sie können auch alle Zeilen als Textdatei herunterladen.

Die Spalte [!UICONTROL Standard Deviation] zeigt farbkodierte Balkendiagramme an, die die Standardabweichung für jede Eigenschaft über das ausgewählte Intervall anzeigen. Rote Balken zeigen Eigenschaften mit einer negativen Standardabweichung an (Datenpunkte liegen tendenziell unter dem Mittelwert). Grüne Balken zeigen Eigenschaften mit einer positiven Standardabweichung an (Datenpunkte liegen tendenziell über dem Mittelwert). Bewegen Sie den Mauszeiger über eine Leiste, um ein Popup-Dialogfeld mit weiteren Informationen und Optionen zum Beibehalten oder Ausschließen dieser Eigenschaft und zum Anzeigen weiterer Informationen anzuzeigen.

Am unteren Rand des Berichts werden Symbole angezeigt, über die Sie Daten in verschiedenen Formaten exportieren, etwaige Änderungen am Bericht rückgängig machen (z. B. Eigenschaften ausschließen), automatische Aktualisierungen aktivieren oder deaktivieren und die Daten des Berichts aktualisieren können. Siehe [Berichtssymbole und -werkzeuge Erklärung](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Nutzungsszenarios {#use-cases}

**Beispiel 1**: Dieser Bericht kann in Situationen, in denen Sie Eigenschaften mit hoher Saisonabhängigkeit haben, sehr nützlich sein. Nehmen wir beispielsweise an, Ihr Online-Store testet saisonale Promotions verschiedener Typen und Preise. Folgende Eigenschaften sind in [!DNL Audience Manager] definiert:

* `productPage == "December Promotion"`
* `price > "500"`

Nehmen wir an, Sie führen den Bericht [!UICONTROL Daily Trait Variation] am 20. Dezember aus und Sie bemerken eine deutliche positive Abweichung von den oben genannten Eigenschaften in den letzten 30 Tagen. Dies kann darauf hindeuten, dass Ihre Besucher nach den Produkten suchen, die in Ihrer saisonalen Werbeaktion erwähnt werden. Um diesen Trend zu nutzen, können Sie dann mehr Anstrengungen unternehmen, um kreative Inhalte für diese Produktkategorie auf Besucher auszurichten, die daran interessiert sind.

**Beispiel 2**: Dieser Bericht kann Ihnen dabei helfen, Targeting-Anomalien im Zusammenhang mit Tagging-Problemen oder Fehlkonfigurationen von Eigenschaften zu identifizieren. Angenommen, Sie haben die folgende Eigenschaft basierend auf den Kategorien Ihres Online-Stores definiert:

* `productPage == "smartphones"`

Aufgrund einer Neukonfiguration Ihres Stores teilen Sie die Smartphone-Seite basierend auf den Markennamen in mehrere Seiten auf. Sie vergessen jedoch, die in [!DNL Audience Manager] definierten Eigenschaften zu aktualisieren.

Einen Monat später führen Sie den Bericht [!UICONTROL Daily Trait Variation] aus und bemerken eine große negative Abweichung von der Eigenschaft `productPage == "smartphones"`, obwohl Ihre Besucherzahl laut Site-Analyse gestiegen ist. Basierend auf diesen Informationen stellen Sie fest, dass Sie die Eigenschaften in [!DNL Audience Manager] für Ihre neuen Produktseiten nicht aktualisiert haben. Sie wissen also, dass Sie die folgenden Eigenschaften erstellen müssen:

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

Danach wird Ihre Zielgruppe für die neu erstellten Eigenschaften qualifiziert.
