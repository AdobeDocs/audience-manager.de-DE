---
description: Beschreibt die gemeinsamen Schlüssel-Wert-Paare auf Plattformebene, die Sie zur Zielgruppe von Benutzern mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto verwenden können.
seo-description: Beschreibt die gemeinsamen Schlüssel-Wert-Paare auf Plattformebene, die Sie zur Zielgruppe von Benutzern mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto verwenden können.
seo-title: Geotargeting mit Schlüsseln auf Platform-Ebene
solution: Audience Manager
title: Geotargeting mit Schlüsseln auf Platform-Ebene
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 1%

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

Beschreibt die gemeinsamen Schlüssel-Wert-Paare auf Plattformebene, die Sie zur Zielgruppe von Benutzern mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto verwenden können.

<!-- c_tb_platform_vars.xml -->

## Zweck der Variablen auf Platform {#platform-variables}

Mithilfe von Variablen auf Platform können Sie Daten, die von einer bestimmten Site übergeben werden, für das Targeting in allen Eigenschaften Ihres [!DNL Audience Manager] Kontos nutzen. Diese Variablen werden durch [Schlüssel-Wert-Paare](../../reference/key-value-pairs-explained.md) gebildet, wobei der Schlüssel dem folgenden vorangestellt wird `d_` .

## Hinzufügen von Werten zu Platform Level Keys {#adding-values}

Bei einigen Schlüsseln auf Plattformebene können Sie den Wert selbst angeben. Bei anderen werden die Schlüssel mit den entsprechenden [!DNL IP] Adressen verknüpft, die bei einem Ereignis-Aufruf übergeben werden. In beiden Fällen müssen Sie den Wert trotzdem angeben, wenn Eigenschaften in erstellt werden [!UICONTROL Trait Builder].

## Benutzerdefinierte Schlüssel auf Platform-Ebene {#user-defined-keys}

Sie geben den Wert beim Erstellen von Eigenschaften mit diesen Schlüssel/Wert-Paaren an:

| Schlüssel | Für Targeting |
|---|---|
| `d_zx` | Postleitzahl (z. B. `d_zx=10022`). |

## Schlüssel auf Platform, die nach IP-Adresse definiert sind {#keys-ip-address}

Wir arbeiten mit [Digital Envoy](https://www.digitalenvoy.com/) zusammen, um die demografischen und geografischen Daten für die unten stehenden Schlüssel zu erhalten und zu aktualisieren. Die Werte für diese Schlüssel werden durch Zuordnung der [!DNL IP] Adressen zu den entsprechenden geografischen und demografischen Daten bestimmt. Sie müssen jedoch den Parameter value trotzdem eingeben, wenn Sie das Schlüssel-Wert-Paar in [!UICONTROL Trait Builder]erstellen.

| Schlüssel | Für Targeting |
|--- |--- |
| d_area_code | [Nordamerika-Gebietscodes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Beispiel: <ul><li>**Eigenschaft**:  d_area_code=801</li><li>**Eigenschaftsname**: Utah</li></ul> |
| d_city | Städte und Städte. Laden Sie die [Liste](assets/d_city.txt)&quot;Städte&quot;herunter.  Beispiel: <ul><li>Eigenschaft:  d_city=bonn</li><li>Eigenschaftsname: Bonn</li></ul> **Tipp**: Sie können `d_city` zusammen mit `d_country` sicherstellen, dass Sie nicht zwei Städte mit demselben Namen in verschiedenen Ländern ansprechen. Sie können Ihr Targeting mit `d_postal_code`noch spezifischer gestalten. |
| d_country | Die Werte entsprechen den ISO-Ländercodes. Eine durchsuchbare Liste von Codes finden Sie in der Platform [ISO Online Browsing](https://www.iso.org/obp/ui/#home). <br>  Das Targeting für das Vereinigte Königreich ist der einzige Sonderfall, der ISO 3166 nicht befolgt. Sie sollten für das Targeting in Großbritannien &quot;UK&quot;anstelle von &quot;GB&quot;verwenden.  Zur Zielgruppe der Niederländischen Antillen wird der Code &quot;AN&quot;seit 2010 nicht mehr unterstützt. Das Gebiet wurde in fünf separate Gebietseinheiten aufgelöst. Das bedeutet, dass Sie beim Targeting in den Niederländischen Antillen nicht &quot;AN&quot;verwenden sollten, sondern eine Kombination der Ländercodes für &quot;CW&quot;, &quot;SX&quot;und &quot;BQ&quot;.  Beispiel:  <br>  Eigenschaft:  d_country=CZ <br>Eigenschaftsname: Tschechische Republik <br>Eigenschaft:  d_country=UK <br>Eigenschaftsname: Vereinigtes <br>Merkmal:  d_country=CW OR d_country=SX OR d_country=BQ <br>Eigenschaftsname: Niederländische Antillen |
| d_dma_code | DMA-Codes für städtische Gebiete. Laden Sie die [DMA-Regions-Liste](assets/DMAregions.csv) herunter (.csv-Format).  Beispiel: <ul><li>Eigenschaft:  d_dma_code=807</li><li>Eigenschaftsname: San Francisco</li></ul> |
| d_lat | Breitengrad (z. B. d_lat=40.75). Laden Sie die Liste [der Breitengrade herunter](assets/d_lat.txt). |
| d_long | Längengrad (z. B. d_long=73.98). Laden Sie die [Liste](assets/d_long.txt)für Längengrade herunter. |
| d_postal_code | Postleitzahlen (ohne den erweiterten +4-Code). Laden Sie die Liste [der](assets/d_postal_code.txt)Postleitzahlen herunter.  Beispiel: <ul><li>Eigenschaft:  d_postal_code=84004 </li><li>Eigenschaftsname: Alpine</li></ul> |
| d_state | Abkürzung mit 2 Zeichen für einen US-Staat. Laden Sie die [Statuscodes Liste](assets/d_state.txt)herunter.  Beispiel: <ul><li>Eigenschaft:  d_state=NY </li><li>Eigenschaftsname: New York</li></ul>d_state enthält wiederholte Werte für verschiedene Status in verschiedenen Ländern. Beispiel: d_state == &quot;on&quot; stimmt mit mehreren Status überein: Ontario (in Kanada), Ondo (in Nigeria), Oshana (in Namibia). Wir empfehlen, dieses Signal mit anderen zu verbinden, wie z.B. d_country für spezifischeres Geotargeting. |
| d_region | Regionale alphanumerische IDs. Laden Sie die [Regions-Liste](assets/Country_RegionCodes_City.csv)herunter.  Anschließend können Sie diese Liste verwenden, um Regions-IDs mit Regionennamen abzugleichen. |
| d_isp | ISP/Einrichtung. Laden Sie die [ISP-Liste](assets/d_isp.txt)herunter. |

Die Liste [aller ortsbasierten Signale](assets/all.txt) umfasst alle oben genannten Signale in der folgenden Reihenfolge: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Voraussetzungen für das Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)

