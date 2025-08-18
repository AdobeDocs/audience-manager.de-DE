---
description: Formatieren Sie den Inhalt Ihrer Audience Optimization-Metadatendatei gemäß diesen Spezifikationen.
seo-description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-title: Content Format for Metadata Files
solution: Audience Manager
title: Inhaltsformat für Metadatendateien
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: Log Files
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 1%

---

# Inhaltsformat für Metadatendateien{#content-format-for-metadata-files}

Formatieren Sie den Inhalt Ihrer Audience Optimization-Metadatendatei gemäß diesen Spezifikationen.

## Syntax {#syntax}

Die folgende Syntax definiert die Struktur von wohlgeformten Inhalten in einer Metadatendatei. Hinweis: *Kursiv* gibt einen Variablenplatzhalter an.

**Syntax:** *content ID* | *name* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

Die dritte Spalte **-1** ist technisch gesehen die übergeordnete ID, ein älteres Feld. Der Wert sollte immer als **-1** festgelegt werden.

>[!NOTE]
>
>Beachten Sie, dass pro Dimension eine Metadatendatei erforderlich ist, sodass im Bucket mehrere Metadatendateien erwartet werden. Die Dimensionen werden im Artikel [Benennungskonventionen für Metadatendateien“ ](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Separate Dateieinträge mit ^a (Control-A oder ASCII 001)**

Verwenden Sie `^a` (Control-A oder ASCII 001), um Inhalte in Ihren Metadatendateien zu trennen. Da es sich hierbei um nicht druckbare Zeichen handelt, zeigt das obige Syntaxbeispiel einen senkrechten Strich (“|„) nur zu Anzeigezwecken.

Bei Bedarf können Sie die Beispieldatei herunterladen - [20181105_0_1](assets/20181105_0_1.zip). Entpacken Sie sie und bearbeiten Sie sie in dem Editor Ihrer Wahl und passen Sie sie entsprechend Ihren tatsächlichen Metadateninhalten an, da sie bereits das erforderliche Trennzeichen enthält.

>[!IMPORTANT]
>
>Fügen Sie keine Kopfzeilen zu Metadatendateien hinzu.

## Beispiele {#examples}

Sehen wir uns an, wie Sie Inhalte in einer Metadatendatei strukturieren würden. Ein Teil dieser Struktur hängt von der Dimension ab. Die Dimensionen werden im Artikel [Benennungskonventionen für Metadatendateien“ ](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

In diesem Beispiel lautet der Dateiname 20180921_0_1 und die drei Spalten in der Datei sind: Kampagnen-ID, Name und übergeordnete ID.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Creative**

In diesem Beispiel lautet der Dateiname 20180827_0_2. Die drei Spalten in der Datei sind: Creative-ID, Name und übergeordnete ID.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Site**

In diesem Beispiel lautet der Dateiname 20180921_0_5 und die drei Spalten in der Datei sind: Site-ID, Name und übergeordnete ID.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
