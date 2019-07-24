---
description: Beschreibt die Integration von Audience Manager und die Einhaltung von allgemeinen Best Practices in Bezug auf den Datenschutz und die Abmeldeverfahren.
seo-description: Beschreibt die Integration von Audience Manager und die Einhaltung von allgemeinen Best Practices in Bezug auf den Datenschutz und die Abmeldeverfahren.
seo-title: Datenschutz
solution: Audience Manager
title: Datenschutz
uuid: 865 e 7 b 4 e-fee 1-4 fa 4-8035-1595 fc 77 cd 96
translation-type: tm+mt
source-git-commit: e6dcd0a33489ae388df25a95d3ad4841030afe31

---


# Datenschutz{#data-privacy}

Beschreibt die Integration von Audience Manager und die Einhaltung von allgemeinen Best Practices in Bezug auf den Datenschutz und die Abmeldeverfahren.

## Datenschutz{#data-privacy-center}

See the [Adobe Privacy Center](https://www.adobe.com/privacy/opt-out.html).

## Consumer Privacy Protection {#consumer-privacy-protection}

Audience Manager erkennt den impliziten Vertrag zwischen Verbrauchern und den Online-Marken, mit denen sie interagieren. Beide Parteien nutzen den transparenten Austausch anonymer Datenelemente:

* Kunden erhalten personalisierte Inhalte, preisgezählte Produktangebote und optimierte Benutzererfahrungen.
* Marken erhalten wichtige Umsatzstreams, die mehrere Online-Geschäftsmodelle unterstützen.

In unserer fortlaufenden Unterstützung dieses Modells bemüht sich Audience Manager weiterhin, Transparenz und Kontrolle für Verbraucher bereitzustellen und die Selbstkontrollprinzipien Online Verhaltensbasierter Advertising (OBA) zu besprechen oder zu überschreiten.

## Opt-Out Management {#opt-out-management}

Die Ausschluss-Dokumentation wurde erweitert und in einen separaten Teil unserer Dokumentation verschoben. See [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

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

## Collecting IP Addresses and IP Address Obfuscation {#collecting-ip-addresses}

<!-- 

Adobe has enabled processes and offers settings that allow customers to use Audience Manager in compliance with applicable data privacy laws.

-->

Die IP-Adresse eines Besuchers auf der Website eines Kunden wird an das Adobe Data Processing Center (DPC) übertragen, wo die IP-Adresse gespeichert werden kann. Abhängig von der Netzwerkkonfiguration des Besuchers stellt die IP-Adresse möglicherweise nicht unbedingt die IP-Adresse des Besuchercomputers dar. Bei der IP-Adresse kann es sich z. B. um die externe IP-Adresse einer Network Address Translation-(NAT-)Firewall, eines HTTP-Proxys oder eines Internet-Gateways handeln.

**IP-Verschleierungsmethode:** Nach den Prinzipien von "Datenschutz nach Design" erlaubt Adobe Audience Manager Kunden, IP-Verschleierung aus der Benutzeroberfläche zu aktivieren, entweder global in allen geografischen Regionen oder in bestimmten Ländern. Wenn Sie diese Einstellung aktivieren, wird das letzte Oktett (der letzte Teil) der IP-Adresse sofort verworfen, wenn die IP-Adresse in Audience Manager übernommen wird. Audience Manager verwirft diesen Teil der IP-Adresse vor der Verarbeitung (einschließlich vor einer optionalen geografischen Suche oder Protokollierung der IP-Adresse). Beispiel:

* Bevor: `255.255.255.255`
* Nachher: `255.255.255.0`

>[!NOTE]
>
>See [IP Address Obfuscation](/help/using/features/administration/ip-obfuscation.md) to learn how to enable IP address obfuscation in the Audience Manager UI.

**Geografische Segmentierung:** Wenn Sie die IP-Adressenverschleierung aktivieren, können die verbleibenden Oktets der IP-Adresse weiterhin für Geo-Segmentierung und Berichterstellung in Audience Manager verwendet werden. Wenn Sie die IP-Adressenverschleierung nicht aktivieren, verwendet Audience Manager die vollständige IP-Adresse. Sie können die Funktion Geografische Segmentierung verwenden, mit der Sie einen IP-Standort nach geografischer Region in beiden Fällen identifizieren können, aber mit einigen leichten Verlusten, wenn die IP-Verschleierung verwendet wird. Das Ermitteln von Information auf Stadtebene wird durch die Verschleierung der IP-Adresse wahrscheinlich merklich beeinträchtigt. Das Abrufen von Informationen auf Regions- und Landesebene sollte nur leicht beeinträchtigt werden. Geografische Segmentierungsdaten sind nur auf Ebene der Stadt oder Postleitzahl granular und nicht auf individueller Ebene. Read more about [geo-targeting](/help/using/features/traits/trait-geotarget-keys.md) and how to set up traits with geographic variables.

## Verwandte Konzepte {#related-concepts}

* [Ausschluss-Management](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [Häufig gestellte Fragen zu Datenschutz und Datenaufbewahrung](/help/using/faq/faq-privacy.md)