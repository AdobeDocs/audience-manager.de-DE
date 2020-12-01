---
description: Suchen Sie nach einem oder mehreren Signalen, basierend auf ihren jeweiligen Schlüssel-Wert-Paaren.
seo-description: Suchen Sie nach einem oder mehreren Signalen, basierend auf ihren jeweiligen Schlüssel-Wert-Paaren.
seo-title: Suchsignale nach Schlüssel-Wert-Paaren
title: Suchsignale nach Schlüssel-Wert-Paaren
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 4%

---


# Suchsignale nach Schlüssel-Wert-Paaren {#search-signals-by-key-value-pairs}

Suchen Sie nach einem oder mehreren Signalen, basierend auf ihren jeweiligen Schlüssel-Wert-Paaren.
Um nach mehr als einem Signal zu suchen, klicken Sie auf die Schaltfläche ![Hinzufügen](assets/icon_add.png). Geben Sie die Schlüssel-Wert-Paare ein, nach denen Sie suchen möchten, und verwenden Sie dann die folgenden Filter, um die Ergebnisse einzugrenzen.

* **Signalstatus**: Suche nach Signalen in Eigenschaften, nicht verwendeten Signalen oder beidem.
* **Ansichten für**: Wählen Sie das Zeitintervall, in dem nach empfangenen Signalen gesucht werden soll.
* **Mindestanzahl**: Zeigt nur Signale mit der angegebenen minimalen Gesamtanzahl im ausgewählten Intervall an.

>[!IMPORTANT]
>
>Für eine optimierte Benutzererfahrung basieren Suchergebnisse für Schlüssel-Wert-Paare auf einer Datenerfassung. Unter [Datenstichprobenerhebung und Fehlerquoten](/help/using/reporting/report-sampling.md) finden Sie Einzelheiten dazu, wie [!DNL Audience Manager] die Datenstichprobenerhebung verwendet und warum beim Vergleich der Schlüsselwertsuche mit allgemeinen Suchvorgängen leichte Ergebnisabweichungen auftreten können.

Bei der Suche nach Signalen mit mehreren Schlüssel-Wert-Paaren verknüpft [!DNL Audience Manager] die Paare mit dem logischen Operator **AND**. Nehmen wir beispielsweise an, Sie führen eine Suche mit den folgenden Schlüssel-Wert-Paaren durch:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Diese Suche gibt nur Ergebnisse zurück, die für alle drei Filter desselben Aufrufs qualifiziert sind: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`

![](assets/signals-search.png)

## Signale, die von der Signalsuche ausgeschlossen sind{#excluded-signals}

Schlüsselvariablen, die von Audience Manager verwendet und mit dem Präfix `d_` und `h_` versehen werden, werden nicht durch [!UICONTROL Signals Search] ersetzt. Weitere Informationen finden Sie unter [Voraussetzungen für das Präfix für Schlüsselvariablen](../../traits/trait-variable-prefixes.md).

## Groß-/Kleinschreibung und automatischer Abschluss der Suche {#case-insensitivity}

Bei den Suchfeldern für Schlüssel und Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. Das Feld für die Schlüsselsuche enthält automatisch ausgefüllte Vorschläge.

![](assets/signal-search-suggestions.png)

Nehmen wir an, dass [!DNL Audience Manager] die folgenden Signale erhalten hat:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Wenn Sie `product` in das Suchfeld eingeben, erhalten Sie automatisch ausgefüllte Vorschläge für `productCategory`, `newProduct`, `PRODUCT` und `product`.

Gleichermaßen gibt [!UICONTROL Data Explorer], wenn Sie nach `product == phone` suchen, Ergebnisse für `PRODUCT == phone` und `product == PHONE` zurück.
Bei rückgefüllten Eigenschaften wird nicht zwischen Groß- und Kleinschreibung unterschieden. Eine Eigenschaft, die das Signal mit dem Schlüssel-Wert-Paar `PRODUCT == SMARTPHONE` enthält, qualifiziert das Signal auch mit dem Schlüssel-Wert-Paar `product == smartphone`.