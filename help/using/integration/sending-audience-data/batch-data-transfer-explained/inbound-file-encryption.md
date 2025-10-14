---
description: Optional können Sie Datendateien beim Senden an Audience Manager mit PGP-Verschlüsselung verschlüsseln.
seo-description: As an option, you can encrypt data files with PGP encryption when sending them to Audience Manager.
seo-title: File PGP Encryption for Inbound Data Types
solution: Audience Manager
title: Datei-PGP-Verschlüsselung für eingehende Datentypen
uuid: 89caace1-0259-48fc-865b-d525ec7822f7
feature: Inbound Data Transfers
exl-id: 5f97a326-4840-4350-bbe8-bc8ce32b0a2e
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 0%

---

# Datei-PGP-Verschlüsselung für eingehende Datentypen{#file-pgp-encryption-for-inbound-data-types}

Datendateien können beim Senden an Audience Manager mit [!DNL PGP] verschlüsselt werden.

<!-- c_encryption.xml -->

>[!IMPORTANT]
>
>[!DNL PGP] Verschlüsselung umfasst die Dateikomprimierung. Stellen Sie beim Senden [!DNL PGP] verschlüsselten eingehenden Dateien sicher, dass Sie sie nicht [komprimieren](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md) mit gzip (`.gz`).
>
>[!DNL PGP] verschlüsselte eingehende Dateien, die ebenfalls [komprimiert) &#x200B;](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md), sind in Audience Manager ungültig.

Gehen Sie wie folgt vor, um eingehende Datendateien zu verschlüsseln.

1. Öffentlichen Schlüssel [Audience Manager herunterladen](./assets/adobe_pgp.pub).
2. Importieren Sie den öffentlichen Schlüssel in Ihren vertrauenswürdigen Store.

   Wenn Sie beispielsweise [!DNL GPG] verwenden, könnte der Befehl in etwa wie folgt aussehen:

   `gpg --import adobe_pgp.pub`

3. Überprüfen Sie mithilfe des folgenden Befehls, ob der Schlüssel korrekt importiert wurde:

   `gpg --list-keys`

   Es sollte eine Meldung ähnlich der folgenden angezeigt werden:

   ```
   pub   4096R/8496CE32 2013-11-01
   uid                  Adobe AudienceManager
   sub   4096R/E3F2A363 2013-11-01
   ```

4. Verschlüsseln Sie die eingehenden Daten mit dem folgenden Befehl:

   `gpg --recipient "Adobe AudienceManager" --cipher-algo AES --output $output.gpg --encrypt $inbound`

   Alle verschlüsselten Daten müssen `.pgp` oder `.gpg` als Dateierweiterung verwenden (z.B. `ftp_dpm_100_123456789.sync.pgp` oder `ftp_dpm_100_123456789.overwrite.gpg`).

   >[!NOTE]
   >
   >Audience Manager unterstützt nur den [!DNL Advanced Encryption Standard (AES)] Datenverschlüsselungsalgorithmus. Audience Manager unterstützt jede Schlüsselgröße.
