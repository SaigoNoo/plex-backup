# plex-backup

> Plex-Backup est un script écrit en bash. Ce script sera chargé de réaliser des backups de PMS et sera capable de les importer !

### Attention

- Sachez que vous aurez besoin des accès root !

- Pour l'instant, ce script ne fonctionne que avec la commande `systemctl` ou service, pas docker (changera avec les prochaines versions)
  
  ## Installation
  
  Pour cela, clonez ce repository sur votre serveur Plex via SSH:
  
  ```bash
  $ git clone https://github.com/4zv4l/plex-backup
  $ cd plex-backup
  $ sudo mv plex-backup /usr/local/bin/ # to use it outside of the cwd
  $ sudo chmod +x /usr/local/bin/plex-backup # give exe permission
  ```
  
  ## Configuration
  
  La configuration ne dépend que de 2 paramètres:
  
  ### Explications
  
  ```
  backupdir         | Répértoire de sauvegarde de Plex, comme un disque dur, ou une emplacement interne
  plexmetadatadir   | Répértoire où sont situés les métadatas (par défaut)
  ```
  
  ### Exemple de syntaxe
  
  `sudo nano /usr/local/bin/plex-backup`
  
  ```bash
  ##### CONFIG #####
  backupdir="/usb/usb1/SYSTEM/backup-plex/"
  plexmetadatadir="/var/lib/plexmediaserver/Library/Application Support/Plex Media Server"
  ```
  
  ## Utilisation
  
  Tapez `plex-backup` dans votre terminal... C'est tout !
  
  ### Informations
  
  Les backups se font dans un dossier avec la structure suivante:
  
  ```textile
  |- BackupFolder        # Dossier de la backup
   |- 2020               # Année
   |  |- 08              # Mois
   |  |  |- 13           # Jour
   |  |  |  |- 12h00     # Heure et minute de la backup
  ```
