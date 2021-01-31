# AWX für den Einsatz ohne Internetzugang vorbereiten

Den passenden Artikel gibt es [hier](https://it-baschtler.de/2021/01/31/awx-air-gapped---mit-eigenem-image-und-ohne-internetzugang-in-die-produktionsumgebung/)


Die Datei `test_inventory` beinhaltet beispielhaft Parameter mit denen sich AWX auf einem lokalen K3s cluster bauen und installieren lässt. Die URL awx.example.org ist über die /etc/hosts gesetzt.

ACHTUNG: [PR9079](https://github.com/ansible/awx/pull/9079) ist voraussetzung dafür, dass das build mit buildah funktioniert.

## Installation

Die Installation kann zum Beispiel wie folgt aufgerufen werden. 

`ansible-playbook -i test_inventory install.yml -e  docker_registry_password=<Passwort>`

Wichtig ist, dass die `install.yml` aus dem Ansible Projekt gefunden wird und selbstverständlich auch die Rollen aus dem AWX Installer.

## Zum Thema Registry

Ich habe in meinem K3s eine lokale Harbor registry laufen. Das ganze funktioniert aber natürlich auch entsprechend mit jedem anderen registry.