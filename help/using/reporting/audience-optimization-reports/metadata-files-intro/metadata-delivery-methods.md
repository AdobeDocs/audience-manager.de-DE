---
description: Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an ein spezielles Amazon S3-Verzeichnis für Ihr Audience Manager-Konto senden. In diesem Abschnitt finden Sie Informationen zu Versand-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen.
seo-description: Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an ein spezielles Amazon S3-Verzeichnis für Ihr Audience Manager-Konto senden. In diesem Abschnitt finden Sie Informationen zu Versand-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen.
seo-title: Bereitstellungsmethoden für Metadatendateien
solution: Audience Manager
title: Bereitstellungsmethoden für Metadatendateien
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Protokolldateien
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 4%

---

# Bereitstellungsmethoden für Metadatendateien{#delivery-methods-for-metadata-files}

Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an ein spezielles [!DNL Amazon S3] -Verzeichnis für Ihr Audience Manager-Konto senden. In diesem Abschnitt finden Sie Informationen zu Versand-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen.

>[!IMPORTANT]
>
> Wenden Sie sich an Ihren Audience Manager-Berater oder an die Kundenunterstützung, um zu beginnen und ein [!DNL Amazon S3]-Verzeichnis für Ihre Metadatendateien einzurichten.

## Syntax und Beispiel für Bereitstellungspfad {#syntax}

Die Daten werden für jeden Kunden in einem [!DNL Amazon S3] -Verzeichnis in einem separaten Namespace gespeichert. Der Dateipfad folgt der unten dargestellten Syntax. Beachten Sie, dass spitze Klammern `<>` einen Variablenplatzhalter angeben. Die anderen Elemente sind Konstanten und ändern sich nicht.

**Syntax:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Beispiel:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br>

Die folgende Tabelle definiert jedes dieser Elemente in einem Dateibereitstellungspfad.


| Dateiparameter | Beschreibung |
---------|----------|
| `.../log_ingestion/` | Dies ist der Anfang des Ordnerspeicherpfads. Sie erhalten den vollständigen Pfad, wenn alles eingerichtet ist. |
| `pid=<AAM ID>` | Dieses Schlüssel-Wert-Paar enthält Ihre Audience Manager-Kunden-ID. |
| `dpid=<d_src>` | Dieses Schlüssel-Wert-Paar enthält die Datenquellen-ID, die bei einem Ereignisaufruf übergeben wird. Die Datenquellen-ID ist der Wert, der alle Inhalte in Ihrer Datei mit den tatsächlichen Daten verknüpft, zu denen sie gehört. </br> Angenommen, Sie haben ein kreatives Element mit der ID 123 und dem Namen &quot;Advertiser Creative A&quot;. Da ein Ereignisaufruf nur die ID übergibt, müssen Sie &quot;Advertiser Creative A&quot;in die Metadatendatei aufnehmen. Die Kampagne und die Kreativinhalte gehören zu einer Datenquelle. Die Datenquellen-ID verbindet diese und ermöglicht es uns, Dateiinhalte exakt mit einer ID zu verknüpfen, die bei einem Ereignisaufruf gesendet wird. Siehe [Wie Ereignisaufruf-IDs Dateinamen, Inhalte und Bereitstellungspfade bestimmen](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Dies ist der Dateiname. Siehe [Benennungskonventionen für Metadatendateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Dateiverarbeitungszeiten und -aktualisierungen {#processing-times}

Metadatendateien werden viermal täglich in regelmäßigen Abständen verarbeitet.

Um Ihre Metadatendatensätze zu aktualisieren, senden Sie einfach eine Datei mit neuen Informationen. Sie müssen nicht jedes Mal vollständige Updates senden.
