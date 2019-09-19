---
description: Die Betaumgebung dient zum Testen Ihrer Audience Manager-Implementierung. Änderungen, die in der Beta-Version vorgenommen werden, wirken sich nicht auf Produktionsdaten aus. Wenden Sie sich an Ihren Audience Manager Partner Solutions-Kundenbetreuer, wenn Sie an der Betaumgebung interessiert sind.
keywords: Sandbox
seo-description: Die Betaumgebung dient zum Testen Ihrer Audience Manager-Implementierung. Änderungen, die in der Beta-Version vorgenommen werden, wirken sich nicht auf Produktionsdaten aus. Wenden Sie sich an Ihren Audience Manager Partner Solutions-Kundenbetreuer, wenn Sie an der Betaumgebung interessiert sind.
seo-title: Beta-Umgebung
solution: Audience Manager
title: Beta-Umgebung
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Beta-Umgebung {#beta-environment}

Die Betaumgebung dient zum Testen Ihrer Audience Manager-Implementierung. Änderungen, die in der Beta-Version vorgenommen werden, wirken sich nicht auf Produktionsdaten aus. Wenden Sie sich an Ihren Audience Manager Partner Solutions-Kundenbetreuer, wenn Sie an der Betaumgebung interessiert sind.

## Überblick

Die Betaumgebung ist eine exakte Replik der Produktionsumgebung, ohne experimentelle oder nicht veröffentlichte Funktionen. Ihre Anmeldedaten aus der Produktionsumgebung sind in der Beta-Umgebung gültig.

**Zeitplan aktualisieren**

Die Beta-Umgebung wird am Ende jedes Monats während der Nebenzeiten aktualisiert.

**Ausgehender Traffic**

Ausgehender Traffic ist für die Betaumgebung nicht aktiviert.

<!-- 

Added re: AAM-30826.

 -->

## Endpunkte



| Diensleistung | URL/Hostname | Zugang erhalten |
|--- |--- | --- |
| S3 | Wenden Sie sich an Ihren Audience Manager Partner Solutions-Kundenbetreuer oder an den Kundendienst | Wenden Sie sich an Ihren Audience Manager Partner Solutions-Kundenbetreuer oder an den Kundendienst, um einen Amazon S3-Behälter für Ihre Beta-Instanz einzurichten. Erfahren Sie mehr über die [Vorteile von Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Siehe [Zugriff auf den DCS in der Beta-Umgebung](../reference/beta-environment.md#access-dcs-beta-environment). |
| Benutzeroberfläche | `https://bank-beta.demdex.com` | Ihre Anmeldeinformationen für die Produktionsumgebung sind für die Betaumgebung gültig. |
| API | `https://api-beta.demdex.com/...` | Ihre Anmeldeinformationen für die Produktionsumgebung sind für die Betaumgebung gültig. Es wird empfohlen, einen generischen API-Benutzer zu erstellen, [siehe Details](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Zugriff auf den DCS in der Beta-Umgebung {#access-dcs-beta-environment}

1. Führen Sie einen DCS-Aufruf mithilfe des [Befehls](https://curl.haxx.se/docs/manpage.html)curl durch. Curl ist ein Tool zum Übertragen von Daten von oder auf einen Server, das eines von vielen unterstützten Protokollen verwendet.

   Beispiel:

   `curl -v https://dcs-beta.demdex.net/event`

1. Überprüfen Sie, ob Ihre Anforderung vom Beta-DCS bearbeitet wurde, indem Sie in der DCS-Antwort-Kopfzeile nach "Sandbox"suchen.

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