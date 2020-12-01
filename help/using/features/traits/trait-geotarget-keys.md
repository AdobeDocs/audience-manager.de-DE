---
description: Beschreibt die gemeinsamen Schlüssel-Wert-Paare auf Plattformebene, die Sie zur Zielgruppe von Benutzern mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto verwenden können.
seo-description: Beschreibt die gemeinsamen Schlüssel-Wert-Paare auf Plattformebene, die Sie zur Zielgruppe von Benutzern mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto verwenden können.
seo-title: Geotargeting mit Schlüsseln auf Plattformebene
solution: Audience Manager
title: Geotargeting mit Schlüsseln auf Plattformebene
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 4%

---


# Geotargeting mit Schlüsseln auf Plattformebene {#geotargeting-with-platform-level-keys}

Beschreibt die gemeinsamen Schlüssel-Wert-Paare auf Plattformebene, die Sie zur Zielgruppe von Benutzern mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto verwenden können.

<!-- c_tb_platform_vars.xml -->

## Zweck der Variablen auf Plattformebene {#platform-variables}

Mit Plattformvariablen können Sie Daten, die von einer bestimmten Site übergeben wurden, aufnehmen und für das Targeting für alle Eigenschaften in Ihrem [!DNL Audience Manager]-Konto verfügbar machen. Diese Variablen werden durch [Schlüssel-Wert-Paare](../../reference/key-value-pairs-explained.md) gebildet, wobei der Schlüssel durch `d_` vorangestellt wird, wie unten dargestellt.

## Hinzufügen von Werten zu Schlüsseln auf Plattformebene {#adding-values}

Bei einigen Schlüsseln auf Plattformebene können Sie den Wert selbst angeben. Bei anderen werden die Schlüssel mit den entsprechenden [!DNL IP]-Adressen verknüpft, die bei einem Ereignis-Aufruf übergeben werden. In beiden Fällen müssen Sie den Wert trotzdem angeben, wenn Sie Eigenschaften in [!UICONTROL Trait Builder] erstellen.

## Benutzerdefinierte Schlüssel auf Plattformebene {#user-defined-keys}

Sie geben den Wert beim Erstellen von Eigenschaften mit diesen Schlüssel/Wert-Paaren an:

| Schlüssel | Für Targeting |
|---|---|
| `d_zx` | Postleitzahl (z. B. `d_zx=10022`). |

## Nach IP-Adresse {#keys-ip-address} definierte Schlüssel auf Plattformebene

Wir arbeiten mit [Digital Envoy](https://www.digitalenvoy.com/), um die demografischen und geografischen Daten für die unten stehenden Schlüssel zu erhalten und zu aktualisieren. Die Werte für diese Schlüssel werden durch Übereinstimmung der [!DNL IP]-Adressen mit den entsprechenden geografischen und demografischen Daten bestimmt. Sie müssen jedoch den Parameter value trotzdem eingeben, wenn Sie das Schlüssel-Wert-Paar in [!UICONTROL Trait Builder] erstellen.

| Schlüssel | Für Targeting |
|--- |--- |
| d_area_code | [Nordamerika-Gebietscodes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Beispiel: <ul><li>**Eigenschaft**: d_area_code=801</li><li>**Eigenschaftsname**: Utah</li></ul> |
| d_city | Städte und Städte. Laden Sie die Liste [Städte](assets/d_city.txt) herunter.  Beispiel: <ul><li>Eigenschaft:  d_city=bonn</li><li>Eigenschaftsname: Bonn</li></ul> **Tipp**: Sie können  `d_city` zusammen mit  `d_country` sicherstellen, dass Sie nicht auf zwei Städte mit demselben Namen in verschiedenen Ländern abzielen. Mit `d_postal_code` können Sie Ihr Targeting noch spezifischer gestalten. |
| d_country | Die Werte entsprechen den ISO-Ländercodes. Eine durchsuchbare Liste von Codes finden Sie unter [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>  Das Targeting für das Vereinigte Königreich ist der einzige Sonderfall, der ISO 3166 nicht befolgt. Sie sollten für das Targeting in Großbritannien &quot;UK&quot;anstelle von &quot;GB&quot;verwenden.  Zur Zielgruppe der Niederländischen Antillen wird der Code &quot;AN&quot;seit 2010 nicht mehr unterstützt. Das Gebiet wurde in fünf separate Gebietseinheiten aufgelöst. Das bedeutet, dass Sie beim Targeting in den Niederländischen Antillen nicht &quot;AN&quot;verwenden sollten, sondern eine Kombination der Ländercodes für &quot;CW&quot;, &quot;SX&quot;und &quot;BQ&quot;.  Beispiel:  <br>  Eigenschaft:  d_country=CZ <br>  Eigenschaftsname: Tschechische Republik <br>  Eigenschaft:  d_country=UK <br>  Eigenschaftsname: Vereinigtes Königreich <br>  Eigenschaft:  d_country=CW OR d_country=SX OR d_country=BQ <br>  Eigenschaftsname: Niederländische Antillen |
| d_dma_code | DMA-Codes für städtische Gebiete. Laden Sie die Liste [DMA-Region](assets/DMAregions.csv) (.csv-Format) herunter.  Beispiel: <ul><li>Eigenschaft:  d_dma_code=807</li><li>Eigenschaftsname: San Francisco</li></ul> |
| d_lat | Breitengrad (z. B. d_lat=40.75). Laden Sie die Liste [latitudes](assets/d_lat.txt) herunter. |
| d_long | Längengrad (z. B. d_long=73.98). Laden Sie die Liste [Längengrade](assets/d_long.txt) herunter. |
| d_postal_code | Postleitzahlen (ohne den erweiterten +4-Code). Laden Sie die Liste [Postleitzahlen](assets/d_postal_code.txt) herunter.  Beispiel: <ul><li>Eigenschaft:  d_postal_code=84004 </li><li>Eigenschaftsname: Alpine</li></ul> |
| d_state | Abkürzung mit 2 Zeichen für einen US-Staat. Laden Sie die Liste [Statuscodes](assets/d_state.txt) herunter.  Beispiel: <ul><li>Eigenschaft:  d_state=NY </li><li>Eigenschaftsname: New York</li></ul>d_state enthält wiederholte Werte für verschiedene Status in verschiedenen Ländern. Beispiel: d_state == &quot;on&quot; stimmt mit mehreren Status überein: Ontario (in Kanada), Ondo (in Nigeria), Oshana (in Namibia). Wir empfehlen, dieses Signal mit anderen zu verbinden, wie z.B. d_country für spezifischeres Geotargeting. |
| d_region | Regionale alphanumerische IDs. Laden Sie die Liste [region](assets/Country_RegionCodes_City.csv) herunter.  Anschließend können Sie diese Liste verwenden, um Regions-IDs mit Regionennamen abzugleichen. |
| d_isp | ISP/Einrichtung. Laden Sie die [ISP-Liste](assets/d_isp.txt) herunter. |

Die Liste von [allen standortbasierten Signalen](assets/all.txt) umfasst alle oben genannten Signale in der folgenden Reihenfolge: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Anforderungen an Präfixe für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)

