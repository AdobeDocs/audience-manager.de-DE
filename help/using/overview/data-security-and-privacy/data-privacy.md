---
description: Beschreibt die Integration von Audience Manager und die Einhaltung allgemein anerkannter bewährter Verfahren zum Schutz der Privatsphäre von Verbrauchern und Ausschluss-Verfahren.
seo-description: Beschreibt die Integration von Audience Manager und die Einhaltung allgemein anerkannter bewährter Verfahren zum Schutz der Privatsphäre von Verbrauchern und Ausschluss-Verfahren.
seo-title: Datenschutz
solution: Audience Manager
title: Datenschutz
uuid: 865e7b4e-fee1-4fa4-8035-1595fc77cd96
translation-type: tm+mt
source-git-commit: e6dcd0a33489ae388df25a95d3ad4841030afe31

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

Die IP-Adresse eines Besuchers auf der Website eines Kunden wird an das Adobe Data Processing Center (DPC) übertragen, wo die IP-Adresse gespeichert werden kann. Je nach Netzwerkkonfiguration des Besuchers muss die IP-Adresse nicht unbedingt die IP-Adresse des Computers des Besuchers darstellen. Bei der IP-Adresse kann es sich z. B. um die externe IP-Adresse einer Network Address Translation-(NAT-)Firewall, eines HTTP-Proxys oder eines Internet-Gateways handeln.

**** IP-Verschleierungsmethode: Gemäß den Grundsätzen von "Datenschutz nach Design"ermöglicht Adobe Audience Manager Kunden die Aktivierung der IP-Verschleierung über die Benutzeroberfläche, entweder global in allen geografischen Regionen oder für bestimmte Länder. Wenn Sie diese Einstellung aktivieren, wird das letzte Oktett (der letzte Teil) der IP-Adresse sofort verworfen, wenn die IP-Adresse in Audience Manager aufgenommen wird. Audience Manager verwirft diesen Teil der IP-Adresse vor der Verarbeitung (auch vor einer optionalen geografischen Suche oder Protokollierung der IP-Adresse). Beispiel:

* Bevor: `255.255.255.255`
* Nachher: `255.255.255.0`

>[!NOTE]
>
>Informationen zum Aktivieren der Verschleierung von IP-Adressen in der Benutzeroberfläche von Audience Manager finden Sie unter [IP-Adressenverschleierung](/help/using/features/administration/ip-obfuscation.md) .

**** Geografische Segmentierung: Wenn Sie die IP-Adressenverschleierung aktivieren, können die verbleibenden Oktette der IP-Adresse weiterhin für die Geo-Segmentierung und Berichterstellung in Audience Manager verwendet werden. Wenn Sie die IP-Adressenverschleierung nicht aktivieren, verwendet Audience Manager die vollständige IP-Adresse. Sie können die Funktion Geografische Segmentierung verwenden, mit der Sie in beiden Fällen eine IP-Position nach geografischem Gebiet identifizieren können. Bei Verwendung der IP-Verschleierung ist die Genauigkeit jedoch etwas geringer. Das Ermitteln von Information auf Stadtebene wird durch die Verschleierung der IP-Adresse wahrscheinlich merklich beeinträchtigt. Das Abrufen von Informationen auf Regions- und Landesebene sollte nur leicht beeinträchtigt werden. Geografische Segmentdaten sind nur auf der Ebene der Stadt oder der Postleitzahl granular und nicht auf der Ebene der einzelnen Personen. Erfahren Sie mehr über das [Geo-Targeting](/help/using/features/traits/trait-geotarget-keys.md) und das Einrichten von Eigenschaften mit geografischen Variablen.

## Verwandte Konzepte {#related-concepts}

* [Abmeldeverwaltung](/help/using/overview/data-security-and-privacy/opt-out-management.md)
* [Häufig gestellte Fragen zum Datenschutz und zur Datenaufbewahrung](/help/using/faq/faq-privacy.md)