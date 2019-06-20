---
description: Beschreibt die Makros, die Sie zu einer Ziel-URL hinzufügen können.
seo-description: Beschreibt die Makros, die Sie zu einer Ziel-URL hinzufügen können.
seo-title: Zielmakros definiert
solution: Audience Manager
title: Zielmakros definiert
uuid: 982 cab 5-8 a 3 f -4 f 96-b 4 d 0-291709712 ad 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Zielmakros definiert {#destination-macros-defined}

Beschreibt die Makros, die Sie einem Ziel hinzufügen [!DNL URL]können.

<!-- destination-macros.xml -->

Beim Erstellen eines [!DNL URL] Ziels können Sie die folgenden Makros in die [!DNL URL] Zeichenfolge einfügen. Wenden Sie sich an Ihren Daten-/Zielpartner, um eine ordnungsgemäße Makroplatzierung innerhalb des Ziels [!DNL URL]zu erhalten.

>[!NOTE]
>
>Makros sind optional, wenn nicht anders angegeben. Eine *kursive* Formatierung gibt einen Variablenplatzhalter an.

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
   <td colname="col2"> <p>Fügt die <span class="keyword"> Audience Manager</span> -ID des Benutzers in die Ziel-URL ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>% dpid_<i>data source id</i>%</code> </p> </td> 
   <td colname="col2"> <p>Die <i>Datenquellen-ID</i> entspricht dem Bezeichner für eine Datenquelle, die an das Makro übergeben wird. </p> <p>Sehen wir uns an, wie dies in einem einfachen Beispiel funktioniert. In diesem Fall haben wir einen <span class="keyword"> Audience Manager</span> -Partner mit den folgenden IDs und Bedingungen: </p> 
    <ul id="ul_697508B437EB4090B121AFA5D519AFBE"> 
     <li id="li_32D9F72A7D1543A892DC7E1529E98A96">Datenquellen-ID: <code> 1</code> </li> 
     <li id="li_099F5B63D2244B5AADA9B26CB6152E6B">Eine interne Kunden-ID: <code> Customerabc</code> </li> 
     <li id="li_0D9FE501C16444DDB388C8E934E5A8C6">Deklarierte ID: Der Partner möchte diese Werte als deklarierte ID <code> 1 übergeben: Customerabc</code>. </li> 
    </ul> <p>Um dies mit der <code>% dpid_<i>data source id</i>% zu erreichen</code>, würde der <span class="keyword"> Audience Manager</span> -Partner das Makro wie folgt formatieren: </p> 
    <ul class="simplelist"> 
     <li> <code> % dpid_ 1%</code> </li> 
    </ul> <p>Das Makro ersetzt <code> 1</code> durch <code> customerabc</code>. </p> <p> 
     <draft-comment>
       Basierend auf AAM -22193 https://jira.corp.adobe.com/browse/AAM-22193 
     </draft-comment> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % http_ proto %</code> </p> </td> 
   <td colname="col2"> <p>Erkennt das in der übergeordneten Webseite verwendete Protokoll und fügt es in die Ziel-URL ein. Beispiel: 
     <br> 
     <ul id="ul_026F56EC46E94D9EB1153557C0F65325"> 
      <li id="li_B41EF140CC274CB68FE7213DD8B908C0">Wenn die Webseite <b>https://aam_client.com lautet</b>, wird dieses Makro durch <b>https://url-destination.com</b> </li> 
      <li id="li_BDCD6EA69B004A92BA6981952341BD77">Wenn die Webseite <b>http://aam_client.com lautet</b>, wird dieses Makro durch <b>http://url-destination.com</b> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % mcid %</code> </p> </td> 
   <td colname="col2"> <p>Fügt die <span class="keyword"> Experience Cloud</span> ID in die Ziel-URL ein. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> % Region %</code> </p> </td> 
   <td colname="col2"> <p>Fügt den Bereich <span class="wintitle"> des Datenerfassungsservers (DCS)</span> in die Ziel-URL ein. Um Latenzzeiten <span class="keyword"> zu minimieren</span>, werden sie zum nächsten <span class="wintitle"> DCS</span> -Datacenter weitergeleitet, wenn der Besucher einen HTTP-Aufruf an Audience Manager durchführt. Dies wird über DNS erreicht, das den Ort des Besuchers erkennen und zur entsprechenden Datacenter leiten kann. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> % rnd %</code> </p> </td> 
   <td colname="col2"> <p>Führt eine Cache-Busting-Funktion durch, indem eine zufallszahl in die Ziel-URL eingefügt wird. Dies verhindert, dass Browser zwischengespeicherte Inhalte bereitstellen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> %timestamp%</code> </p> </td> 
   <td colname="col2"> <p>Fügt einen UNIX-Zeitstempel in die Ziel-URL ein, um zu verhindern, dass Browser zwischengespeicherte Inhalte bereitstellen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cache-Busting mit Zielmakros {#destination-cache-busting}

Die `%rnd%` Werte und `%timestamp%` Makros fügen eindeutige Werte in eine [!DNL URL] Zeichenfolge ein, um die Zwischenspeicherung des Browsers zu verhindern.

## Cache-Busting `%rnd%` und `%timestamp%`{#dest-cache-busting}

<!-- c_dest_cache_busting.xml -->

Browser speichern (speichern) häufig angeforderte Inhalte im Arbeitsspeicher. Beim Laden einer Seite werden gespeicherte Inhalte vom Cache statt vom Remote-Server bereitgestellt. Dieser Prozess sorgt für effiziente Downloadzeiten, da die Daten lokal statt von einem anderen Ort bereitgestellt werden. Da die Zwischenspeicherung jedoch keinen Serveraufruf erfordert, kann dies die Berichterstellung verfälschen, indem die Anzahl eindeutiger Anforderungen künstlich verringert wird.

Durch das Buche-Busting wird verhindert, dass Browser Inhalte speichern und wiederverwenden. Diese Technik verwendet Code, der eine zufällige Zahl oder einen Zeitstempel in eine URL-Zeichenfolge einfügt, wodurch es eindeutig für den Browser aussieht. Daher wird jeder `HTTP` Aufruf als separate Anfrage an den Server gezählt. Durch Erzwingen eines neuen Serveraufrufs für jede Anforderung wird die Genauigkeit der Berichterstellung beibehalten und Diskrepanzen reduziert. [!DNL Audience Manager] stellt zwei Makros für das Cache-Busting bereit:

* `%rnd%`: Fügt eine zufallszahl in eine URL ein.
* `%timestamp%`: Fügt das Unix-Datum/-Uhrzeit in eine URL ein.

## Vergleich `%rnd%` und `%timestamp%`{#compare-rnd-timestamp}

Beide Makros verhindern Zwischenspeicherung, `%rnd%` können jedoch effizienter sein. Wenn `%timestamp%`beispielsweise mehrere Benutzer eine Seite gleichzeitig anzeigen, erhalten sie denselben Datums-/Uhrzeitwert. Daher wird die Variable [!DNL URL] nicht eindeutig und mehrere Aufrufe werden nur einmal gezählt. `%rnd%` Generiert jedoch einen eindeutigen numerischen Wert für jeden Aufruf (auch wenn die Benutzer dieselbe Seite gleichzeitig sehen). Dies bedeutet, dass die [!DNL URL] Zeichenfolge verschiedene Werte enthält und als eindeutig gezählt wird.

>[!MORE_ LIKE_ THIS]
>
>* [Zielmakros definiert](../../features/destinations/destination-macros.md#destination-macros-defined)