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


# Geotargeting mit Schlüssel auf Plattformebene {#geotargeting-with-platform-level-keys}

Beschreibt die gängigen Schlüssel-Wert-Paare auf Plattformebene, die Sie verwenden können, um Benutzer mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto anzusprechen.

<!-- c_tb_platform_vars.xml -->

## Zweck der Variablen auf Plattformebene {#platform-variables}

Mit Variablen auf Plattformebene können Sie Daten aus einer bestimmten Site übernehmen und diese für Targeting über alle Eigenschaften in Ihrem [!DNL Audience Manager] Konto hinweg bereitstellen. Diese Variablen werden durch [Schlüssel-Wert-Paare mit](../../reference/key-value-pairs-explained.md) dem Schlüssel, wie `d_` unten dargestellt, gebildet.

## Werte zu Plattformebenen hinzufügen {#adding-values}

Bei einigen Schlüsseln auf Plattformebene können Sie den Wert selbst angeben. Bei anderen werden die Schlüssel mit den entsprechenden [!DNL IP] Adressen verknüpft, die bei einem Ereignisaufruf übergeben wurden. In either case, you still need to specify the value when building traits in [!UICONTROL Trait Builder].

## Benutzerdefinierte Plattformebene {#user-defined-keys}

Sie geben den Wert an, wenn Eigenschaften mit diesen Schlüssel/Wert-Paaren erstellt werden:

| Schlüssel | Für Targeting |
|---|---|
| `d_zx` | Postleitzahl (z. `d_zx=10022`B.). |

## Durch IP-Adresse definierte Plattformebene {#keys-ip-address}

Wir arbeiten mit [Digital Envoy](https://www.digitalenvoy.com/) zusammen, um demografische und geografische Daten für die unten stehenden Schlüssel abzurufen und zu aktualisieren. Die Werte für diese Schlüssel werden durch Übereinstimmende [!DNL IP] Adressen zu entsprechenden geografischen und demografischen Daten bestimmt. However, you&#39;ll still have to enter the value parameter when creating the key-value pair in [!UICONTROL Trait Builder].

| Schlüssel | Für Targeting |
|--- |--- |
| d_ area_ code | [Nordamerika-Gebietscodes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes). Beispiel: <ul><li>**Merkmal**: d_ area_ code = 801</li><li>**Eigenschaftsname**: Utah</li></ul> |
| d_ city | Städte und Städte. Laden Sie die [Ortsliste herunter](assets/d_city.txt). Beispiel: <ul><li>Merkmal: d_ city = bonn</li><li>Eigenschaftsname: Bonn</li></ul> **Tipp**: `d_city` Sie können miteinander kombinieren, um `d_country` sicherzustellen, dass Sie nicht zwei Städte mit demselben Namen in verschiedenen Ländern ansprechen. Sie können `d_postal_code`noch genauer in Ihrem Targeting sein. |
| d_ country | Werte entsprechen ISO-Ländercodes. Eine durchsuchbare Liste von Codes finden Sie auf der [ISO-Onlinebrowsing-Plattform](https://www.iso.org/obp/ui/#home). <br>Das Targeting für Deutschland ist der einzige Sonderfall, der ISO 3166 nicht befolgt. Für Targeting in Großbritannien sollten Sie &quot;UK&quot; anstelle von&quot; GB&quot; verwenden. Zum Targeting auf niederländische Antillen wurde der Code &quot;AN&quot; seit 2010 nicht mehr unterstützt. Der Bereich wurde in fünf separate Gebietseinheiten aufgeteilt. Die implizite Bedeutung besteht darin, dass Sie für Targeting in den niederländischen Antillen keine &quot;AN&quot; , sondern eine Kombination der Ländercodes für&quot; CW&quot; , &quot;SX&quot; und&quot; BQ&quot; verwenden sollten. Beispiel: <br>Merkmal: d_ country = CZ  <br>Trait Name: Tschechische <br>Republik: d_ country = UK  <br>Trait Name: Vereinigtes Königreich  <br>Trait: d_ country = CW OR d_ country = SX OR d_ country = BQ  <br>Trait Name: Niederländische Antillen |
| d_ dma_ code | Metropolitan Area DMA-Codes. Laden Sie die Liste [der DMA-Regionen](assets/DMAregions.csv) (. csv-Format) herunter. Beispiel: <ul><li>Merkmal: d_ dma_ code = 807</li><li>Eigenschaftsname: San Francisco</li></ul> |
| d_ lat | Breitengrad (d. d. d_ lat = 40,75). Laden Sie die Liste [der Breiten herunter](assets/d_lat.txt). |
| d_ long | Längengrad (d. d. d_ long = 73,98). Laden Sie [die Längenliste herunter](assets/d_long.txt). |
| d_ postal_ code | Postleitzahlen (schließen Sie den erweiterten +4-Code aus). Laden [Sie die Liste der Postleitzahlen herunter](assets/d_postal_code.txt). Beispiel: <ul><li>Merkmal: d_ postal_ code = 84004 </li><li>Eigenschaftsname: Alpine</li></ul> |
| d_ state | 2-Zeichen-Abkürzung für einen US-Bundesstaat. Laden Sie die [Liste der Statuscodes herunter](assets/d_state.txt). Beispiel: <ul><li>Merkmal: d_ state = NY </li><li>Eigenschaftsname: New York</li></ul>d_ state enthält wiederholte Werte für verschiedene Status in verschiedenen Ländern. d_ state = = &quot;on&quot; entspricht beispielsweise mehreren Status: Ontario (in Kanada), Ondo (in Nigeria), Oshana (in Namibia). Wir empfehlen, dieses Signal mit anderen zu teilen, z. B. d_ country für spezifischere Geotargeting. |
| d_ region | Regionale alphanumerische IDs. Laden Sie die [Regionsliste herunter](assets/Country_RegionCodes_City.csv). Anschließend können Sie diese Liste verwenden, um Regions-IDs für Regionsnamen zu verwenden. |
| d_ isp | ISP/Organisation. Laden Sie die [ISP-Liste herunter](assets/d_isp.txt). |

Die Liste [aller standortbasierten Signale](assets/all.csv) umfasst alle oben stehenden Signale in der folgenden Reihenfolge: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORE_ LIKE_ THIS]
>
>* [Präfix für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)

