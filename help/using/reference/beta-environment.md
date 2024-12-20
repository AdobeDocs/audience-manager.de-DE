---
description: Die Beta-Umgebung dient zum Testen Ihrer Audience Manager-Implementierung. In der Beta-Version vorgenommene Änderungen wirken sich nicht auf die Produktionsdaten aus. Wenden Sie sich an den Audience Manager Partner Solutions-Support, wenn Sie die Beta-Umgebung verwenden möchten.
keywords: Sandbox
seo-description: The beta environment is for testing your Audience Manager implementation. Changes made in beta do not affect production data. Contact your Audience Manager Partner Solutions representative if you're interested in using the beta environment.
seo-title: Beta Environment
solution: Audience Manager
title: Beta-Umgebung
uuid: de4a1a46-cfa4-4f64-8569-48a7650fd8cf
feature: Reference
exl-id: a6a5e1c2-29a2-40bf-972c-87fb8716a394
source-git-commit: fce39268f1c8c4dd1b7ff21b61a9830a20fa0b4e
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# Beta-Umgebung {#beta-environment}

Die Beta-Umgebung dient zum Testen Ihrer Audience Manager-Implementierung. In der Beta-Version vorgenommene Änderungen wirken sich nicht auf die Produktionsdaten aus. Wenden Sie sich an den Audience Manager Partner Solutions-Support, wenn Sie die Beta-Umgebung verwenden möchten.

## Überblick

Die Funktionalität in der Beta-Umgebung ist eine exakte Replikation der Produktionsumgebung, ohne experimentelle oder unveröffentlichte Funktionen. Ihre Anmeldedaten aus der Produktionsumgebung sind in der Beta-Umgebung gültig.

**Zeitplan aktualisieren**

Die Beta-Umgebung wird am Ende jedes Monats außerhalb der Spitzenzeiten aktualisiert.

>[!IMPORTANT]
>
>Beachten Sie, dass Ihre Kundendaten [Signale, Eigenschaften und Segmente](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html?lang=en) nicht zwischen der Produktions- und der Beta-Umgebung synchronisiert werden.

## Inbound-Traffic

Die Beta-Umgebung unterstützt eingehenden Traffic nur für die Validierung von Dateinamen und Inhaltssyntax. Da in der Beta-Umgebung keine ID-Zuordnung stattfindet, sehen Kunden keine Segmentpopulationen.

Daher meldet die [!UICONTROL Onboarding Status] immer [!UICONTROL No matching AAM ID] bei der Dateiaufnahme in der Beta-Umgebung.

Wir empfehlen allen Kunden, eingehende Tests in ihrer Produktionsumgebung durchzuführen.

## Ausgehender Traffic

Ausgehender Traffic ist für die Beta-Umgebung nicht aktiviert.

## Endpunkte

| Service | URL/Hostname | So erhalten Sie Zugriff |
|--- |--- | --- |
| S3 | Wenden Sie sich an den Audience Manager Partner Solutions-Support oder an die Kundenunterstützung | Wenden Sie sich an Ihren Audience Manager Partner Solutions-Support-Mitarbeiter oder an die Kundenunterstützung, um einen Amazon S3-Bucket für Ihre Beta-Instanz einzurichten. Erfahren Sie mehr über die [Vorteile der Verwendung von Amazon S3](../reference/amazon-s3.md). |
| DCS | `https://dcs-beta.demdex.net/...` | Siehe [Zugriff auf den DCS in der Beta-Umgebung](../reference/beta-environment.md#access-dcs-beta-environment). |
| Benutzeroberfläche | `https://bank-beta.demdex.com` | Die Anmeldeinformationen für die Produktionsumgebung sind für die Beta-Umgebung gültig. |
| API | `https://api-beta.demdex.com/...` | Die Anmeldeinformationen für die Produktionsumgebung sind für die Beta-Umgebung gültig. Es wird empfohlen, einen generischen API-Benutzer zu erstellen [siehe Details](../api/rest-api-main/aam-api-getting-started.md#requirements). |

## Zugreifen auf den DCS in der Beta-Umgebung {#access-dcs-beta-environment}

1. Führen Sie einen DCS-Aufruf mit dem curl-[ aus](https://curl.haxx.se/docs/manpage.html). cURL ist ein Tool zum Übertragen von Daten von oder auf einen Server mithilfe eines von vielen unterstützten Protokollen.

   Beispiel:

   `curl -v https://dcs-beta.demdex.net/event`

1. Stellen Sie sicher, dass Ihre Anfrage vom Beta-DCS verarbeitet wurde, indem Sie im DCS-Antwort-Header nach „Sandbox“ suchen.

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
