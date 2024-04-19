# DexelCoCScan

## Renommage des fichiers selon numéro de PO
Il faut encore valider le nouveau `def autocorrect_match(match)` (ancien en commentaire)

### Besoin :
- `chmod 777` sur les dossier "ocr-output" & "scan-input"

### ID
- uid=1032(scanncoc) gid=100(users) groups=100(users),101(administrators),1023(http)

### Commandes
- `sudo umount /home/julien/docker/dexelcocscan/inputnfstest`
- `sudo mount -t nfs 192.168.45.29:/volume1/Docker/CoC/scan-input /home/julien/docker/dexelcocscan/inputnfstest`
- `sudo docker volume rm dexelcocscan_ocr-output dexelcocscan_scan-input`

---

Oui, dans le code Python que vous avez fourni, il est configuré pour utiliser soit le polling soit inotify en fonction de la valeur de la variable d'environnement `OCR_USE_POLLING`.

Si `OCR_USE_POLLING` est défini à True, le code utilise `PollingObserver` qui utilise le polling pour détecter les modifications de fichiers. Si `OCR_USE_POLLING` est défini à False ou n'est pas défini, le code utilise `Observer` qui utilise inotify pour détecter les modifications de fichiers.

Voici le morceau de code pertinent :

