---
description: Als Option können Sie Datendateien mit der PGP-Verschlüsselung verschlüsseln, wenn Sie sie an Audience Manager senden.
seo-description: Als Option können Sie Datendateien mit der PGP-Verschlüsselung verschlüsseln, wenn Sie sie an Audience Manager senden.
seo-title: Datei-PGP-Verschlüsselung für Inbound-Datentypen
solution: Audience Manager
title: Datei-PGP-Verschlüsselung für Inbound-Datentypen
uuid: 89 caace 1-0259-48 fc -665 b-d 525 ec 7822 f 7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File PGP Encryption for Inbound Data Types{#file-pgp-encryption-for-inbound-data-types}

As an option, you can encrypt data files with [!DNL PGP] encryption when sending them to Audience Manager.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>Verschlüsselung und Komprimierung werden derzeit nicht in derselben Inbound-Datendatei unterstützt. You can select to either encrypt or [compress](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) your inbound files.

Gehen Sie wie unten beschrieben vor, um eingehende Datendateien zu verschlüsseln.

1. Download the [Audience Manager public key](./assets/adobe_pgp.pub).
1. Importieren Sie den öffentlichen Schlüssel in Ihren vertrauenswürdigen Store.

   For example, if you use [!DNL GPG], the command could be similar to the following:

   `gpg --import adobe_pgp.pub`

1. Überprüfen Sie, ob der Schlüssel korrekt importiert wurde, indem Sie den folgenden Befehl ausführen:

   `gpg --list-keys`

   Es sollte eine Meldung ähnlich dem Folgenden angezeigt werden:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. Verschlüsseln Sie die eingehenden Daten mithilfe des folgenden Befehls:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   All encrypted data must use `.pgp` or `.gpg` as the file extension (e.g. `ftp_dpm_100_123456789.sync.pgp` or `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager supports only the [!DNL Advanced Encryption Standard (AES)] data-encryption algorithm. Audience Manager unterstützt alle Schlüsselgrößen.