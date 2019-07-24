---
description: Allgemeine Fragen und Probleme mit Funktionen und Funktionen.
keywords: Audience Manager-Cookies
seo-description: Allgemeine Fragen und Probleme mit Funktionen und Funktionen.
seo-title: Häufig gestellte Fragen zu Produktfunktionen und Funktionen
solution: Audience Manager
title: Häufig gestellte Fragen zu Produktfunktionen und Funktionen
uuid: da 5 f 5089-24 a 8-4455-88 a 6-eb 62 d 83939 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Product Features and Functions FAQ{#product-features-and-functions-faq}

Allgemeine Fragen und Probleme mit Funktionen und Funktionen.

<br> 

<!-- 

faq_features_functions.xml

 -->

**Wie lautet meine Organisations-ID und wie finde ich sie?**

The *`Organization ID`* is a unique ID that identifies your organization to [!DNL Audience Manager] and the [!DNL Adobe Experience Cloud]. It consists of a case-sensitive, 24-character alphanumeric string followed by [!UICONTROL @AdobeOrg].

*`Organization ID`* Beispielsweise sieht dies wie folgt aus: `1FD6776A524453CC0A490D44@AdobeOrg`.

The *`Organization ID`* is used by Audience Manager's [DIL](../dil/dil-overview.md) API, the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/), and other [!DNL Experience Cloud] solutions. Users with Administrator permissions can find the *`Organization ID`* on the [!DNL Adobe Admin Console]. See the [Administration - User Management FAQ](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

<br> 

**Kann ich Masseneigenschaften oder Ziele stapelweise erstellen?**

Ja. See [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] tools *are not* supported by [!DNL Audience Manager]. Sie werden zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. For bulk changes, we recommend you work with the [Audience Manager APIs](../api/api.md) instead.

<br> 

**Kann[!DNL Audience Manager]der Bedarf an Drittanbieter-Tags oder -pixeln reduziert und die Seitenladezeiten verbessert werden?**

If [!DNL Audience Manager] is integrated with your third-party data partner, you can replace their pixels and tags with a server-to-server ID call to [!DNL Audience Manager]. In this case, [!DNL Audience Manager] would fire a single ID call the first time we see a user and synchronize that information with your third-party partner. Dadurch müssen Sie nicht mehr auf jeder Seite mehrere Pixel aufrufen. Durch Reduzieren von Pixelaufrufen können die Seitenladezeiten verbessert werden.

<br> 

**Ich habe einen Datenfeed abonniert. Where is that data stored?**

Your data feed and all the traits contained in the feed appear as subfolders and traits in [!DNL Audience Manager]. Go to **[!UICONTROL Audience Data > Traits]** and expand the [!UICONTROL 3rd-Party Data] folder to view your traits or create segments and models with this data.

<br> 

**Was ist[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager used [!UICONTROL Tag Insertion Manager] (TIM) to create and manage [!UICONTROL data collection code (DIL)]. This feature is obsolete and has been replaced first by [!UICONTROL Dynamic Tag Manager (DTM)], and later by [!DNL Adobe Launch]. For more information, see [Adobe Launch](https://docs.adobelaunch.com/) and [Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**Was sind die Unterschiede zwischen algorithmischen Modellen und Eigenschaften-Empfehlungen? When should I use each of them?**

**Algorithmische Modelle**

Algorithmische Modelle suchen nicht nur einflussreiche Eigenschaften, sondern können auch Benutzer anhand dieser Eigenschaften auswerten und jedem Benutzer ein einzelnes Ergebnis zuweisen. Anschließend erstellen Sie algorithmische Eigenschaften zur Ausrichtung Ihrer Benutzer. Mit Präzision und Reichweite der Reichweite im Eigenschaftenaufbau können Sie angeben, welche Benutzer unter allen Benutzern mit den einflussreichen Eigenschaften als Ziel dienen sollen.

Mit algorithmischen Modellen können Sie Benutzer auf unterschiedlichen Genauigkeitsstufen auswählen und in Audience Lab testen, welche Benutzergruppe besser konvertiert wird. See the detailed use case in [Compare Models in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

In Algorithmischen Modellen läuft das Modell alle 8 Tage ab und aktualisiert die Benutzer, die für algorithmische Eigenschaften qualifiziert sind.

**Trait Recommendations**

Eigenschaftsempfehlungen sind eine schnelle Möglichkeit, Einblicke zu anderen Eigenschaften zu erhalten, die den in einem Segment verwendeten Ähneln.

Sie sollten Eigenschaftsempfehlungen verwenden, wenn:

* Sie benötigen beim Erstellen eines Segments schnelle Einblicke;
* Sie verwenden die Segmente für kurze Kampagnen oder wenn Sie die Zielgruppe schnell unterdrücken möchten, die konvertiert.
* Sie versuchen, die Reichweite zu maximieren.

<br> 

**Gibt es Unterschiede zwischen Adobe Analytics und Audience Manager?**

Yes, please read [Understanding Segments in Analytics and Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) for an in-depth description of the differences.
