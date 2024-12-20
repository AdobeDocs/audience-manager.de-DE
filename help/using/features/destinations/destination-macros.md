---
description: Beschreibt die Makros, die Sie einer Ziel-URL hinzufügen können.
seo-description: Describes the macros you can add to a destination URL.
seo-title: Destination Macros Defined
solution: Audience Manager
title: Zielmakros definiert
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
exl-id: 7be4b417-046c-4fe3-a53c-e4e0ed36acb9
source-git-commit: d86769304b03161490d0c3d9eb340cee64d52034
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 1%

---

# Zielmakros definiert {#destination-macros-defined}

Beschreibt die Makros, die Sie einer [!DNL URL] hinzufügen können.

<!-- destination-macros.xml -->

Beim Erstellen eines [!DNL URL] Ziels können Sie die folgenden Makros in die [!DNL URL] einfügen. Erkundigen Sie sich bei Ihrem Daten-/Zielpartner nach der korrekten Makroplatzierung im [!DNL URL].

>[!NOTE]
>
>Makros sind optional, sofern nicht anders angegeben. Eine *kursive* Formatierung gibt einen Variablenplatzhalter an.

<table id="table_2C532EFB9DAE41B08714753EBD7DFB05"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Makro </th> 
   <th colname="col2" class="entry"> Erklärung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> %alias%</code> </p> </td> 
   <td colname="col2"> <p>Erforderlich. </p> <p>Definiert den Speicherort des zugeordneten Segmentwerts in einer Ziel-URL. Normalerweise ist dies die <i>Segment-ID</i>, kann aber auch der Integrations-Code sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Fügt die <span class="keyword"> Audience Manager-ID des Benutzers </span> die Ziel-URL ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>Die <i>Datenquellen-ID</i> entspricht der Kennung für eine Datenquelle, die an das Makro übergeben wurde. </p> <p>Sehen wir uns an, wie dies funktioniert, in einem einfachen Beispiel. In diesem Fall haben wir einen <span class="keyword"> Audience Manager </span> Partner mit den folgenden IDs und Bedingungen: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Datenquellen-ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Eine interne Kunden-ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Declared ID: Der Partner möchte diese Werte als deklarierte ID-<code> 1:CustomerABC</code> übergeben. </li> 
    </ul> <p>Um dies mit dem <code>%dpid_<i>data source id</i>%</code> zu tun, formatiert der <span class="keyword"> Audience Manager </span> Partner das Makro wie folgt: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>Das Makro ersetzt <code> 1</code> durch <code> CustomerABC</code>. </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>Gibt an, ob für den Besucher DSGVO-bezogene Vorschriften gelten oder nicht. Verwenden Sie dieses Makro, um das Einverständnis in Segmente einzuschließen, die an mit IAB integrierte URL-Ziele gesendet werden. Detaillierte Informationen finden Sie unter <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-Plug-in für IAB </a>.</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>Die Einverständniszeichenfolge (einschließlich der IAB-Anbieter-ID), die erfasst wird, wenn Besuchende eine Einwilligung für Ihre Site erteilen oder verweigern. Verwenden Sie dieses Makro, um die Einverständniszeichenfolge in Segmente einzuschließen, die an mit IAB integrierte URL-Ziele gesendet werden. Ersetzen Sie <code>XXXX</code> durch die Zielpartner-ID. Detaillierte Informationen finden Sie unter <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-Plug-in für IAB </a>. </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Erkennt das auf der übergeordneten Web-Seite verwendete Protokoll und fügt es in die Ziel-URL ein. Beispiel:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">Wenn die Web-Seite <b>https</b>://aam_client.com lautet, wird dieses Makro durch "<b>" </b>://url-destination.com ersetzt </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">Wenn die Web-Seite <b>http</b>://aam_client.com lautet, wird dieses Makro durch <b>http</b>://url-destination.com ersetzt </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Fügt die <span class="keyword"> Experience Cloud</span> ID in die Ziel-URL ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Fügt die Region <span class="wintitle">-Datenerfassungsserver (DCS) in </span> Ziel-URL ein. Um die Latenz zu minimieren, werden Besuchende bei einem HTTP-Aufruf an <span class="keyword"> Audience Manager </span> an das nächstgelegene <span class="wintitle"> DCS</span>-Rechenzentrum umgeleitet. Dies erfolgt über das DNS, das den Standort des Besuchers erkennen und an das entsprechende Rechenzentrum weiterleiten kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>Führt eine Cache-Busting-Funktion durch, indem eine zufällige Zahl in die Ziel-URL eingefügt wird. Dadurch wird verhindert, dass Browser zwischengespeicherte Inhalte bereitstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Fügt einen UNIX-Zeitstempel in die Ziel-URL ein, um zu verhindern, dass Browser zwischengespeicherte Inhalte bereitstellen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Zwischenspeichern von Daten mit Zielmakros {#destination-cache-busting}

Die `%rnd%`- und `%timestamp%` fügen eindeutige Werte in eine [!DNL URL] ein, um das Zwischenspeichern im Browser zu verhindern.

## Cache-Busting mit `%rnd%` und `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

Häufig angeforderte Inhalte werden im Speicher zwischengespeichert (gespeichert). Beim Laden einer Seite werden gespeicherte Inhalte aus dem Cache und nicht von einem Remote-Server bereitgestellt. Dieser Prozess trägt dazu bei, effiziente Download-Zeiten beizubehalten, da Daten lokal und nicht von einem anderen Speicherort bereitgestellt werden. Da für die Zwischenspeicherung jedoch kein Server-Aufruf erforderlich ist, kann sie die Berichterstellung verfälschen, indem die Anzahl der eindeutigen Anforderungen künstlich verringert wird.

Cache-Busting verhindert, dass Browser Inhalte speichern und wiederverwenden. Bei dieser Technik wird ein Code verwendet, der eine zufällige Zahl oder einen Zeitstempel in eine URL-Zeichenfolge einfügt, wodurch sie im Browser eindeutig aussieht. Daher wird jeder `HTTP`-Aufruf als separate Anfrage an den Server gezählt. Das Erzwingen eines neuen Server-Aufrufs für jede Anfrage hilft, die Berichtsgenauigkeit aufrechtzuerhalten und Diskrepanzen zu reduzieren. [!DNL Audience Manager] bietet zwei Makros für Cache-Busting:

* `%rnd%`: Fügt eine zufällige Zahl in eine URL ein.
* `%timestamp%`: Fügt Datum/Uhrzeit der Unix-Version in eine URL ein.

## Vergleichen von `%rnd%` und `%timestamp%` {#compare-rnd-timestamp}

Beide Makros verhindern das Zwischenspeichern, `%rnd%` jedoch effizienter sein. Wenn beispielsweise `%timestamp%` mehrere Benutzende eine Seite gleichzeitig anzeigen, erhalten sie denselben Datums-/Uhrzeitwert. Daher ist die [!DNL URL] nicht eindeutig und mehrere Aufrufe werden nur einmal gezählt. `%rnd%` generiert jedoch für jeden Aufruf einen eindeutigen numerischen Wert (selbst wenn Benutzende dieselbe Seite gleichzeitig sehen). Dies bedeutet, dass die [!DNL URL]-Zeichenfolge unterschiedliche Werte enthält und als eindeutig gezählt wird.

>[!MORELIKETHIS]
>
>* [Definierte Zielmakros](../../features/destinations/destination-macros.md#destination-macros-defined)
