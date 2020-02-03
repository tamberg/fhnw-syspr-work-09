# System-Programmierung
## Hands-on zu Lektion 9
Für Slides und Code Beispiele, siehe [Lektion 9](../../../fhnw-syspr/blob/master/09/README.md)

> *Achtung: Arbeiten Sie nicht direkt auf diesem Repository.*<br/>
> *[Prüfen Sie die vorhandenen Forks, um das Repository für Ihre Klasse zu finden.](../../network/members)*

### a) UNIX Domain Sockets, 15'
* Analysieren Sie diese Socket Beispiele bestehend aus:
* Header [us_xfr.h](http://man7.org/tlpi/code/online/book/sockets/us_xfr.h.html)<sup>TLPI</sup>, Server [us_xfr_sv.c](http://man7.org/tlpi/code/online/book/sockets/us_xfr_sv.c.html)<sup>TLPI</sup>, Client [us_xfr_cl.c](http://man7.org/tlpi/code/online/book/sockets/us_xfr_cl.c.html)<sup>TLPI</sup>.
* Header [ud_ucase.h](http://man7.org/tlpi/code/online/book/sockets/ud_ucase.h.html)<sup>TLPI</sup>, Server [ud_ucase_sv.c](http://man7.org/tlpi/code/online/book/sockets/ud_ucase_sv.c.html)<sup>TLPI</sup>, Client [ud_ucase_cl.c](http://man7.org/tlpi/code/online/book/sockets/ud_ucase_cl.c.html)<sup>TLPI</sup>.
* Builden Sie die Programme, und lassen Sie sie laufen.
* Zeichnen Sie [Sequenzdiagramme](http://websequencediagrams.com) mit User, Client, Server, das den Ablauf / übertragene Daten zeigt.

### b) Internet Domain Sockets, 15'
* Analysieren Sie dieses Socket Beispiel bestehend aus:
* Header [i6d_ucase.h](http://man7.org/tlpi/code/online/book/sockets/i6d_ucase.h.html)<sup>TLPI</sup>, Server [i6d_ucase_sv.c](http://man7.org/tlpi/code/online/book/sockets/i6d_ucase_sv.c.html)<sup>TLPI</sup>, Client [i6d_ucase_cl.c](http://man7.org/tlpi/code/online/book/sockets/i6d_ucase_cl.c.html)<sup>TLPI</sup>.
* Builden Sie die Programme, und lassen Sie sie laufen:<pre>
    $ ./i6d_ucase_sv &
    $ ./i6d_ucase_cl ::1 hello</pre>

### c) Web Client, 1h
* Schreiben Sie einen Web Client _my_http_client.c_, der folgenden HTTP Request an den Host _tmb.gr_, Port _80_ sendet, die Antwort liest, und auf _stdout_ ausgibt:<pre>
    "GET /syspr HTTP/1.1\r\n"
    "Host: tmb.gr\r\n"
    "\r\n"</pre>
* Hinweis: HTTP nutzt TCP als Transport-Protokoll.
* Länge der Antwort ist im _Content-Length_ Header.

### d) Web Server, 1h
* Schreiben Sie einen Web Server _my_http_server.c_, der einkommende HTTP Requests auf Port _8080_ liest und folgende Antwort zum Client / Browser sendet:<pre>
    "HTTP/1.1 200 OK\r\n"
    "Connection: close\r\n"
    "Content-Length: 5\r\n"
    "\r\n"
    "hello"</pre>
