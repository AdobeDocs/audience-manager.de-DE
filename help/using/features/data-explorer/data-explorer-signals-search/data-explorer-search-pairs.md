---
description: Suchen Sie nach einem oder mehreren Signalen, basierend auf ihren jeweiligen Schlüssel-Wert-Paaren.
seo-description: Suchen Sie nach einem oder mehreren Signalen, basierend auf ihren jeweiligen Schlüssel-Wert-Paaren.
seo-title: Suchsignale nach Schlüsselwertpaaren
title: Suchsignale nach Schlüsselwertpaaren
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
translation-type: tm+mt
source-git-commit: 2206b5e40f7024084953fed52bb02fcc46ea36f1

---


# Suchsignale nach Schlüsselwertpaaren {#search-signals-by-key-value-pairs}

Suchen Sie nach einem oder mehreren Signalen, basierend auf ihren jeweiligen Schlüssel-Wert-Paaren.
Um nach mehr als einem Signal zu suchen, klicken Sie auf die Schaltfläche ![Hinzufügen](assets/icon_add.png) . Geben Sie die Schlüssel-Wert-Paare ein, nach denen Sie suchen möchten, und verwenden Sie dann die folgenden Filter, um die Ergebnisse einzugrenzen.

* **Signalstatus**: Suche nach Signalen in Eigenschaften, nicht verwendeten Signalen oder beidem.
* **Datensätze anzeigen für**: Wählen Sie das Zeitintervall, in dem nach empfangenen Signalen gesucht werden soll.
* **Mindestanzahl**: nur Signale mit der angegebenen minimalen Gesamtanzahl im ausgewählten Intervall anzeigen.

>[!IMPORTANT]
>
>Für eine optimierte Benutzererfahrung basieren Suchergebnisse für Schlüssel-Wert-Paare auf einer Datenerfassung. Unter [Datenstichproben und Fehlerquoten](/help/using/reporting/report-sampling.md) [!DNL Audience Manager] finden Sie Einzelheiten dazu, wie die Datenerfassung verwendet wird und warum beim Vergleich der Schlüsselwertsuche mit allgemeinen Suchvorgängen geringfügige Ergebnisschwankungen auftreten können.

Bei der Suche nach Signalen mit mehreren Schlüssel/Wert-Paaren werden die Paare mit dem logischen [!DNL Audience Manager]UND **** -Operator verknüpft. Nehmen wir beispielsweise an, Sie führen eine Suche mit den folgenden Schlüssel-Wert-Paaren durch:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Diese Suche gibt nur Ergebnisse zurück, die für alle drei Filter bei demselben Aufruf qualifiziert sind: `c_creative == "12345"``AND``c_product == "smartphone"``AND``c_location == "europe"` .

![](assets/signals-search.png)

## Von der Signalsuche ausgeschlossene Signale {#excluded-signals}

Schlüsselvariablen, die von Audience Manager verwendet werden und denen die Präfixe `d_` und `h_` Präfixe vorangestellt werden, werden nicht durch [!UICONTROL Signals Search]übersehen. Weitere Informationen finden Sie unter [Voraussetzungen für das Präfix für Schlüsselvariablen](../../traits/trait-variable-prefixes.md) .

## Groß-/Kleinschreibung und automatischer Abschluss der Suche {#case-insensitivity}

Bei den Suchfeldern für Schlüssel und Wert wird nicht zwischen Groß- und Kleinschreibung unterschieden. Das Feld für die Schlüsselsuche enthält automatisch ausgefüllte Vorschläge.

![](assets/signal-search-suggestions.png)

Nehmen wir an, [!DNL Audience Manager] Sie haben folgende Signale erhalten:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Wenn Sie `product` in das Suchfeld eingeben, erhalten Sie automatisch ausgefüllte Vorschläge für `productCategory`, `newProduct`, `PRODUCT`und `product`.

Gleichermaßen gibt bei der Suche nach `product == phone`die [!UICONTROL Data Explorer] Ergebnisse sowohl für `PRODUCT == phone` als auch `product == PHONE`zurück.
Bei rückgefüllten Eigenschaften wird zwischen Groß- und Kleinschreibung unterschieden. Eine Eigenschaft, die das Signal mit dem Schlüssel-Wert-Paar enthält, qualifiziert `PRODUCT == SMARTPHONE` auch das Signal mit dem Schlüssel-Wert-Paar `product == smartphone`.