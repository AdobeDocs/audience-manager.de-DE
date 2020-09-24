---
description: Beschreibt die Makros, die Sie einer Ziel-URL hinzufügen können.
seo-description: Beschreibt die Makros, die Sie einer Ziel-URL hinzufügen können.
seo-title: Definierte Zielmakros
solution: Audience Manager
title: Definierte Zielmakros
uuid: 982cab05-8a3f-4f96-b4d0-291709712ad1
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 4bf32099e964c421d943d9925c74dd0d4d6ee576
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 3%

---


# Definierte Zielmakros {#destination-macros-defined}

Beschreibt die Makros, die Sie einem Ziel hinzufügen können [!DNL URL].

<!-- destination-macros.xml -->

Beim Erstellen eines [!DNL URL] Ziels können Sie die folgenden Makros in die [!DNL URL] Zeichenfolge einfügen. Fragen Sie bei Ihrem Daten-/Zielpartner nach einer richtigen Makroplatzierung innerhalb des Ziels [!DNL URL].

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
   <td colname="col2"> <p>Erforderlich. </p> <p>Definiert die Position des zugeordneten Segmentwerts in einer Ziel-URL. Normalerweise ist dies die <i>Segment-ID</i>, könnte aber auch der Integrationscode sein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %did%</code> </p> </td> 
   <td colname="col2"> <p>Fügt die <span class="keyword"> Audience Manager</span> -ID des Benutzers in die Ziel-URL ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>%dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>Die <i>Datenquellen-ID</i> entspricht dem Bezeichner für eine Datenquelle, die an das Makro übergeben wird. </p> <p>Sehen wir uns an, wie das in einem einfachen Beispiel funktioniert. In diesem Fall haben wir einen <span class="keyword"> Audience Manager</span> -Partner mit den folgenden IDs und Bedingungen: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Datenquellen-ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Eine interne Kunden-ID: <code> CustomerABC</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Deklarierte ID: Der Partner möchte diese Werte als deklarierte ID übergeben <code> 1:CustomerABC</code>. </li> 
    </ul> <p>Um dies mit dem <code>%dpid_<i>data source id</i>%</code>zu tun, formatiert der <span class="keyword"> Audience Manager</span> -Partner das Makro wie folgt: </p> 
    <ul class="simplelist"> 
     <li> <code> %dpid_1%</code> </li> 
    </ul> <p>Das Makro wird durch <code> 1</code> ersetzt <code> CustomerABC</code>. </p> <p> 
     <!--
       Based on AAM-22193 https://jira.corp.adobe.com/browse/AAM-22193 
     --> </p> </td> 
  </tr> 
  <tr>
    <td><p><code>${GDPR}</code></p></td>
    <td><p>Gibt an, ob GDPR-Regelungen für den Besucher gelten. Verwenden Sie dieses Makro, um die Zustimmung in Segmente einzubeziehen, die an in IAB integrierte URL-Ziele gesendet werden. Weitere Informationen finden Sie unter <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-Plug-in für IAB TCF</a> .</p></td>
  </tr>
   <tr>
    <td><code>${GDPR_CONSENT_XXXX}</code></p></td>
    <td><p>Die Zustimmungszeichenfolge (einschließlich der IAB-Anbieter-ID), die erfasst wird, wenn Besucher die Zustimmung zu Ihrer Site erteilen oder verweigern. Verwenden Sie dieses Makro, um die Zustimmungszeichenfolge in Segmente einzuschließen, die an in IAB integrierte URL-Ziele gesendet werden. Ersetzen Sie dies <code>XXXX</code> durch die Ziel-Partner-ID. Weitere Informationen finden Sie unter <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-Plug-in für IAB TCF</a> . </p></td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> %http_proto%</code> </p> </td> 
   <td colname="col2"> <p>Erkennt das Protokoll, das auf der übergeordneten Webseite verwendet wird, und fügt es in die Ziel-URL ein. Beispiel:
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">Wenn die Webseite <b>https</b>://aam_client.com lautet, wird dieses Makro durch <b>https</b>://url-destination.com ersetzt. </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">Wenn die Webseite <b>http</b>://aam_client.com lautet, wird dieses Makro durch <b>http</b>://url-destination.com ersetzt. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %mcid%</code> </p> </td> 
   <td colname="col2"> <p>Fügt die <span class="keyword"> Experience Cloud</span> -ID in die Ziel-URL ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> %region%</code> </p> </td> 
   <td colname="col2"> <p>Fügt die <span class="wintitle"> Datenerfassungsserverregion (DCS)</span> in die Ziel-URL ein. Um Latenzzeiten zu minimieren, werden sie, wenn der Besucher einen HTTP-Aufruf an <span class="keyword"> Audience Manager</span>durchführt, an das nächstgelegene <span class="wintitle"> DCS</span> -Rechenzentrum weitergeleitet. Dies wird durch DNS erreicht, das den Standort des Besuchers ermitteln und an das entsprechende Rechenzentrum weiterleiten kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %rnd%</code> </p> </td> 
   <td colname="col2"> <p>Führt eine Cache-Busting-Funktion durch, indem eine Zufallszahl in die Ziel-URL eingefügt wird. Dadurch wird verhindert, dass Browser zwischengespeicherte Inhalte bereitstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Fügt einen UNIX-Zeitstempel in die Ziel-URL ein, um zu verhindern, dass Browser zwischengespeicherte Inhalte bereitstellen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cache-Busting mit Zielmakros {#destination-cache-busting}

Die `%rnd%` und `%timestamp%` Makros fügen eindeutige Werte in eine [!DNL URL] Zeichenfolge ein, um die Zwischenspeicherung im Browser zu verhindern.

## Cache-Busting mit %rnd% und %timestamp% {#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

Browser speichern (speichern) häufig angeforderte Inhalte im Arbeitsspeicher. Beim Laden einer Seite werden gespeicherte Inhalte aus dem Cache und nicht von einem Remote-Server bereitgestellt. Dieser Prozess hilft, effiziente Downloadzeiten zu erhalten, da die Daten lokal und nicht von einem anderen Standort aus bereitgestellt werden. Da für die Zwischenspeicherung kein Serveraufruf erforderlich ist, kann dies den Berichte verfälschen, indem die Anzahl der individuellen Anforderungen künstlich verringert wird.

Cache-Busting verhindert, dass Browser Inhalte speichern und wiederverwenden. Bei dieser Methode wird Code verwendet, der eine zufällige Nummer oder einen Zeitstempel in eine URL-Zeichenfolge einfügt, sodass sie für den Browser eindeutig aussieht. Daher wird jeder `HTTP` Aufruf als separate Anforderung an den Server gezählt. Das Erzwingen eines neuen Serveraufrufs für jede Anforderung hilft, die Genauigkeit des Berichte zu erhalten und Diskrepanzen zu reduzieren. [!DNL Audience Manager] stellt zwei Makros zum Zwischenspeichern bereit:

* `%rnd%`: Fügt eine Zufallszahl in eine URL ein.
* `%timestamp%`: Fügt das Unix-Datum/die Unix-Uhrzeit in eine URL ein.

## Vergleich von %rnd% und %timestamp% {#compare-rnd-timestamp}

Beide Makros verhindern die Zwischenspeicherung, können aber effizienter `%rnd%` sein. Wenn beispielsweise mehrere Benutzer eine Seite gleichzeitig `%timestamp%`Ansicht haben, erhalten sie denselben Datums-/Uhrzeitwert. Daher [!DNL URL] ist der Aufruf nicht eindeutig und mehrere Aufrufe werden nur einmal gezählt. Generiert jedoch einen eindeutigen numerischen Wert für jeden Aufruf (auch wenn Benutzer dieselbe Seite gleichzeitig sehen). `%rnd%` Das bedeutet, dass die [!DNL URL] Zeichenfolge unterschiedliche Werte enthält und als eindeutig gezählt wird.

>[!MORELIKETHIS]
>
>* [Definierte Zielmakros](../../features/destinations/destination-macros.md#destination-macros-defined)