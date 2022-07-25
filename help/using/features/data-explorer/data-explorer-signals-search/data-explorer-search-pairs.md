---
description: Suche nach einem oder mehreren Signalen basierend auf ihren jeweiligen Schlüssel-Wert-Paaren.
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: Suchsignale nach Schlüssel-Wert-Paaren
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 1%

---

# Suchsignale nach Schlüssel-Wert-Paaren {#search-signals-by-key-value-pairs}

Suche nach einem oder mehreren Signalen basierend auf ihren jeweiligen Schlüssel-Wert-Paaren.
Wenn Sie nach mehr als einem Signal suchen möchten, klicken Sie auf das ![Hinzufügen](assets/icon_add.png) Schaltfläche. Geben Sie die Schlüssel-Wert-Paare ein, nach denen Sie suchen möchten, und verwenden Sie dann die folgenden Filter, um Ihre Ergebnisse einzugrenzen.

* **Signalstatus**: Suche nach Signalen, die in Eigenschaften, nicht verwendeten Signalen oder beidem enthalten sind.
* **Anzeigen von Datensätzen für**: Wählen Sie das Zeitintervall aus, in dem nach empfangenen Signalen gesucht werden soll.
* **Mindestanzahl von Anschlüssen**: zeigt nur Signale mit der angegebenen minimalen Gesamtanzahl im ausgewählten Intervall an.

>[!IMPORTANT]
>
>Für ein optimiertes Benutzererlebnis basieren die Suchergebnisse für Schlüssel-Wert-Paare auf dem Daten-Sampling. Siehe [Daten-Sampling und Fehlerraten](/help/using/reporting/report-sampling.md) für Einzelheiten zur [!DNL Audience Manager] verwendet das Daten-Sampling und warum beim Vergleich der Schlüsselwertsuche mit allgemeinen Suchvorgängen leichte Ergebnisabweichungen auftreten können.

Bei der Suche nach Signalen mit mehreren Schlüssel-Wert-Paaren [!DNL Audience Manager] verknüpft die Paare mithilfe der logischen **UND** Operator. Angenommen, Sie führen eine Suche mit den folgenden Schlüssel-Wert-Paaren durch:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Diese Suche gibt nur Ergebnisse zurück, die für alle drei Filter im selben Aufruf qualifiziert sind: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Signale, die von der Signalsuche ausgeschlossen sind {#excluded-signals}

Schlüsselvariablen, die von Audience Manager verwendet werden und dem `d_` und `h_` -Präfixe werden nicht durch [!UICONTROL Signals Search]. Siehe [Voraussetzungen für das Präfix für Schlüsselvariablen](../../traits/trait-variable-prefixes.md) für Details.

## Groß-/Kleinschreibung und automatische Vervollständigung von Suchvorgängen {#case-insensitivity}

Bei den Suchfeldern Schlüssel und Wert wird zwischen Groß- und Kleinschreibung unterschieden. Das Schlüsselsuchfeld enthält automatisch ausgefüllte Vorschläge.

![](assets/signal-search-suggestions.png)

Sagen wir mal: [!DNL Audience Manager] die folgenden Signale empfangen haben:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Wenn Sie `product` im Schlüsselsuchfeld erhalten Sie automatisch ausgefüllte Vorschläge für `productCategory` und `product`.

Wenn Sie nach `product == PHONE`, [!UICONTROL Data Explorer] liefert Ergebnisse nur für `product == PHONE`.

Bei zurückgegebenen Eigenschaftsrealisierungen wird ebenfalls zwischen Groß- und Kleinschreibung unterschieden. Eine Eigenschaft, die das Signal mit dem Schlüssel-Wert-Paar enthält `PRODUCT == SMARTPHONE` qualifiziert das Signal nicht mit dem Schlüssel-Wert-Paar `product == smartphone`.
