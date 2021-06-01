---
description: Beschreibt die Makros, die Sie einer Ziel-URL hinzufügen können.
seo-description: Beschreibt die Makros, die Sie einer Ziel-URL hinzufügen können.
seo-title: Definierte Zielmakros
solution: Audience Manager
title: Definierte Zielmakros
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Zielgrundlagen
exl-id: 7be4b417-046c-4fe3-a53c-e4e0ed36acb9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '669'
ht-degree: 3%

---

# Definierte Zielmakros {#destination-macros-defined}

Beschreibt die Makros, die Sie einem Ziel hinzufügen können [!DNL URL].

<!-- destination-macros.xml -->

Beim Erstellen eines Ziels [!DNL URL] können Sie die folgenden Makros in die Zeichenfolge [!DNL URL] einfügen. Fragen Sie bei Ihrem Daten-/Zielpartner nach der richtigen Makroplatzierung innerhalb des Ziels [!DNL URL].

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
   <td colname="col2"> <p>Erforderlich. </p> <p>Definiert den Speicherort des zugeordneten Segmentwerts in einer Ziel-URL. Normalerweise ist dies die <i>Segment-ID</i>, kann aber auch der Integrationscode sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Fügt die <span class="keyword">-Audience Manager</span>-ID des Benutzers in die Ziel-URL ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>Die <i>Datenquellen-ID</i> entspricht der Kennung einer Datenquelle, die an das Makro übergeben wird. </p> <p>Sehen wir uns an, wie das in einem einfachen Beispiel funktioniert. In diesem Fall haben wir einen <span class="keyword">-Audience Manager</span> mit den folgenden IDs und Bedingungen: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Datenquellen-ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Interne Kunden-ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Declared ID: Der Partner möchte diese Werte als deklarierte ID <code> 1:CustomerABC</code> übergeben. </li> 
    </ul> <p>Um dies mit <code>%dpid_<i>data source id</i>%</code> zu tun, formatiert der Partner <span class="keyword"> Audience Manager</span> das Makro wie folgt: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>Das Makro ersetzt <code> 1</code> durch <code> CustomerABC</code>. </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>Gibt an, ob die DSGVO-Vorschriften für den Besucher gelten oder nicht. Verwenden Sie dieses Makro, um die Zustimmung in Segmente einzubeziehen, die an URL-Ziele gesendet werden, die in IAB integriert sind. Weitere Informationen finden Sie unter <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-Plug-in für IAB TCF</a> .</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>Die Zustimmungszeichenfolge (einschließlich der IAB-Anbieter-ID), die erfasst wird, wenn Besucher die Zustimmung zu Ihrer Site erteilen oder verweigern. Verwenden Sie dieses Makro, um die Zustimmungszeichenfolge in Segmenten einzuschließen, die an in IAB integrierte URL-Ziele gesendet werden. Ersetzen Sie <code>XXXX</code> durch die Ziel-Partner-ID. Weitere Informationen finden Sie unter <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-Plug-in für IAB TCF</a> . </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Ermittelt das auf der übergeordneten Webseite verwendete Protokoll und fügt es in die Ziel-URL ein. Beispiel:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">Wenn die Webseite <b>https</b>://aam_client.com lautet, wird dieses Makro durch <b>https</b>://url-destination.com ersetzt. </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">Wenn die Webseite <b>http</b>://aam_client.com ist, wird dieses Makro durch <b>http</b>://url-destination.com ersetzt. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Fügt die ID <span class="keyword"> Experience Cloud</span> in die Ziel-URL ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Fügt den Bereich <span class="wintitle"> Data Collection Server (DCS)</span> in die Ziel-URL ein. Um Latenzzeiten zu minimieren, werden Besucher, die einen HTTP-Aufruf an <span class="keyword"> Audience Manager</span> durchführen, zum nächstgelegenen <span class="wintitle"> DCS</span>-Rechenzentrum weitergeleitet. Dies wird über das DNS erreicht, das den Standort des Besuchers erkennen und an das entsprechende Rechenzentrum weiterleiten kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>Führt eine Cache-Busting-Funktion durch, indem eine zufällige Nummer in die Ziel-URL eingefügt wird. Dadurch wird verhindert, dass Browser zwischengespeicherte Inhalte bereitstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Fügt einen UNIX-Zeitstempel in die Ziel-URL ein, um zu verhindern, dass Browser zwischengespeicherten Inhalt bereitstellen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cache-Busting mit Zielmakros {#destination-cache-busting}

Die Makros `%rnd%` und `%timestamp%` fügen eindeutige Werte in eine [!DNL URL]-Zeichenfolge ein, um das Zwischenspeichern im Browser zu verhindern.

## Cache-Busting mit `%rnd%` und `%timestamp%` {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

Browser speichern (speichern) häufig angeforderte Inhalte im Speicher. Beim Laden einer Seite werden gespeicherte Inhalte aus dem Cache und nicht von einem Remote-Server bereitgestellt. Dieser Prozess hilft, effiziente Download-Zeiten zu erhalten, da Daten lokal und nicht von einem anderen Standort aus bereitgestellt werden. Da für die Zwischenspeicherung jedoch kein Server-Aufruf erforderlich ist, kann dies die Berichterstellung verfälschen, indem die Anzahl der eindeutigen Anforderungen künstlich verringert wird.

Das Cache-Busting verhindert, dass Browser Inhalte speichern und wiederverwenden. Bei dieser Technik wird Code verwendet, der eine zufällige Nummer oder einen Zeitstempel in eine URL-Zeichenfolge einfügt, sodass diese für den Browser eindeutig aussieht. Daher wird jeder `HTTP`-Aufruf als separate Anfrage an den Server gezählt. Durch das Erzwingen eines neuen Server-Aufrufs für jede Anfrage können Sie die Genauigkeit der Berichterstellung wahren und Diskrepanzen reduzieren. [!DNL Audience Manager] stellt zwei Makros für das Cache-Busting bereit:

* `%rnd%`: Fügt eine zufällige Nummer in eine URL ein.
* `%timestamp%`: Fügt das Unix-Datum/-die-Uhrzeit in eine URL ein.

## Vergleich von `%rnd%` und `%timestamp%` {#compare-rnd-timestamp}

Beide Makros verhindern das Zwischenspeichern, `%rnd%` kann jedoch effizienter sein. Wenn beispielsweise mehrere Benutzer mit `%timestamp%` eine Seite gleichzeitig anzeigen, erhalten sie denselben Datums-/Uhrzeitwert. Daher ist [!DNL URL] nicht eindeutig und mehrere Aufrufe werden nur einmal gezählt. `%rnd%` generiert jedoch einen eindeutigen numerischen Wert für jeden Aufruf (auch wenn Benutzer dieselbe Seite gleichzeitig sehen). Das bedeutet, dass die Zeichenfolge [!DNL URL] unterschiedliche Werte enthält und als eindeutig gezählt wird.

>[!MORELIKETHIS]
>
>* [Definierte Zielmakros](../../features/destinations/destination-macros.md#destination-macros-defined)

