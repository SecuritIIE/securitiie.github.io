---
title: "Outils"
#tags: ["Outils", "Tools"]
type: "page"
image: "/images/lorem-ipsum/quick-fox.png"
showTableOfContents: false
---

- [CyberChef](#cyberchef)
- [RustScan](#rustscan)
- [gobuster](#gobuster)
- [nikto](#nikto)
- [linPEAS / winPEAS](#linpeas-winpeas)
- [BruteForce](#bruteforce)

## [CyberChef](https://securitiie.iiens.net/cyberchef/){#cyberchef}

CyberChef est une interface web qui réunit un ensemble d'outils facilement utilisables.

---

## [RustScan](https://github.com/RustScan/RustScan){#rustscan}

Le scanner de port moderne.

### :sparkles: Fonctionnalités

 - Scanne 65k ports en 3 secondes.
 - Moteur de script.
 - Apprentissage adaptatif. RustScan s'améliore au fur et à mesure que vous l'utilisez. Il n'y a pas d'apprentissage automatique, juste des mathématiques de base.
 - IPv6, CIDR, entrée de fichiers et plus encore.
 - Transfert automatique des ports dans Nmap.

```
rustscan -a 10.10.x.x -- -A -sC
```

![](/cli/rustscan.gif)


---

## [gobuster](https://github.com/OJ/gobuster){#gobuster}

Pour brute-force et énumérer les paths de sites webs.

### :sparkles: Fonctionnalités

Gobuster est un outil utilisé pour faire du brute-force sur :

 - Les URI (répertoires et fichiers) dans les sites web.
 - Les sous-domaines DNS (avec prise en charge de wildcard).
 - Les noms d'hôtes virtuels sur les serveurs web cibles.
 - Les buckets Amazon S3 ouverts

```
gobuster dir -u http://vulnsite.com/ -w /opt/gobuster-medium.txt
gobuster dir -u https://mysite.com/path/to/folder -c 'session=123456' -t 50 -w common-files.txt -x .php,.html
```

```
gobuster dir -u https://buffered.io -w ~/wordlists/shortlist.txt

===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Mode         : dir
[+] Url/Domain   : https://buffered.io/
[+] Threads      : 10
[+] Wordlist     : /home/oj/wordlists/shortlist.txt
[+] Status codes : 200,204,301,302,307,401,403
[+] User Agent   : gobuster/3.1.0
[+] Timeout      : 10s
===============================================================
2019/06/21 11:49:43 Starting gobuster
===============================================================
/categories (Status: 301)
/contact (Status: 301)
/posts (Status: 301)
/index (Status: 200)
===============================================================
2019/06/21 11:49:44 Finished
===============================================================
```

---

## [nikto](https://github.com/sullo/nikto){#nikto}

Pour scanner les vulnérabilités des applis Web.

```
nikto -h http://10.10.x.x
```

---

## [linPEAS / winPEAS](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/){#linpeas-winpeas}

*PEASS - Privilege Escalation Awesome Script SUITE*

Une fois que vous êtes un utilisateur avec un terminal sur la machine, un script qui analyse absolument tous les vecteurs d'attaque pour devenir root.

![](/cli/linpeas.png)

```sh
#Output to file
./linpeas.sh -a > /dev/shm/linpeas.txt #Victim
less -r /dev/shm/linpeas.txt #Read with colors
```
---

## [BruteForce](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/){#bruteforce}

Pour bruteforce des hash de mot de passe à toute vitesse (écrit en Go donc beaucoup plus rapide que les scripts Python)

```sh
./BruteForce --type sha256 --value 88d4266fd4e6338d13b845fcf289579d209c897823b9217da3e161936f031589
Start brute-forcing (sha256)...
Found: abc in 1 s
```

Fonctionnalités :
- Supporte les hashs SHA1, SHA256, SHA512, MD5 et bcrypt 
- Liste de caractères personnalisée
- Dictionnaire de mots de passe personnalisé
- Utilisation du GPU
