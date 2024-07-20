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
ht-degree: 0%

---

# Suchsignale nach Schlüssel-Wert-Paaren {#search-signals-by-key-value-pairs}

Suche nach einem oder mehreren Signalen basierend auf ihren jeweiligen Schlüssel-Wert-Paaren.
Um nach mehr als einem Signal zu suchen, klicken Sie auf die Schaltfläche ![Hinzufügen](assets/icon_add.png) . Geben Sie die Schlüssel-Wert-Paare ein, nach denen Sie suchen möchten, und verwenden Sie dann die folgenden Filter, um Ihre Ergebnisse einzugrenzen.

* **Signalstatus**: Suche nach Signalen, die in Eigenschaften, nicht verwendeten Signalen oder beidem enthalten sind.
* **Datensätze für** anzeigen: Wählen Sie das Zeitintervall aus, in dem nach empfangenen Signalen gesucht werden soll.
* **Mindestanzahl**: Zeigt nur Signale mit der angegebenen Mindestgesamtanzahl im ausgewählten Intervall an.

>[!IMPORTANT]
>
>Für ein optimiertes Benutzererlebnis basieren die Suchergebnisse für Schlüssel-Wert-Paare auf dem Daten-Sampling. Unter [Daten-Sampling und Fehlerraten](/help/using/reporting/report-sampling.md) finden Sie Einzelheiten dazu, wie [!DNL Audience Manager] das Daten-Sampling verwendet und warum beim Vergleich der Schlüsselwertsuche mit allgemeinen Suchen leichte Ergebnisvarianten auftreten können.

Bei der Suche nach Signalen mit mehreren Schlüssel-Wert-Paaren verknüpft [!DNL Audience Manager] die Paare mithilfe des logischen **AND** -Operators. Angenommen, Sie führen eine Suche mit den folgenden Schlüssel-Wert-Paaren durch:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Diese Suche gibt nur Ergebnisse zurück, die für alle drei Filter beim gleichen Aufruf qualifiziert sind: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Signale, die von der Signalsuche ausgeschlossen sind {#excluded-signals}

Schlüsselvariablen, die vom Audience Manager verwendet werden und mit dem Präfix `d_` und `h_` versehen sind, werden nicht von [!UICONTROL Signals Search] angezeigt. Weitere Informationen finden Sie unter [Voraussetzungen für das Präfix für Schlüsselvariablen](../../traits/trait-variable-prefixes.md) .

## Groß-/Kleinschreibung und automatische Vervollständigung der Suche {#case-insensitivity}

Bei den Suchfeldern Schlüssel und Wert wird zwischen Groß- und Kleinschreibung unterschieden. Das Schlüsselsuchfeld enthält automatisch ausgefüllte Vorschläge.

![](assets/signal-search-suggestions.png)

Nehmen wir an, [!DNL Audience Manager] hat die folgenden Signale empfangen:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Wenn Sie `product` in das Schlüsselsuchfeld eingeben, erhalten Sie automatisch ausgefüllte Vorschläge für `productCategory` und `product`.

Entsprechend gibt [!UICONTROL Data Explorer] bei der Suche nach `product == PHONE` nur Ergebnisse für `product == PHONE` zurück.

Bei zurückgegebenen Eigenschaftsrealisierungen wird ebenfalls zwischen Groß- und Kleinschreibung unterschieden. Eine Eigenschaft, die das Signal mit dem Schlüssel-Wert-Paar `PRODUCT == SMARTPHONE` enthält, qualifiziert das Signal nicht mit dem Schlüssel-Wert-Paar `product == smartphone`.
