---
description: Suche nach einem oder mehreren Signalen basierend auf ihren jeweiligen Schlüssel-Wert-Paaren.
seo-description: Suche nach einem oder mehreren Signalen basierend auf ihren jeweiligen Schlüssel-Wert-Paaren.
seo-title: Suchsignale nach Schlüssel-Wert-Paaren
title: Suchsignale nach Schlüssel-Wert-Paaren
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: 'Data Explorer '
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 5%

---

# Suchsignale nach Schlüssel-Wert-Paaren {#search-signals-by-key-value-pairs}

Suche nach einem oder mehreren Signalen basierend auf ihren jeweiligen Schlüssel-Wert-Paaren.
Um nach mehr als einem Signal zu suchen, klicken Sie auf die Schaltfläche ![Hinzufügen](assets/icon_add.png) . Geben Sie die Schlüssel-Wert-Paare ein, nach denen Sie suchen möchten, und verwenden Sie dann die folgenden Filter, um Ihre Ergebnisse einzugrenzen.

* **Signalstatus**: Suche nach Signalen, die in Eigenschaften, nicht verwendeten Signalen oder beidem enthalten sind.
* **Anzeigen von Datensätzen für**: Wählen Sie das Zeitintervall aus, in dem nach empfangenen Signalen gesucht werden soll.
* **Mindestanzahl**: zeigt nur Signale mit der angegebenen minimalen Gesamtanzahl im ausgewählten Intervall an.

>[!IMPORTANT]
>
>Für ein optimiertes Benutzererlebnis basieren die Suchergebnisse für Schlüssel-Wert-Paare auf dem Daten-Sampling. Unter [Daten-Sampling und Fehlerraten](/help/using/reporting/report-sampling.md) finden Sie Details dazu, wie [!DNL Audience Manager] Daten-Sampling verwendet und warum beim Vergleich von Schlüssel-Wert-Suchen mit allgemeinen Suchen leichte Ergebnisvarianten auftreten können.

Bei der Suche nach Signalen mit mehreren Schlüssel-Wert-Paaren verknüpft [!DNL Audience Manager] die Paare mithilfe des logischen Operators **AND**. Angenommen, Sie führen eine Suche mit den folgenden Schlüssel-Wert-Paaren durch:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Diese Suche gibt nur Ergebnisse zurück, die für alle drei Filter im selben Aufruf qualifiziert sind: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`

![](assets/signals-search.png)

## Von der Signalsuche ausgeschlossene Signale {#excluded-signals}

Schlüsselvariablen, die von Audience Manager verwendet werden und mit dem Präfix `d_` und `h_` versehen sind, werden nicht von [!UICONTROL Signals Search] angezeigt. Weitere Informationen finden Sie unter [Voraussetzungen für das Präfix für Schlüsselvariablen](../../traits/trait-variable-prefixes.md) .

## Groß-/Kleinschreibung und automatischer Abschluss der Suche {#case-insensitivity}

Bei den Suchfeldern Schlüssel und Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. Das Schlüsselsuchfeld enthält automatisch ausgefüllte Vorschläge.

![](assets/signal-search-suggestions.png)

Nehmen wir an, [!DNL Audience Manager] hat die folgenden Signale empfangen:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Wenn Sie `product` in das Schlüsselsuchfeld eingeben, erhalten Sie automatisch ausgefüllte Vorschläge für `productCategory`, `newProduct`, `PRODUCT` und `product`.

Wenn Sie nach `product == phone` suchen, gibt [!UICONTROL Data Explorer] Ergebnisse für `PRODUCT == phone` und `product == PHONE` zurück.
Bei rückgängig gemachten Merkmalrealisierungen wird nicht zwischen Groß- und Kleinschreibung unterschieden. Eine Eigenschaft, die das Signal mit dem Schlüssel-Wert-Paar `PRODUCT == SMARTPHONE` enthält, qualifiziert auch das Signal mit dem Schlüssel-Wert-Paar `product == smartphone`.
