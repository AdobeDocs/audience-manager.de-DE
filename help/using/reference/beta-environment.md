---
description: Die Beta-Umgebung dient zum Testen Ihrer Audience Manager-Implementierung. In Beta vorgenommene Änderungen wirken sich nicht auf Produktionsdaten aus. Wenden Sie sich an Ihren Audience Manager-Partner-Lösungsvertreter, wenn Sie an der Verwendung der Beta-Umgebung interessiert sind.
keywords: sandbox
seo-description: Die Beta-Umgebung dient zum Testen Ihrer Audience Manager-Implementierung. In Beta vorgenommene Änderungen wirken sich nicht auf Produktionsdaten aus. Wenden Sie sich an Ihren Audience Manager-Partner-Lösungsvertreter, wenn Sie an der Verwendung der Beta-Umgebung interessiert sind.
seo-title: Beta-Umgebung
solution: Audience Manager
title: Beta-Umgebung
uuid: de 4 a 1 a 46-cfa 4-4 f 64-8569-48 a 7650 fd 8 cf
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Beta-Umgebung {#beta-environment}

Die Beta-Umgebung dient zum Testen Ihrer Audience Manager-Implementierung. In Beta vorgenommene Änderungen wirken sich nicht auf Produktionsdaten aus. Wenden Sie sich an Ihren Audience Manager-Partner-Lösungsvertreter, wenn Sie an der Verwendung der Beta-Umgebung interessiert sind.

## Überblick

Die Beta-Umgebung ist eine exakte Replizierung der Produktionsumgebung ohne experimentelle oder nicht veröffentlichte Funktionen. Ihre Anmeldeinformationen aus der Produktionsumgebung sind in der Beta-Umgebung gültig.

**Zeitplan aktualisieren**

Die Beta-Umgebung wird am Ende jedes Monats während der Stoßzeiten aktualisiert.

**Ausgehender Traffic**

Ausgehender Traffic ist für die Beta-Umgebung nicht aktiviert.

<!-- 

Added re: AAM-30826.

 -->

## Endpunkte



| Dienst | URL/Hostname | Zugriff auf den Zugriff |
|--- |--- | --- |
| S3 | Wenden Sie sich an Ihren Audience Manager-Partner oder Kundendienst. | Wenden Sie sich an Ihren Audience Manager-Partner oder Kundendienst, um ein Amazon S 3-Bucket für Ihre Beta-Instanz einzurichten. Lesen Sie die [Vorteile der Verwendung von Amazon S 3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Siehe [Zugriff auf das DCS in der Beta-Umgebung](../reference/beta-environment.md#access-dcs-beta-environment). |
| Benutzeroberfläche | `https://bank-beta.demdex.com` | Ihre Anmeldedaten für die Produktionsumgebung sind für die Beta-Umgebung gültig. |
| API | `https://api-beta.demdex.com/...` | Ihre Anmeldedaten für die Produktionsumgebung sind für die Beta-Umgebung gültig. Es wird empfohlen, einen generischen API-Benutzer zu erstellen, siehe [Details](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Zugriff auf das DCS in der Beta-Umgebung {#access-dcs-beta-environment}

1. Tätigen Sie einen DCS-Aufruf mit dem Curl [-Befehl](https://curl.haxx.se/docs/manpage.html). Curl ist ein Tool zum Übertragen von Daten von oder auf einen Server, wobei einer der vielen unterstützten Protokolle verwendet wird.

   Beispiel:

   `curl -v https://dcs-beta.demdex.net/event`

1. Stellen Sie sicher, dass Ihre Anforderung von der Beta-DCS bereitgestellt wurde, indem Sie im DCS-Antwortkopf nach &quot;Sandbox&quot; suchen.

   Beispiel:

   ```
   curl -v http://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

<!--

1. Determine the load balancer's endpoint IP addresses.

   Run the `dig`  [command](https://en.wikipedia.org/wiki/Dig_(command)) to determine the IP address of the nearest load balancer. The `dig` command queries the Domain Name System and returns the name and IP addresses of the [!DNL Audience Manager] [!UICONTROL Data Collection Servers (DCS)].

   ```
   dig dcs-beta.demdex.net
   ...
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.87.15.51
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 50.16.150.8
   dcs-sandbox-1754093861.us-east-1.elb.amazonaws.com. 60 IN A 52.2.228.100
   ```

2. Using one of the addresses in the above table, add a static DNS entry in the [!DNL /etc/hosts] file.

   On Windows, modify [!DNL c:\WINDOWS\system32\drivers\etc\hosts].

   For example:

   [!DNL 52.87.15.51 *`samplepartner`*.demdex.net]

   >[!NOTE]
   >
   >The addresses change occasionally, so you must keep your [!DNL /etc/hosts] file up to date.

   Additionally, if you need to set up ID synchronization, you must add a similar entry for [!DNL dpm.demdex.net.]

   [!DNL 52.87.15.51 dpm.demdex.net]. 

3. Make a DCS call, using the `curl` [command](https://curl.haxx.se/docs/manpage.html). Curl is a tool to transfer data from or to a server, using one of many supported protocols.

   For example:

   [!DNL https://<domain>/event?product=camera] 

4. Verify that your request was served by the beta DCS by looking for "sandbox" in the DCS response header.

   For example:

   ```
   curl -v https://dcs-beta.demdex.net/?event
   [...]
   < DCS: va6-sandbox-dcs-3.sandbox.demdex.com <release_number>
   [...]
   ```

   -->