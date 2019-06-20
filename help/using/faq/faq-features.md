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


# Häufig gestellte Fragen zu Produktfunktionen und Funktionen{#product-features-and-functions-faq}

Allgemeine Fragen und Probleme mit Funktionen und Funktionen.

<br> 

<!-- 

faq_features_functions.xml

 -->

**Wie lautet meine Organisations-ID und wie finde ich sie?**

Die *`Organization ID`* ID ist eine eindeutige ID, die Ihre Organisation auf [!DNL Audience Manager] und [!DNL Adobe Experience Cloud]. Es besteht aus einer Groß- und Kleinschreibung, einer 24-stelligen alphanumerischen Zeichenfolge gefolgt von [!UICONTROL @AdobeOrg].

*`Organization ID`* Beispielsweise sieht dies wie folgt aus: `1FD6776A524453CC0A490D44@AdobeOrg`.

Wird *`Organization ID`* von der [DIL](../dil/dil-overview.md) -API des Audience Manager, dem [Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/)und anderen [!DNL Experience Cloud] Lösungen verwendet. Benutzer mit Administratorberechtigungen finden das *`Organization ID`* on [!DNL Adobe Admin Console]. Siehe Häufig gestellte Fragen [zu Administration - Häufig gestellte Fragen](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html)zur Benutzerverwaltung.

<br> 

**Kann ich Masseneigenschaften oder Ziele stapelweise erstellen?**

Ja. Siehe [Massenverwaltungswerkzeuge](../reference/bulk-management-tools/bulk-management-intro.md).

>[!NOTE]
>
>Die [!UICONTROL Bulk Management Tools] Werkzeuge *werden nicht* [!DNL Audience Manager]unterstützt. Sie werden zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. Bei Massenänderungen sollten Sie stattdessen mit den [Audience Manager-apis](../api/api.md) arbeiten.

<br> 

**Kann[!DNL Audience Manager]der Bedarf an Drittanbieter-Tags oder -pixeln reduziert und die Seitenladezeiten verbessert werden?**

Wenn [!DNL Audience Manager] Sie in Ihren Drittanbieter-Datenpartner integriert [!DNL Audience Manager]sind, können Sie deren Pixel und Tags durch einen Server-zu-Server-ID-Aufruf ersetzen. In diesem Fall [!DNL Audience Manager] würden Sie einen einzelnen ID-Aufruf auslösen, wenn wir einen Benutzer zum ersten Mal anzeigen und diese Informationen mit Ihrem Drittanbieter-Partner synchronisieren. Dadurch müssen Sie nicht mehr auf jeder Seite mehrere Pixel aufrufen. Durch Reduzieren von Pixelaufrufen können die Seitenladezeiten verbessert werden.

<br> 

**Ich habe einen Datenfeed abonniert. Wo sind diese Daten gespeichert?**

Ihr Datenfeed und alle im Feed enthaltenen Eigenschaften werden als Unterordner und Eigenschaften angezeigt [!DNL Audience Manager]. Wechseln **[!UICONTROL Audience Data > Traits]** Sie zum [!UICONTROL 3rd-Party Data] Ordner, um Ihre Eigenschaften anzuzeigen oder Segmente und Modelle mit diesen Daten zu erstellen.

<br> 

**Was ist[!UICONTROL Tag Insertion Manager (TIM)]?**

Audience Manager verwendet ( [!UICONTROL Tag Insertion Manager] TIM) zum Erstellen und Verwalten [!UICONTROL data collection code (DIL)]. Diese Funktion ist veraltet und wurde zuerst durch [!UICONTROL Dynamic Tag Manager (DTM)][!DNL Adobe Launch]und später ersetzt. Weitere Informationen finden Sie unter [Adobe Launch](https://docs.adobelaunch.com/) and [Dynamisches Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/).

<br> 

**Was sind die Unterschiede zwischen algorithmischen Modellen und Eigenschaften-Empfehlungen? Wann sollte ich diese verwenden?**

**Algorithmische Modelle**

Algorithmische Modelle suchen nicht nur einflussreiche Eigenschaften, sondern können auch Benutzer anhand dieser Eigenschaften auswerten und jedem Benutzer ein einzelnes Ergebnis zuweisen. Anschließend erstellen Sie algorithmische Eigenschaften zur Ausrichtung Ihrer Benutzer. Mit Präzision und Reichweite der Reichweite im Eigenschaftenaufbau können Sie angeben, welche Benutzer unter allen Benutzern mit den einflussreichen Eigenschaften als Ziel dienen sollen.

Mit algorithmischen Modellen können Sie Benutzer auf unterschiedlichen Genauigkeitsstufen auswählen und in Audience Lab testen, welche Benutzergruppe besser konvertiert wird. Weitere Informationen finden Sie im detaillierten Verwendungsfall unter Modelle [vergleichen in Audience Lab](../features/audience-lab/audience-lab-use-cases.md#compare-models).

In Algorithmischen Modellen läuft das Modell alle 8 Tage ab und aktualisiert die Benutzer, die für algorithmische Eigenschaften qualifiziert sind.

**Trait Recommendations**

Eigenschaftsempfehlungen sind eine schnelle Möglichkeit, Einblicke zu anderen Eigenschaften zu erhalten, die den in einem Segment verwendeten Ähneln.

Sie sollten Eigenschaftsempfehlungen verwenden, wenn:

* Sie benötigen beim Erstellen eines Segments schnelle Einblicke;
* Sie verwenden die Segmente für kurze Kampagnen oder wenn Sie die Zielgruppe schnell unterdrücken möchten, die konvertiert.
* Sie versuchen, die Reichweite zu maximieren.

<br> 

**Gibt es Unterschiede zwischen Adobe Analytics und Audience Manager?**

Ja. Bitte lesen Sie [die Segmente in Analytics und Audience Manager](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/aam-analytics-segments.html) , um eine ausführliche Beschreibung der Unterschiede zu erhalten.
