---
description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: Geotargeting mit Schlüsseln auf Plattformebene
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 366589d51601f438999bfdc6a10c306eb1186742
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 3%

---

# Geotargeting mit Schlüsseln auf Plattformebene {#geotargeting-with-platform-level-keys}

Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.

<!-- c_tb_platform_vars.xml -->

## Zweck der Variablen auf Plattformebene {#platform-variables}

Mit Variablen auf Plattformebene können Sie Daten aus einer bestimmten Site aufnehmen und für das Targeting über alle Eigenschaften in Ihrer [!DNL Audience Manager] -Konto. Diese Variablen werden durch [Schlüssel-Wert-Paare](../../reference/key-value-pairs-explained.md) mit dem vorangestellten -Schlüssel `d_` wie unten dargestellt.

## Hinzufügen von Werten zu Schlüsseln auf Plattformebene {#adding-values}

Bei einigen Schlüsseln auf Plattformebene können Sie den Wert selbst angeben. Bei anderen werden die Schlüssel mit den entsprechenden [!DNL IP] Adressen, die bei einem Ereignisaufruf übergeben werden. In beiden Fällen müssen Sie den Wert beim Erstellen von Eigenschaften in [!UICONTROL Trait Builder].

## Benutzerdefinierte Schlüssel auf Plattformebene {#user-defined-keys}

Wenn Sie bereits über einen Prozess zur Definition und Erfassung von Schlüssel-Wert-Paaren verfügen oder diesen gerade einrichten, verwenden Sie diese Option. If you want to use keys pre-defined by IP address, continue to the next section. In the case of user-defined keys, you specify the value when building traits with these key-value pairs:

| Schlüssel | For Targeting |
|---|---|
| `d_zx` | ZIP code (e.g., `d_zx=10022`). |

## Von IP-Adresse definierte Schlüssel auf Plattformebene {#keys-ip-address}

Wir arbeiten mit [Digital Envoy](https://www.digitalenvoy.com/) , um die demografischen und geografischen Daten für die folgenden Schlüssel zu erhalten und zu aktualisieren. Die Werte für diese Schlüssel werden durch Abgleich [!DNL IP] Adressen der entsprechenden geografischen und demografischen Daten. Sie müssen jedoch weiterhin den Parameter value eingeben, wenn Sie das Schlüssel-Wert-Paar in [!UICONTROL Trait Builder].

| Schlüssel | Für Targeting |
|--- |--- |
| d_area_code | [Nordamerika-Ländercodes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Beispiel: <ul><li>**Eigenschaft**: d_area_code=801</li><li>**Trait Name**: Utah</li></ul> |
| d_city | Cities and towns. Download the [cities list](assets/d_city.txt).  Beispiel: <ul><li>Eigenschaft: d_city=bonn</li><li>Eigenschaftsname: Bonn</li></ul> **Tipp**: Sie können `d_city` gekoppelt mit `d_country` Sie sollten sicherstellen, dass Sie nicht zwei Städte mit demselben Namen in verschiedenen Ländern ansprechen. You can be even more specific in your targeting by using `d_postal_code`. |
| d_country | Die Werte entsprechen den ISO-Ländercodes. For a searchable list of codes, see the [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>  Targeting for the United Kingdom is the only special case that does not obey ISO 3166. You should use &quot;UK&quot; instead of &quot;GB&quot; for targeting in the United Kingdom.  Für die Niederländischen Antillen ist der Code &quot;AN&quot;seit 2010 veraltet. Das Gebiet wurde in fünf separate Gebietseinheiten aufgelöst. Das bedeutet, dass Sie für das Targeting auf den Niederländischen Antillen nicht &quot;AN&quot;verwenden sollten, sondern eine Kombination der Ländercodes für &quot;CW&quot;, &quot;SX&quot;und &quot;BQ&quot;.  Beispiel:  <br>  Eigenschaft: d_country=CZ  <br>  Eigenschaftsname: Tschechische Republik <br>  Eigenschaft: d_country=UK <br>  Eigenschaftsname: Vereinigtes Königreich  <br>  Eigenschaft: d_country=CW ODER d_country=SX ODER d_country=BQ  <br>  Eigenschaftsname: Niederländische Antillen |
| d_dma_code | DMA-Codes für großstädtische Gebiete. Laden Sie die [DMA-Regionsliste](assets/DMAregions.csv) (CSV-Format).  Beispiel: <ul><li>Eigenschaft: d_dma_code=807</li><li>Eigenschaftsname: San Francisco</li></ul> |
| d_lat | Latitude (e.g.  d_lat=40.75). Laden Sie die [Liste der Breitengrade](assets/d_lat.txt). |
| d_long | Längengrad (z. B. d_long=73.98). Laden Sie die [longitudes list](assets/d_long.txt). |
| d_postal_code | ZIP codes (exclude the extended +4 code). Laden Sie die  [Postleitzahlenliste](assets/d_postal_code.txt).  Beispiel: <ul><li>Eigenschaft: d_postal_code=84004 </li><li>Trait Name: Alpine</li></ul> |
| d_state | 2-stellige Abkürzung für einen US-Bundesstaat. Laden Sie die [Statuscode-Liste](assets/d_state.txt).  Beispiel: <ul><li>Eigenschaft: d_state=NY </li><li>Trait Name: New York</li></ul>d_state enthält wiederholte Werte für verschiedene Status in verschiedenen Ländern. For example, d_state == &quot;on&quot; matches multiple states: Ontario (in Canada), Ondo (in Nigeria), Oshana (in Namibia). Es wird empfohlen, dieses Signal mit anderen zu koppeln, z. B. d_country für spezifischeres Geotargeting. |
| d_region | Regionale alphanumerische IDs. Laden Sie die [Regionsliste](assets/Country_RegionCodes_City.csv).  Anschließend können Sie diese Liste verwenden, um Regions-IDs mit Regionennamen abzugleichen. |
| d_isp | ISP/Organisation. Laden Sie die [ISP-Liste](assets/d_isp.txt). |

Die Liste der [alle standortbasierten Signale](assets/all.txt) umfasst alle oben genannten Signale in folgender Reihenfolge: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Anforderungen an Präfixe für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)

