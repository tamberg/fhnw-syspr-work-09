# System-Programmierung
## Hands-on zu Lektion 9
Für Slides und Code Beispiele, siehe [Lektion 9](../../../fhnw-syspr/blob/master/09/README.md)

> *Achtung: Arbeiten Sie nicht direkt auf diesem Repository.*<br/>
> *[Prüfen Sie die vorhandenen Forks, um das Repository für Ihre Klasse zu finden.](../../network/members)*

### a) UNIX Domain Sockets, 30'
* Analysieren Sie diese Socket Beispiele bestehend aus:
* Header [us_xfr.h](http://man7.org/tlpi/code/online/book/sockets/us_xfr.h.html)<sup>TLPI</sup>, Server [us_xfr_sv.c](http://man7.org/tlpi/code/online/book/sockets/us_xfr_sv.c.html)<sup>TLPI</sup>, Client [us_xfr_cl.c](http://man7.org/tlpi/code/online/book/sockets/us_xfr_cl.c.html)<sup>TLPI</sup>.
* Header [ud_ucase.h](http://man7.org/tlpi/code/online/book/sockets/ud_ucase.h.html)<sup>TLPI</sup>, Server [ud_ucase_sv.c](http://man7.org/tlpi/code/online/book/sockets/ud_ucase_sv.c.html)<sup>TLPI</sup>, Client [ud_ucase_cl.c](http://man7.org/tlpi/code/online/book/sockets/ud_ucase_cl.c.html)<sup>TLPI</sup>.
* Builden Sie die Programme, und lassen Sie sie laufen.
* Zeichnen Sie [Sequenzdiagramme](http://websequencediagrams.com) mit User, Client, Server, das den Ablauf / übertragene Daten zeigt.

### b) Internet Domain Sockets, 30'
* Analysieren Sie dieses Socket Beispiel bestehend aus:
* Header [i6d_ucase.h](http://man7.org/tlpi/code/online/book/sockets/i6d_ucase.h.html)<sup>TLPI</sup>, Server [i6d_ucase_sv.c](http://man7.org/tlpi/code/online/book/sockets/i6d_ucase_sv.c.html)<sup>TLPI</sup>, Client [i6d_ucase_cl.c](http://man7.org/tlpi/code/online/book/sockets/i6d_ucase_cl.c.html)<sup>TLPI</sup>.
* Builden Sie die Programme, und lassen Sie sie laufen:<pre>
    $ ./i6d_ucase_sv &
    $ ./i6d_ucase_cl ::1 hello</pre>

### c) Web Client, 1h
* Schreiben Sie einen Web Client my_http_client.c, der folgenden HTTP Request an den Host tmb.gr, Port 80 sendet, die Antwort liest, und auf stdout ausgibt:<pre>
    "GET /syspr HTTP/1.1\r\n"
    "Host: tmb.gr\r\n"
    "\r\n"</pre>
* Hinweis: HTTP nutzt TCP als Transport-Protokoll.
* Länge der Antwort ist im Content-Length Header.

### d) Web Server, 1h
* Schreiben Sie einen Web Server my_http_server.c, der einkommende HTTP Requests auf Port 8080 liest und folgende Antwort zum Client / Browser sendet:<pre>
    "HTTP/1.1 200 OK\r\n"
    "Connection: close\r\n"
    "Content-Length: 5\r\n"
    "\r\n"
    "hello"</pre>

### Abgabe (optional)
* Lokale Änderungen [committen und pushen](#git).
* GitHub [Issue erstellen](../../issues/new) mit "Bitte um Review, @tamberg".
* Offene Fragen ausformulieren, was geht nicht, was haben Sie versucht.
* GitHub mailt mir (@tamberg) automatisch, ich versuche in weniger als 24h zu antworten :)

## Tools
### Git
Auf Ihrem Computer
* Zu Beginn jeder Lektion wird ein Hands-on Repository Link freigeschaltet
* Nachdem Sie das "Assessment" annehmen, bekommen Sie per Email ein Repository
* Die REPO_URL enthält Ihren GitHub Account USER_NAME und Ihre Klasse 3ia oder 3ib, z.B.<br/>
            https://github.com/fhnw-syspr-3ia/fhnw-syspr-work-09-tamberg

Auf dem Raspberry Pi
* Repository klonen<pre>
    $ cd ~
    $ git clone REPO_URL</pre>
* Neue Datei kreieren<pre>
    $ git add FILE</pre>
* Änderungen committen<pre>
    $ git commit FILE -m "Fixed all bugs"</pre>
* Änderungen hochladen<pre>
    $ git push</pre>

### Nano
Auf dem Raspberry Pi
* Neue oder bestehende Datei öffnen mit $ nano FILE
* Editieren (Achtung, nano hat kein Undo)
* Speichern mit `CRTL-X` `Y` `RETURN`

### SSH
Auf Ihrem Computer
* Terminal öffnen (Mac) oder `WINDOWS` `R` cmd `RETURN` (Windows)
* SSH Session starten mit<pre>
    $ ssh pi@raspberrypi.local</pre>

## Support
- [FHNW Syspr Slack](https://fhnw-syspr.slack.com/)
