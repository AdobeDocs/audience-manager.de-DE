---
description: Beschreibt die allgemeinen Schlüssel-Wert-Paare auf Plattformebene, mit denen Sie Benutzende mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto auswählen können.
seo-description: Describes the common platform-level key-value pairs you can use to target users with geographic variables across all properties in your Audience Manager account.
seo-title: Geotargeting With Platform-level Keys
solution: Audience Manager
title: Geotargeting mit Schlüsseln auf Plattformebene
uuid: c7e4cbfe-e564-404e-a565-bbe5fd2fb519
feature: Traits
exl-id: 449096f9-64fd-495f-ac1d-3181a4544279
source-git-commit: 2de7aba53e3c88d31270f2acb4fa29389f940312
workflow-type: tm+mt
source-wordcount: '621'
ht-degree: 2%

---

# Geotargeting mit Schlüsseln auf Plattformebene {#geotargeting-with-platform-level-keys}

Beschreibt die allgemeinen Schlüssel-Wert-Paare auf Plattformebene, mit denen Sie Benutzende mit geografischen Variablen für alle Eigenschaften in Ihrem Audience Manager-Konto auswählen können.

<!-- c_tb_platform_vars.xml -->

## Zweck von Variablen auf Plattformebene {#platform-variables}

Mit Variablen auf Plattformebene können Sie Daten, die von einer bestimmten Site übergeben werden, für die Zielgruppenbestimmung in allen Eigenschaften in Ihrem [!DNL Audience Manager]-Konto verfügbar machen. Diese Variablen werden durch [Schlüssel-Wert-Paare](../../reference/key-value-pairs-explained.md) gebildet, wobei der Schlüssel wie unten dargestellt durch `d_` vorangestellt wird.

## Hinzufügen von Werten zu Schlüsseln auf Plattformebene {#adding-values}

Für einige Schlüssel auf Plattformebene können Sie den Wert selbst angeben. Bei anderen werden die Schlüssel mit entsprechenden [!DNL IP] verknüpft, die bei einem Ereignisaufruf übergeben werden. In beiden Fällen müssen Sie beim Erstellen von Eigenschaften in [!UICONTROL Trait Builder] weiterhin den Wert angeben.

## Benutzerdefinierte Schlüssel auf Plattformebene {#user-defined-keys}

Wenn Sie bereits über einen Prozess zum Definieren und Erfassen von Schlüssel-Wert-Paaren verfügen oder einen Prozess einrichten, nutzen Sie diese Option. Wenn Sie Schlüssel verwenden möchten, die durch eine IP-Adresse vordefiniert sind, fahren Sie mit dem nächsten Abschnitt fort. Bei benutzerdefinierten Schlüsseln geben Sie den Wert an, wenn Sie Eigenschaften mit diesen Schlüssel-Wert-Paaren erstellen:

| Schlüssel | für das Targeting |
|---|---|
| `d_zx` | Postleitzahl (z. B. `d_zx=10022`). |

## Schlüssel auf Plattformebene, definiert durch IP-Adresse {#keys-ip-address}

Wir arbeiten mit [Digital Envoy](https://www.digitalenvoy.com/) zusammen, um die demografischen und geografischen Daten für die unten stehenden Schlüssel zu erhalten und zu aktualisieren. Die Werte für diese Schlüssel werden durch Abgleich [!DNL IP] Adressen mit entsprechenden geografischen und demografischen Daten bestimmt. Sie müssen jedoch weiterhin den Wert-Parameter eingeben, wenn Sie das Schlüssel-Wert-Paar in [!UICONTROL Trait Builder] erstellen.

| Schlüssel | für das Targeting |
|--- |--- |
| d_area_code | [Nordamerika-Codes](https://en.wikipedia.org/wiki/List_of_North_American_Numbering_Plan_area_codes).  Beispiel: <ul><li>**Eigenschaft**: d_area_code=801</li><li>**Eigenschaftsname**: Utah</li></ul> |
| d_city | Städte und Gemeinden. Laden Sie die [Liste der Städte](assets/d_city.txt).  Beispiel: <ul><li>Eigenschaft: d_city=bonn</li><li>Eigenschaftsname: Bonn</li></ul> **Tipp**: Verwenden Sie `d_city` in Verbindung mit `d_country`, um sicherzustellen, dass Sie nicht zwei Städte mit demselben Namen in verschiedenen Ländern auswählen. Mithilfe von `d_postal_code` können Sie Ihre Zielgruppenbestimmung noch spezifischer gestalten. |
| d_country | Die Werte entsprechen den ISO-Ländercodes. Eine durchsuchbare Liste der Codes finden Sie unter [ISO Online Browsing Platform](https://www.iso.org/obp/ui/#home). <br>  Das Targeting für das Vereinigte Königreich ist der einzige Sonderfall, der nicht ISO 3166 entspricht. Verwenden Sie für das Targeting in Großbritannien „GB“ anstelle von „GB“.  Um die Niederländischen Antillen ins Visier zu nehmen, ist der Code „AN“ seit 2010 veraltet. Das Gebiet wurde in fünf separate Gebietseinheiten aufgelöst. Daraus folgt, dass man beim Targeting auf den Niederländischen Antillen nicht „AN“, sondern eine Kombination der Länder-Codes für „CW“, „SX“ und „BQ“ verwenden sollte.  Beispiel: <br>  Eigenschaft: d_country=CZ <br>  Eigenschaftsname: Tschechische Republik <br>  Eigenschaft: d_country=UK <br>  Trait Name: Vereinigtes Königreich <br>  Eigenschaft: d_country=CW ODER d_country=SX ODER d_country=BQ <br>  Eigenschaftsname: Niederländische Antillen |
| d_dma_code | Metropolitan Area DMA-Codes. Laden Sie die [Liste der DMA-Regionen](assets/DMAregions.csv) (.csv-Format) herunter.  Beispiel: <ul><li>Eigenschaft: d_dma_code=807</li><li>Eigenschaftsname: San Francisco</li></ul> |
| d_lat | Breitengrad (z. B. d_lat=40.75). Laden Sie die [Latitude-Liste](assets/d_lat.txt) herunter. |
| d_long | Längengrad (z. B. d_long=73,98). Laden Sie die [Längengrad-Liste“ &#x200B;](assets/d_long.txt). |
| d_postal_code | Postleitzahlen (erweiterten +4-Code ausschließen). Laden Sie die [Liste der Postleitzahlen](assets/d_postal_code.txt) herunter.  Beispiel: <ul><li>Eigenschaft: d_post_code=84004 </li><li>Eigenschaftsname: Alpine</li></ul> |
| d_state | 2-stellige Abkürzung für einen US-Bundesstaat. Laden Sie die [Codes-Liste“ &#x200B;](assets/d_state.txt).  Beispiel: <ul><li>Eigenschaft: d_state=NY </li><li>Eigenschaftsname: New York</li></ul>d_state enthält wiederholte Werte für verschiedene Zustände in verschiedenen Ländern. Beispiel: d_state == „on“ entspricht mehreren Bundesstaaten: Ontario (in Kanada), Ondo (in Nigeria), Oshana (in Namibia). Wir empfehlen, dieses Signal mit anderen Signalen wie d_country zu koppeln, um ein spezifischeres Geotargeting zu ermöglichen. |
| d_region | Regionale alphanumerische IDs. Laden Sie die [Regionsliste“ &#x200B;](assets/Country_RegionCodes_City.csv).  Anschließend können Sie diese Liste verwenden, um Regions-IDs mit Regionsnamen abzugleichen. |
| d_isp | ISP/Organisation. Laden Sie die [ISP-Liste“ &#x200B;](assets/d_isp.txt). |

Die Liste [alle standortbasierten Signale](assets/all.txt) umfasst alle oben genannten Signale in der folgenden Reihenfolge: `d_country,d_city,d_region,d_state,d_dma_code,d_postal_code,d_area_code,d_lat,d_long`

>[!MORELIKETHIS]
>
>* [Anforderungen an Präfixe für Schlüsselvariablen](../../features/traits/trait-variable-prefixes.md)

