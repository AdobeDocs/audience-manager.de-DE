---
description: Suchen Sie nach einem oder mehreren Signalen, basierend auf den jeweiligen Schlüsselwertpaaren.
seo-description: Suchen Sie nach einem oder mehreren Signalen, basierend auf den jeweiligen Schlüsselwertpaaren.
seo-title: Suchsignale nach Schlüssel-Wert-Paaren
title: Suchsignale nach Schlüssel-Wert-Paaren
uuid: 2 a 38 d 0 d 4-4 a 2 e -4 ca 5-b 9 ec-af 9 d 4963 d 876
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Suchsignale nach Schlüssel-Wert-Paaren {#search-signals-by-key-value-pairs}

Suchen Sie nach einem oder mehreren Signalen, basierend auf den jeweiligen Schlüsselwertpaaren.
Um nach mehreren Signal zu suchen, klicken Sie auf ![die Schaltfläche &quot;Hinzufügen](assets/icon_add.png) &quot; . Geben Sie die Schlüssel/Wert-Paare ein, nach denen Sie suchen möchten, und verwenden Sie dann die folgenden Filter, um Ihre Ergebnisse einzugrenzen.

* **Signalstatus**: Suchen nach Signalen, die in Eigenschaften, nicht verwendeten Signalen oder beidem enthalten sind.
* **Datensätze anzeigen für**: Wählen Sie das Zeitintervall aus, in dem nach empfangenen Signalen gesucht werden soll.
* **Minimale Anzahl**: zeigt nur Signale mit der angegebenen Mindestanzahl im ausgewählten Intervall an.

>[!IMPORTANT]
>
>Für ein optimiertes Benutzererlebnis basieren die Schlüsselwertpaare auf der Datenstichprobe. Unter [Datenstichproben und Fehlerquoten](/help/using/reporting/report-sampling.md) finden Sie Einzelheiten dazu, wie [!DNL Audience Manager] die Datenstichproben verwendet werden und weshalb geringfügige Ergebnisvariationen beim Vergleich von Schlüsselwertsuche mit allgemeinen Suchen auftreten können.

Wenn Sie nach Signalen suchen, die mehrere Schlüssel/Wert-Paare verwenden, [!DNL Audience Manager] verknüpfen Sie die Paare mit dem logischen **UND** -Operator. Nehmen wir beispielsweise an, Sie führen eine Suche mit den folgenden Schlüsselwertpaaren durch:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Diese Suche gibt nur Ergebnisse zurück, die sich für alle drei Filter in demselben Aufruf qualifizieren: `c_creative == "12345"``AND``c_product == "smartphone"``AND``c_location == "europe"`.

![](assets/signals-search.png)

## Unterscheidung zwischen Groß- und Kleinschreibung und automatische Suche {#case-insensitivity}

Bei den Suchfeldern für Schlüssel und Wert wird zwischen Groß- und Kleinschreibung unterschieden. Das Schlüsselsuchfeld enthält automatisch vervollständigte Vorschläge.

![](assets/signal-search-suggestions.png)

Nehmen wir an, [!DNL Audience Manager] die folgenden Signale wurden erhalten:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Wenn Sie in `product` das Schlüsselsuchfeld eingeben, erhalten Sie automatisch vervollständigte Vorschläge für `productCategory``newProduct`, `PRODUCT`und `product`.

Gleichermaßen `product == phone`[!UICONTROL Data Explorer] gibt bei der Suche die Ergebnisse für beide `PRODUCT == phone` und `product == PHONE`zurück.
Bei zurückgestellten Eigenschaften für Eigenschaften wird zwischen Groß- und Kleinschreibung unterschieden. Eine Eigenschaft, die das Signal mit dem Schlüssel-Wert-Paar `PRODUCT == SMARTPHONE` enthält, qualifiziert das Signal auch mit dem Schlüssel-Wert-Paar `product == smartphone`.