---
description: Beschreibt die gängigen Schlüssel-Wert-Paare auf Plattformebene, die Sie verwenden können, um Benutzer mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto anzusprechen.
seo-description: Beschreibt die gängigen Schlüssel-Wert-Paare auf Plattformebene, die Sie verwenden können, um Benutzer mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto anzusprechen.
seo-title: Geotargeting mit Schlüssel auf Plattformebene
solution: Audience Manager
title: Geotargeting mit Schlüssel auf Plattformebene
uuid: c 7 e 4 cbfe-e 564-404 e-a 565-bbe 5 fd 2 fb 519
translation-type: tm+mt
source-git-commit: c5c57423bcba8d4b3974a04c46dc7c7afc7484a0

---


# Geotargeting With Platform-level Keys {#geotargeting-with-platform-level-keys}

Beschreibt die gängigen Schlüssel-Wert-Paare auf Plattformebene, die Sie verwenden können, um Benutzer mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto anzusprechen.

<!-- c_tb_platform_vars.xml -->

## Purpose of Platform-level Variables {#platform-variables}

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Adding Values to Platform Level Keys {#adding-values}

Bei einigen Schlüsseln auf Plattformebene können Sie den Wert selbst angeben. With others, the keys are associated with corresponding [!DNL IP] addresses passed in on an event call. In either case, you still need to specify the value when building traits in [!UICONTROL Trait Builder].

## User Defined Platform-Level Keys {#user-defined-keys}

Sie geben den Wert an, wenn Eigenschaften mit diesen Schlüssel/Wert-Paaren erstellt werden:

| Schlüssel | Für Targeting |
|---|---|
| `d_zx` | ZIP code (e.g., `d_zx=10022`). |

## Platform Level Keys Defined by IP Address {#keys-ip-address}

We work with [Digital Envoy](https://www.digitalenvoy.com/) to obtain and update the demographic and geographic data for the keys below. The values for these keys are determined by matching [!DNL IP] addresses to corresponding geographic and demographic data. However, you'll still have to enter the value parameter when creating the key-value pair in [!UICONTROL Trait Builder].

| Schlüssel | Für Targeting |
|--- |--- |
| d_ area_ code | [Nordamerika-Gebietscodes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes). Beispiel: <ul><li>**Merkmal**: d_ area_ code = 801</li><li>**Eigenschaftsname**: Utah</li></ul> |
| d_ city | Städte und Städte. Download the [cities list](assets/d_city.txt).  Beispiel: <ul><li>Merkmal: d_ city = bonn</li><li>Eigenschaftsname: Bonn</li></ul> **Tipp**: `d_city` Sie können miteinander kombinieren, um `d_country` sicherzustellen, dass Sie nicht zwei Städte mit demselben Namen in verschiedenen Ländern ansprechen. You can be even more specific in your targeting by using `d_postal_code`. |
| d_ country | Werte entsprechen ISO-Ländercodes. For a searchable list of codes, see the [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>Das Targeting für Deutschland ist der einzige Sonderfall, der ISO 3166 nicht befolgt. Für Targeting in Großbritannien sollten Sie "UK" anstelle von" GB" verwenden. Zum Targeting auf niederländische Antillen wurde der Code "AN" seit 2010 nicht mehr unterstützt. Der Bereich wurde in fünf separate Gebietseinheiten aufgeteilt. Die implizite Bedeutung besteht darin, dass Sie für Targeting in den niederländischen Antillen keine "AN" , sondern eine Kombination der Ländercodes für" CW" , "SX" und" BQ" verwenden sollten. For example:  <br>  Trait:  d_country=CZ  <br>  Trait Name: Czech Republic <br>  Trait:  d_country=UK <br>  Trait Name: United Kingdom  <br>  Trait:  d_country=CW OR d_country=SX OR d_country=BQ  <br>  Trait Name: Netherlands Antilles |
| d_ dma_ code | Metropolitan Area DMA-Codes. Download the [DMA region list](assets/DMAregions.csv) (.csv format).  Beispiel: <ul><li>Merkmal: d_ dma_ code = 807</li><li>Eigenschaftsname: San Francisco</li></ul> |
| d_ lat | Breitengrad (d. d. d_ lat = 40,75). Download the [latitudes list](assets/d_lat.txt). |
| d_ long | Längengrad (d. d. d_ long = 73,98). Download the [longitudes list](assets/d_long.txt). |
| d_ postal_ code | Postleitzahlen (schließen Sie den erweiterten +4-Code aus). Download the  [postal codes list](assets/d_postal_code.txt).  Beispiel: <ul><li>Merkmal: d_ postal_ code = 84004 </li><li>Eigenschaftsname: Alpine</li></ul> |
| d_ state | 2-Zeichen-Abkürzung für einen US-Bundesstaat. Download the [states codes list](assets/d_state.txt).  Beispiel: <ul><li>Merkmal: d_ state = NY </li><li>Eigenschaftsname: New York</li></ul>d_ state enthält wiederholte Werte für verschiedene Status in verschiedenen Ländern. d_ state = = "on" entspricht beispielsweise mehreren Status: Ontario (in Kanada), Ondo (in Nigeria), Oshana (in Namibia). Wir empfehlen, dieses Signal mit anderen zu teilen, z. B. d_ country für spezifischere Geotargeting. |
| d_ region | Regionale alphanumerische IDs. Download the [region list](assets/Country_RegionCodes_City.csv).  Anschließend können Sie diese Liste verwenden, um Regions-IDs für Regionsnamen zu verwenden. |
| d_ isp | ISP/Organisation. Download the [ISP List](assets/d_isp.txt). |

The list of [all location-based signals](assets/all.csv) comprises all the signals above, in the following order: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORE_ LIKE_ THIS]
>
>* [Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)

