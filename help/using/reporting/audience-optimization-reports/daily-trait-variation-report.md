---
description: Dieser Bericht gibt eine Liste von Eigenschaften zurück, die in den 30 Tagen vor dem/den gewählten Datum/en mindestens 10.000 Mal realisiert wurden und die eine Standardabweichung von 1,7 in beide Richtungen im selben Zeitintervall aufweisen. Der Bericht hilft Ihnen bei der Beurteilung, wie viele Impressionen von Unique Users in einer Eigenschaft im Laufe der Zeit schwanken.
seo-description: Dieser Bericht gibt eine Liste von Eigenschaften zurück, die in den 30 Tagen vor dem/den gewählten Datum/en mindestens 10.000 Mal realisiert wurden und die eine Standardabweichung von 1,7 in beide Richtungen im selben Zeitintervall aufweisen. Der Bericht hilft Ihnen bei der Beurteilung, wie viele Impressionen von Unique Users in einer Eigenschaft im Laufe der Zeit schwanken.
seo-title: Täglicher Bericht zur Eigenschaftsvarianz
solution: Audience Manager
title: Täglicher Bericht zur Eigenschaftsvarianz
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---


# Täglicher Bericht zur Eigenschaftsvarianz {#daily-trait-variation-report}

Dieser Bericht gibt eine Liste von Eigenschaften zurück, die in den 30 Tagen vor dem/den gewählten Datum/en mindestens 10.000 Mal realisiert wurden und die eine Standardabweichung von 1,7 in beide Richtungen im selben Zeitintervall aufweisen. Der Bericht hilft Ihnen bei der Beurteilung, wie viele Impressionen von Unique Users in einer Eigenschaft im Laufe der Zeit schwanken.

>[!NOTE]
>
>Der Bericht &quot;Tägliche Trait-Variation&quot;in Audience Manager befolgt die RBAC-Prinzipien. Sie können Eigenschaften nur aus Datenquellen anzeigen, auf die Sie Zugriff haben, basierend auf der [RBAC-Benutzergruppe](/help/using/features/administration/administration-overview.md) , der Sie angehören.

Die Standardabweichung misst den Umfang der Abweichung oder Streuung vom Mittelwert (oder vom Mittelwert/erwarteten Wert). Eine niedrige Standardabweichung deutet darauf hin, dass die Datenpunkte tendenziell sehr nahe am Mittelwert liegen. Eine hohe Standardabweichung zeigt an, dass die Datenpunkte über einen großen Wertebereich verteilt sind.

![](assets/daily_trait_variation.png)

Verwenden Sie die [!UICONTROL Date] Liste, um ein oder mehrere Daten für Ihren Bericht auszuwählen. Am unteren Rand der Liste wird ein farbkodiertes Balkendiagramm angezeigt, das den Bereich der Standardabweichung für alle Eigenschaften über alle ausgewählten Daten hinweg visuell widerspiegelt. Die schwarze vertikale Linie zeigt den Mittelwert an.

Die mittlere Spalte enthält eine Liste von Eigenschaften, die durch [!UICONTROL Trait ID] und gekennzeichnet sind [!UICONTROL Trait Name]. Klicken Sie auf eine beliebige Eigenschaft, um ein Popup-Dialogfeld aufzurufen, in dem Sie eine der folgenden Optionen auswählen können:

* **Nur beibehalten:** Entfernt alle anderen Eigenschaften aus dem Bericht und zeigt nur Daten zu dieser Eigenschaft an.
* **Ausschließen:** Entfernt diese Eigenschaft aus dem Bericht und zeigt Daten zu allen anderen Eigenschaften an. Sie können mehrere Eigenschaften ausschließen.
* **Daten zur Ansicht:** Hiermit können Sie Daten zu dieser Zeile anzeigen. Sie können auch alle Zeilen als Textdatei herunterladen.

Die [!UICONTROL Standard Deviation] Spalte zeigt farbkodierte Balkendiagramme an, die die Standardabweichung für jede Eigenschaft im ausgewählten Intervall anzeigen. Rote Balken weisen auf Eigenschaften mit einer negativen Standardabweichung hin (Datenpunkte liegen tendenziell unter dem Mittelwert). Grüne Balken weisen auf Eigenschaften mit einer positiven Standardabweichung hin (Datenpunkte liegen meist über dem Mittelwert). Bewegen Sie den Mauszeiger über eine Leiste, um ein Popup-Dialogfeld mit weiteren Informationen und Optionen anzuzeigen, mit denen diese Eigenschaft beibehalten oder ausgeschlossen werden kann, und weitere Informationen zur Ansicht anzuzeigen.

Am Ende des Berichts werden Symbole angezeigt, mit denen Sie Daten in verschiedene Formate exportieren, Änderungen am Bericht wiederherstellen (z. B. Eigenschaften ausschließen), automatische Aktualisierungen aktivieren oder deaktivieren und die Berichtsdaten aktualisieren können. Siehe [Berichtssymbole und erläuterte](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)Tools.

## Nutzungsszenarios {#use-cases}

**Beispiel 1**: Dieser Bericht kann sehr nützlich sein, wenn Sie Eigenschaften mit hoher Saisonabhängigkeit haben. Nehmen wir zum Beispiel an, Ihr Online-Shop testet saisonale Promotions verschiedener Art und Preise. Folgende Eigenschaften sind definiert in [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Nehmen wir an, Sie führen den [!UICONTROL Daily Trait Variation] Bericht am 20. Dezember aus und Sie bemerken eine feste positive Abweichung von den oben genannten Eigenschaften in den letzten 30 Tagen. Dies kann darauf hindeuten, dass Ihre Besucher nach den in Ihrer saisonalen Promotion erwähnten Produkten suchen. Um diesen Trend zu nutzen, können Sie dann mehr Anstrengungen unternehmen, um kreative Elemente für diese spezifische Kategorie auf Besucher auszurichten, die daran interessiert sind.

**Beispiel 2**: Dieser Bericht kann Ihnen dabei helfen, Targeting-Anomalien im Zusammenhang mit Tagging-Problemen oder Eigenschaftenfehlkonfigurationen zu identifizieren. Stellen Sie sich vor, Sie haben die folgenden Eigenschaften basierend auf den Kategorien Ihres Online-Stores definiert:

* `productPage == "smartphones"`

Durch eine Neukonfiguration Ihres Geschäfts teilen Sie die Smartphone-Seite basierend auf den Markennamen in mehrere Seiten. Sie vergessen jedoch, die unter [!DNL Audience Manager]&quot;Eigenschaften&quot;definierten Eigenschaften zu aktualisieren.

Einen Monat später führen Sie den [!UICONTROL Daily Trait Variation] Bericht aus und bemerken eine große negative Abweichung von der `productPage == "smartphones"` Eigenschaft, obwohl Ihre Besucher-Anzahl gestiegen ist, wie Ihre Site-Analyse zeigt. Anhand dieser Informationen erkennen Sie, dass Sie die Eigenschaften für Ihre neuen Produktseiten nicht aktualisiert haben. Daher wissen Sie, dass Sie die folgenden Eigenschaften erstellen müssen: [!DNL Audience Manager]

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

Sobald Sie dies tun, sehen Sie, dass Ihre Audience für die neu erstellten Eigenschaften qualifiziert ist.
