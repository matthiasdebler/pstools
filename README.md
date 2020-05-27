# pstools 
Quelle: https://www.ip-insider.de/pstools-zwoelf-kommandozeilen-helferlein-fuer-den-administrator-a-105115/

Tool-Übersicht
Derzeit sind in den PsTools zwölf Kommandozeilenprogramme enthalten. Im Folgenden werden diese mit Ihrem Einsatzzweck jeweils kurz vorgestellt. Allen gemein ist die mögliche Angabe eines Computernamens und einer Benutzername-Kennwort-Kombination, zur Ausführung der Aktion auf einem beliebigen Rechner und/oder unter einem anderen Benutzerkontext. Gerade diese Option bieten die meisten standardmäßig vorhandenen Tools nicht. Zu beachten ist jedoch, dass die Anmeldeinformationen hier im Klartext über das Netzwerk geschickt werden.

PsExec
Mit PsExec können auf beliebigen Rechnern im Netzwerk Prozesse gestartet werden. Dabei ist es nicht erforderlich, auf den Computern eine spezielle Client-Software zu installieren. Neben den notwendigen Berechtigungen ist es lediglich erforderlich, dass die administrative Freigabe admin$ auf dem Remotesystem existiert und die Ports für die Datei- und Druckerfreigabe in der Firewall geöffnet sind.

Hier ein Beispiel, mit dem das Programm test.exe auf einer Remotemaschine ausführt wird:


psexec \\computer -u User -p Kennwort -c test.exe

Wird statt einem bestimmten Computernamen \\* angegeben, wird die Aktion auf allen Computern der Domäne ausgeführt. Die Antworten von Kommandozeilenprogrammen werden lokal ausgegeben.

PsFile
PsFile zeigt eine Liste aller Dateien, die andere Computer auf der lokalen Maschine geöffnet haben. Auch PsFile kann diese Information von einer Remotemaschine auslesen.

PsGetSid
Werden Probleme vermutet, die durch zwei identische SIDs hervorgerufen werden, kann PsGetSid helfen. Es gibt die SID des Computers aus und hilft so bei der Fehlersuche.

PsInfo
PsInfo liefert eine Liste der wichtigsten Systeminformationen. Dazu gehören Betriebssystemversion, Installationsdatum, ob es eine Test-Version ist und wann diese ausläuft sowie Hardwareinformationen. Über weitere Parameter können ebenso die installierten Hotfixes (-h), die installierten Anwendungen (-s) und Laufwerksinformationen (-d) ausgegeben werden. Der Aufruf könnte wie folgt aussehen:

Psinfo \\computer -h -s -d

PsKill
Blockiert ein Prozess oder soll ein unerwünschter Prozess beendet werden, hilft PsKill. Nach Angabe der Prozess-ID oder des Prozessnamens wird der betroffene Prozess beendet.

PsList
PsList gibt statistische Informationen zu den laufenden Prozessen in verschiedenen Detailstufen aus. Es ist auch eine Anzeige des Prozessbaums (-t) vorgesehen, über die ersichtlich wird, von welchem Prozess aus die Prozesse gestartet wurden. Die Anzeige der Informationen lässt sich auch auf einen bestimmten Prozess beschränken.

PsLoggedOn
Mit PsLoggedOn wird eine Liste aller Benutzer geliefert, die entweder direkt auf dem lokalen Computer angemeldet sind, oder über eine Remotemaschine. Sofern vorhanden, wird auch der Anmeldezeitpunkt mit ausgegeben.

Außerdem kann durch Angabe eines bestimmten Benutzernamens in der gesamten Netzwerkumgebung gesucht werden, ob und wo ein bestimmter Benutzer angemeldet ist.

PsLogList
PsLogList gibt ohne weitere Parameter den Inhalt des System-Eventlogs aus. Ein Wechsel des Eventlogs ist ebenso möglich wie die Einschränkung auf einen bestimmten Zeitraum.

PsPasswd
Mit PsPasswd kann das Kennwort eines Benutzers geändert werden. Das Tool eignet sich beispielsweise dazu, das Kennwort des lokalen Administrators regelmäßig auf allen Maschinen zu ändern.

PsService
Neben der Ausgabe der Dienste samt ihrem derzeitigen Status kann PsService auch gezielt Dienste starten, stoppen, anhalten und fortsetzen. Auch die Ausgabe von Abhängigkeiten zwischen Diensten ist vorgesehen.

PsShutdown
PsShutdown kann den Computer herunterfahren, neu starten, den Ruhezustand aktivieren, den aktuellen Benutzer abmelden und die Konsole sperren.

PsSuspend
Belegt ein Prozess zu viele Systemressourcen und behindert so einen anderen Prozess bei der Erledigung einer wichtigen Aufgabe, kann er mit PsSuspend kurzzeitig angehalten und zu einem späteren Zeitpunkt fortgeführt werden.
