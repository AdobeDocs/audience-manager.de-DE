---
description: Beschreibt die Integration von Audience Manager und die Einhaltung allgemein anerkannter bewährter Verfahren zum Schutz der Privatsphäre von Verbrauchern und Ausschluss-Verfahren.
seo-description: Beschreibt die Integration von Audience Manager und die Einhaltung allgemein anerkannter bewährter Verfahren zum Schutz der Privatsphäre von Verbrauchern und Ausschluss-Verfahren.
seo-title: Datenschutz
solution: Audience Manager
title: Datenschutz
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: a1d75c83d5876090f3a4d284b18984e2d1a70313

---


# Datenschutz{#data-privacy}

Beschreibt die Integration von Audience Manager und die Einhaltung allgemein anerkannter bewährter Verfahren zum Schutz der Privatsphäre von Verbrauchern und Ausschluss-Verfahren.

## Datenschutz{#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Verbraucherschutz {#consumer-privacy-protection}

Audience Manager erkennt den impliziten Pakt zwischen Verbrauchern und den Online-Marken, mit denen sie interagieren. Beide Parteien profitieren vom transparenten Austausch anonymer Datenelemente:

* Kunden erhalten personalisierte Inhalte, reduzierte Produktangebote und optimierte Benutzererfahrungen.
* Marken erhalten wichtige Umsatzströme, die mehrere Online-Geschäftsmodelle unterstützen.

Durch unsere fortwährende Unterstützung dieses Modells setzt sich Audience Manager weiterhin für Transparenz und Kontrolle der Verbraucher ein und setzt sich dafür ein, die Selbstregulierungsgrundsätze der Online-verhaltensbasierten Werbung (OBA) einzuhalten oder zu übertreffen.

## Abmeldeverwaltung {#opt-out-management}

Die Ausschluss-Dokumentation wurde erweitert und in einen anderen Teil unserer Dokumentation verschoben. Siehe [Abmeldeverwaltung](../../overview/data-security-and-privacy/opt-out-management.md).

<!-- 

<p>  </p>
<table id="table_A1FF33B328BD451FAFF6C6B8422F928B"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="2.74*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Opt-Out For </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
    <td colname="col2"> <p>The <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Your Privacy Choices page</a> provides 1-click features that let you control and opt-out of data collection by the Adobe Experience Cloud advertising solutions (including Audience Manager). Specifically, see the <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> business customer section</a> of the Privacy Choices page. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Browsers that do not support third-party cookies </p> </td> 
    <td colname="col2"> <p>See <a href="../../features/declared-ids.md#declared-id-targeting"> Declared ID Targeting</a>. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>Mobile devices </p> </td> 
    <td colname="col2"> <p>See the opt-out and privacy settings for: </p> <p> 
      <ul id="ul_86EFAB879215403D937B5148C26A41D9"> 
       <li id="li_C0B544E8F4FE473B94A5436D3A60BDB1"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Android devices</a> </li> 
       <li id="li_26C787BAB729499A9FEDF055E9AB0637"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> iOS devices</a> </li> 
      </ul> </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

## Erfassen von IP-Adressen und IP-Adressenverschleierung {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** IP-Verschleierungsmethode: Gemäß den Grundsätzen von "Privacy By Design"ermöglicht Adobe Audience Manager Kunden, Verschleierung über die Benutzeroberfläche zu aktivieren, entweder global über alle geografischen Regionen oder für bestimmte Länder. [!DNL IP] Wenn Sie diese Einstellung aktivieren, wird das letzte Oktett (der letzte Teil) der [!DNL IP] Adresse sofort verworfen, wenn die [!DNL IP] Adresse in Audience Manager aufgenommen wird. Audience Manager verwirft diesen Teil der [!DNL IP] Adresse vor der Verarbeitung (auch vor einer optionalen geografischen Suche oder Protokollierung der [!DNL IP] Adresse). Beispiel:

* Bevor: `255.255.255.255`
* Nachher: `255.255.255.0`

>[!NOTE]
>
>Siehe [IP-Adressenverschleierung](/help/using/features/administration/ip-obfuscation.md) , um zu erfahren, wie Sie die [!DNL IP] Adressenverschleierung in der Benutzeroberfläche von Audience Manager aktivieren.

Sehen Sie sich das unten stehende Video an, um zu verstehen, wie [!DNL IP] Adressenverschleierung in Audience Manager funktioniert.

>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=ger)

**** Geografische Segmentierung: Wenn Sie die [!DNL IP] Adressenverschleierung aktivieren, können die verbleibenden Oktette der [!DNL IP] Adresse weiterhin für die Geo-Segmentierung und Berichterstellung in Audience Manager verwendet werden. Wenn Sie die [!DNL IP] Adressenverschleierung nicht aktivieren, verwendet Audience Manager die vollständige [!DNL IP] Adresse. Sie können die Funktion Geografische Segmentierung verwenden, mit der Sie einen Standort in jedem Fall nach geografischem Gebiet identifizieren können, allerdings mit etwas geringer Präzision, wenn [!DNL IP] [!DNL IP] Verschleierung verwendet wird. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. Das Abrufen von Informationen auf Regions- und Landesebene sollte nur leicht beeinträchtigt werden. Geografische Segmentdaten sind nur auf der Ebene der Stadt oder der Postleitzahl granular und nicht auf der Ebene der einzelnen Personen. Erfahren Sie mehr über das [Geo-Targeting](/help/using/features/traits/trait-geotarget-keys.md) und das Einrichten von Eigenschaften mit geografischen Variablen.

## Verwandte Konzepte {#related-concepts}

* [Abmeldeverwaltung](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [Häufig gestellte Fragen zum Datenschutz und zur Datenaufbewahrung](/help/using/faq/faq-privacy.md)