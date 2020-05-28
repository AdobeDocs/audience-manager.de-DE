---
description: Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an einen Amazon S3-Ordner für Ihr Audience Manager-Konto senden. Informationen zu Versand-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen finden Sie in diesem Abschnitt.
seo-description: Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an einen Amazon S3-Ordner für Ihr Audience Manager-Konto senden. Informationen zu Versand-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen finden Sie in diesem Abschnitt.
seo-title: Versand-Methoden für Metadatendateien
solution: Audience Manager
title: Versand-Methoden für Metadatendateien
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: 62147fc719a59d2b2c7b444bce853334b03816c6
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---


# Versand-Methoden für Metadatendateien{#delivery-methods-for-metadata-files}

Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an einen speziellen [!DNL Amazon S3] Ordner für Ihr Audience Manager-Konto senden. Informationen zu Versand-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen finden Sie in diesem Abschnitt.

>[!IMPORTANT]
>
> Wenden Sie sich an Ihren Audience Manager-Berater oder an den Kundendienst, um einen [!DNL Amazon S3] Ordner für Ihre Metadatendateien einzurichten.

## Versand-Pfadsyntax und Beispiel {#syntax}

Die Daten werden in einem separaten Namensraum für jeden Kunden in einem [!DNL Amazon S3] Verzeichnis gespeichert. Der Dateipfad folgt der unten stehenden Syntax. Beachten Sie, dass spitze Klammern einen variablen Platzhalter `<>` angeben. Die anderen Elemente sind Konstanten und bleiben unverändert.

**Syntax:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Beispiel:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br> 

In der folgenden Tabelle werden diese Elemente in einem Dateipfad definiert.


| Dateiparameter | Beschreibung |
---------|----------|
| `.../log_ingestion/` | Dies ist der Beginn des Ordnerpfads für die Datenspeicherung. Sie erhalten den vollständigen Pfad, wenn alles eingerichtet ist. |
| `pid=<AAM ID>` | Dieses Schlüssel-Wert-Paar enthält Ihre Audience Manager-Kunden-ID. |
| `dpid=<d_src>` | Dieses Schlüssel-Wert-Paar enthält die Datenquellen-ID, die bei einem Ereignis-Aufruf übergeben wird. Die Datenquellen-ID ist der Wert, der den gesamten Inhalt Ihrer Datei mit den tatsächlichen Daten verknüpft, zu denen sie gehört. </br> Angenommen, Sie haben ein kreatives Element mit der ID 123 und dem Namen &quot;Werbetreibende Kreative A&quot;. Da ein Ereignis-Aufruf nur in der ID weitergegeben wird, müssen Sie &quot;Werbetreibende Kreative A&quot;in die Metadatendatei aufnehmen. Kampagne und Kreativelemente gehören zu einer Datenquelle. Die Datenquellen-ID verbindet diese und ermöglicht es uns, Dateiinhalte exakt mit einer ID zu verknüpfen, die bei einem Ereignis-Aufruf gesendet wird. Siehe [Bestimmen von Dateinamen, Inhalten und Versand-Pfaden durch Ereignis-Aufruf-IDs](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Dies ist der Dateiname. Siehe [Benennungskonventionen für Metadatendateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Dateiverarbeitungszeiten und -aktualisierungen {#processing-times}

Metadaten-Dateien werden in regelmäßigen Abständen viermal am Tag verarbeitet.

Um Ihre Metadaten-Datensätze zu aktualisieren, senden Sie einfach eine Datei mit neuen Informationen. Sie müssen keine vollständigen Updates jedes Mal senden.
