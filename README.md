# plex-backup
*Plex-Backup est un script écrit en bash. Ce script sera chargé de réaliser des backups de PMS et sera capable de les importer !*

### Attention
- Sachez que vous aurez besoin des accès root !
- Pour l'instant, ce script ne fonctionne que avec la commande systemctl ou service, pas docker (changera avec les prochaines versions)

## Installation
Pour cela, clonez ce repository sur votre serveur Plex via SSH:

```
git clone https://github.com/gigidsss/plex-backup
cd plex-backup
sudo mv plex-backup /usr/local/bin/
sudo chmod a+x /usr/local/bin/plex-backup
sudo chmod +x /usr/local/bin/plex-backup
```

## Configuration
La configuration ne dépend que de 2 paramètres:

### Explications
```
backupdir         | Répértoire de sauvegarde de Plex, comme un disque dur, ou une emplacement interne
plexmetadatadir   | Répértoire où sont situés les métadatas (par défaut)
```

### Exemple de syntaxe
``sudo nano /usr/local/bin/plex-backup``
```
##### CONFIG #####
backupdir=$(echo '/usb/usb1/SYSTEM/backup-plex/')
plexmetadatadir=$(echo "/var/lib/plexmediaserver/Library/Application Support/Plex Media Server")
##### PAS TOUCHER #####
```

## Utilisation
Tapez plex-backup dans votre terminal... C'est tout !

### Informations
Les backups se font dans un dossier avec la structure suivante:

```
|- BackupFolder          # Dossier de la backup
   |- 2020               # Année
   |  |- 08              # Mois
   |  |  |- 13           # Jour
   |  |  |  |- 12h00     # Heure et minute de la backup
```
