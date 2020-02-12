---
description: Als Option können Sie Datendateien mit PGP-Verschlüsselung verschlüsseln, wenn Sie sie an Audience Manager senden.
seo-description: Als Option können Sie Datendateien mit PGP-Verschlüsselung verschlüsseln, wenn Sie sie an Audience Manager senden.
seo-title: Datei-PGP-Verschlüsselung für Inbound-Datentypen
solution: Audience Manager
title: Datei-PGP-Verschlüsselung für Inbound-Datentypen
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
translation-type: tm+mt
source-git-commit: 8d2d841f8e94fd67c2165eb280b85ab18001d77e

---


# Datei-PGP-Verschlüsselung für Inbound-Datentypen{#file-pgp-encryption-for-inbound-data-types}

Als Option können Sie Datendateien mit [!DNL PGP] Verschlüsselung verschlüsseln, wenn sie an Audience Manager gesendet werden.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>Wir unterstützen derzeit keine Verschlüsselung und Komprimierung in derselben eingehenden Datendatei. Sie können Ihre eingehenden Dateien entweder verschlüsseln oder [komprimieren](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) .
>
> Beachten Sie jedoch, dass PGP-Verschlüsselung eine integrierte Komprimierung beinhaltet.

Gehen Sie wie folgt vor, um eingehende Datendateien zu verschlüsseln.

1. Laden Sie den öffentlichen [Audience Manager-Schlüssel](./assets/adobe_pgp.pub)herunter.
1. Importieren Sie den öffentlichen Schlüssel in Ihren vertrauenswürdigen Store.

   Wenn Sie beispielsweise [!DNL GPG]Folgendes verwenden, könnte der Befehl wie folgt aussehen:

   `gpg --import adobe_pgp.pub`

1. Überprüfen Sie, ob der Schlüssel korrekt importiert wurde, indem Sie den folgenden Befehl ausführen:

   `gpg --list-keys`

   Es sollte eine Meldung wie die folgende angezeigt werden:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

1. Verschlüsseln Sie die eingehenden Daten mit dem folgenden Befehl:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Alle verschlüsselten Daten müssen als Dateierweiterung verwendet `.pgp` oder `.gpg` verwendet werden (z.B. `ftp_dpm_100_123456789.sync.pgp` oder `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager unterstützt nur den [!DNL Advanced Encryption Standard (AES)] Datenverschlüsselungsalgorithmus. Audience Manager unterstützt alle wichtigen Größen.
