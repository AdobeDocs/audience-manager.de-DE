---
description: Suchen Sie nach einem oder mehreren Signalen, basierend auf den jeweiligen Schlüsselwertpaaren.
seo-description: Suchen Sie nach einem oder mehreren Signalen, basierend auf den jeweiligen Schlüsselwertpaaren.
seo-title: Suchsignale nach Schlüssel-Wert-Paaren
title: Suchsignale nach Schlüssel-Wert-Paaren
uuid: 2 a 38 d 0 d 4-4 a 2 e -4 ca 5-b 9 ec-af 9 d 4963 d 876
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Search Signals by Key-Value Pairs {#search-signals-by-key-value-pairs}

Suchen Sie nach einem oder mehreren Signalen, basierend auf den jeweiligen Schlüsselwertpaaren.
To search for more than one signal, click the ![Add](assets/icon_add.png) button. Geben Sie die Schlüssel/Wert-Paare ein, nach denen Sie suchen möchten, und verwenden Sie dann die folgenden Filter, um Ihre Ergebnisse einzugrenzen.

* **Signalstatus**: Suchen nach Signalen, die in Eigenschaften, nicht verwendeten Signalen oder beidem enthalten sind.
* **Datensätze anzeigen für**: Wählen Sie das Zeitintervall aus, in dem nach empfangenen Signalen gesucht werden soll.
* **Minimale Anzahl**: zeigt nur Signale mit der angegebenen Mindestanzahl im ausgewählten Intervall an.

>[!IMPORTANT]
>
>Für ein optimiertes Benutzererlebnis basieren die Schlüsselwertpaare auf der Datenstichprobe. See [Data Sampling and Error Rates](/help/using/reporting/report-sampling.md) for details on how [!DNL Audience Manager] uses data sampling and why slight result variations may appear when comparing key-value search to general searches.

When searching for signals using multiple key-value pairs, [!DNL Audience Manager] links the pairs using the logical **AND** operator. Nehmen wir beispielsweise an, Sie führen eine Suche mit den folgenden Schlüsselwertpaaren durch:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

This search will return only results that qualify for all three filters on the same call: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Case Insensitivity and Search Auto-Completion {#case-insensitivity}

Bei den Suchfeldern für Schlüssel und Wert wird zwischen Groß- und Kleinschreibung unterschieden. Das Schlüsselsuchfeld enthält automatisch vervollständigte Vorschläge.

![](assets/signal-search-suggestions.png)

Let's say [!DNL Audience Manager] received the following signals:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

When you enter `product` in the key search field, you receive auto-completed suggestions for `productCategory`, `newProduct`, `PRODUCT`, and `product`.

Similarly, when you search for `product == phone`, [!UICONTROL Data Explorer] returns results for both `PRODUCT == phone` and `product == PHONE`.
Bei zurückgestellten Eigenschaften für Eigenschaften wird zwischen Groß- und Kleinschreibung unterschieden. A trait containing the signal with the key-value pair `PRODUCT == SMARTPHONE` also qualifies the signal with the key-value pair `product == smartphone`.