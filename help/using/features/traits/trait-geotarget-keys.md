---
description: Beschreibt die gebräuchlichen Schlüssel-Wert-Paare auf Plattformebene, mit denen Sie Benutzer mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto ansprechen können.
seo-description: Beschreibt die gebräuchlichen Schlüssel-Wert-Paare auf Plattformebene, mit denen Sie Benutzer mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto ansprechen können.
seo-title: Geotargeting mit Schlüsseln auf Plattformebene
solution: Audience Manager
title: Geotargeting mit Schlüsseln auf Plattformebene
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: 'Eigenschaften '
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 4%

---

# Geotargeting mit Schlüsseln auf Plattformebene {#geotargeting-with-platform-level-keys}

Beschreibt die gebräuchlichen Schlüssel-Wert-Paare auf Plattformebene, mit denen Sie Benutzer mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto ansprechen können.

<!-- c_tb_platform_vars.xml -->

## Zweck der Variablen auf Plattformebene {#platform-variables}

Variablen auf Plattformebene ermöglichen es Ihnen, von einer bestimmten Site übergebene Daten für das Targeting über alle Eigenschaften Ihres [!DNL Audience Manager]-Kontos hinweg zur Verfügung zu stellen. Diese Variablen werden durch [Schlüssel-Wert-Paare](../../reference/key-value-pairs-explained.md) gebildet, wobei dem Schlüssel `d_` das Präfix  vorangestellt wird, wie unten dargestellt.

## Hinzufügen von Werten zu Schlüsseln auf Plattformebene {#adding-values}

Bei einigen Schlüsseln auf Plattformebene können Sie den Wert selbst angeben. Bei anderen werden die Schlüssel mit den entsprechenden [!DNL IP]-Adressen verknüpft, die bei einem Ereignisaufruf übergeben werden. In beiden Fällen müssen Sie den Wert beim Erstellen von Eigenschaften in [!UICONTROL Trait Builder] weiterhin angeben.

## Benutzerdefinierte Schlüssel auf Plattformebene {#user-defined-keys}

Sie geben den Wert beim Erstellen von Eigenschaften mit diesen Schlüssel-Wert-Paaren an:

| Schlüssel | Für Targeting |
|---|---|
| `d_zx` | Postleitzahl (z. B. `d_zx=10022`). |

## Von IP-Adresse definierte Schlüssel auf Plattformebene {#keys-ip-address}

Wir arbeiten mit [Digital Envoy](https://www.digitalenvoy.com/) zusammen, um die demografischen und geografischen Daten für die folgenden Schlüssel zu erhalten und zu aktualisieren. Die Werte für diese Schlüssel werden durch Abgleich der [!DNL IP]-Adressen mit den entsprechenden geografischen und demografischen Daten bestimmt. Sie müssen jedoch weiterhin den Parameter value eingeben, wenn Sie das Schlüssel-Wert-Paar in [!UICONTROL Trait Builder] erstellen.

| Schlüssel | Für Targeting |
|--- |--- |
| d_area_code | [Nordamerika-Gebietscodes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Beispiel: <ul><li>**Eigenschaft**: d_area_code=801</li><li>**Eigenschaftsname**: Utah</li></ul> |
| d_city | Städte und Städte. Laden Sie die [Städteliste](assets/d_city.txt) herunter.  Beispiel: <ul><li>Eigenschaft:  d_city=bonn</li><li>Eigenschaftsname: Bonn</li></ul> **Tipp**: Sie können  `d_city` in Verbindung mit verwenden,  `d_country` um sicherzustellen, dass Sie nicht zwei Städte mit demselben Namen in verschiedenen Ländern ansprechen. Mit `d_postal_code` können Sie Ihre Zielgruppenbestimmung noch genauer gestalten. |
| d_country | Die Werte entsprechen den ISO-Ländercodes. Eine durchsuchbare Liste von Codes finden Sie unter [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>  Die Zielgruppenbestimmung für das Vereinigte Königreich ist der einzige Sonderfall, der nicht der Norm ISO 3166 entspricht. Sie sollten für das Targeting in Großbritannien &quot;UK&quot;anstelle von &quot;GB&quot;verwenden.  Für die Niederländischen Antillen ist der Code &quot;AN&quot;seit 2010 veraltet. Das Gebiet wurde in fünf separate Gebietseinheiten aufgelöst. Das bedeutet, dass Sie für das Targeting auf den Niederländischen Antillen nicht &quot;AN&quot;verwenden sollten, sondern eine Kombination der Ländercodes für &quot;CW&quot;, &quot;SX&quot;und &quot;BQ&quot;.  Beispiel:  <br>  Eigenschaft:  d_country=CZ <br>  Eigenschaftsname: Tschechische Republik <br>  Eigenschaft:  d_country=UK <br>  Eigenschaftsname: Vereinigtes Königreich <br>  Eigenschaft:  d_country=CW ODER d_country=SX ODER d_country=BQ <br>  Eigenschaftsname: Niederländische Antillen |
| d_dma_code | DMA-Codes für großstädtische Gebiete. Laden Sie die [DMA-Regionsliste](assets/DMAregions.csv) (.csv-Format) herunter.  Beispiel: <ul><li>Eigenschaft:  d_dma_code=807</li><li>Eigenschaftsname: San Francisco</li></ul> |
| d_lat | Breitengrad (z. B. d_lat=40.75). Laden Sie die Liste [latitudes](assets/d_lat.txt) herunter. |
| d_long | Längengrad (z. B. d_long=73.98). Laden Sie die Liste [longiturs](assets/d_long.txt) herunter. |
| d_postal_code | Postleitzahlen (ohne erweiterten +4-Code). Laden Sie die Liste [Postleitzahlen](assets/d_postal_code.txt) herunter.  Beispiel: <ul><li>Eigenschaft:  d_postal_code=84004 </li><li>Eigenschaftsname: Alpine</li></ul> |
| d_state | 2-stellige Abkürzung für einen US-Bundesstaat. Laden Sie die Liste [Statuscodes](assets/d_state.txt) herunter.  Beispiel: <ul><li>Eigenschaft:  d_state=NY </li><li>Eigenschaftsname: New York</li></ul>d_state enthält wiederholte Werte für verschiedene Status in verschiedenen Ländern. Beispielsweise entspricht d_state == &quot;on&quot; mehreren Status: Ontario (in Kanada), Ondo (in Nigeria), Oshana (in Namibia). Es wird empfohlen, dieses Signal mit anderen zu koppeln, z. B. d_country für spezifischeres Geotargeting. |
| d_region | Regionale alphanumerische IDs. Laden Sie die Liste [region](assets/Country_RegionCodes_City.csv) herunter.  Anschließend können Sie diese Liste verwenden, um Regions-IDs mit Regionennamen abzugleichen. |
| d_isp | ISP/Organisation. Laden Sie die [ISP-Liste](assets/d_isp.txt) herunter. |

Die Liste aller standortbasierten [Signale](assets/all.txt) umfasst alle oben genannten Signale in der folgenden Reihenfolge: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Anforderungen an Präfixe für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)

