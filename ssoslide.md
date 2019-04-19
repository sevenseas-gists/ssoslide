#Einer für alle(s)! Das SSO der WWU
SSO oder auch **S**ingle **S**ign **O**n (dt. Einmaliges Anmelden) ist eine Art der
Anmeldung bei der man sich nur einmal für alle verbundenen Dienste und Anwendungen
anmelden muss. Toll ist daran vorallem: das lästige Eingeben von Passwort und Benutzernamen
beim Wechseln zwischen einzelnen Diensten entfällt, das spart Zeit und Nerven.

#Verbreitung
Zahlreiche WWU Dienste bieten bereits die Möglichkeit das SSO zu nutzen. Dazu gehören zum Beispiel
die größeren Dienste wie meinZIV, das Learnweb oder der Maildienst perMail, aber auch über 50 andere oft
fachbereichspezifische Dienste.

#Nutzung
Wenn du das erste mal seit du deinen Browser geöffnet hast auf eine Seite mit SSO zugreifen willst so musst du dich
einmalig anmelden, danach bist du bei allen SSO Diensten angemenldet, bis du deinen Browser schließt.\
![Anmeldebox](images/loginbox.png "Authentifizierungsaufforderung")

#Nutze ich SSO?
Wahrscheinlich nutzt du das SSO schon ohne es aktiv zu merken. Schau dir die URL in deinem Browserfenster an, sämtliche
Dienste die das SSO benutzen liegen auf einem einzigen virtuellen Punkt `sso.wwu-muenster.de`,
wenn du also eine Seite
besuchst deren URL mit `sso.wwu-muenster.de` beginnt, kannst du dir sicher sein, dass diese das SSO der WWU verwendet.\
Beispielsweise verwendest du hier SSO bereits \
![url mit wwu](images/sso_learnweb.png)<br />
Solltest du auf einer Seite der WWU sein, die das SSO unterstützt aber mit www beginnt, so ist die einfachste
Möglichkeit, auf die SSO version zu wechseln das ersetzen des `www.uni-muenster.de` durch `sso.uni-muenseter.de`.\
Viele Seiten bieten auch neben dem normalen Login Knopf einen speziellen SSO login Knopf.

#Hintergrundinformationen
Das Single Sign On funktioniert indem dem Browser vorgegaukelt wird alle Dienste befänden sich am gleichen punkt, 
an `sso.uni-muenster.de`. Beim besuch dieses Webspaces wird der User aufgefortdert sich mithilfe einer 
`Digest-Authentisierung` zu identifizieren. Diese Methode hat den Vorteil, dass alle Daten nur Clientseitig gespeichert
werden und zB ein Session Hjacking fehlschlägt, solange der Browser vertrauenswürdig ist. Spricht man nun eine andere
Seite in der Domäne an, so sendet der Browser die Authentifizierungsdaten direkt mit. Der angesprochene Server agiert
als Proxy, er identifiziert zunächst den angeforderten Dienst und dessen Server, überprüft dann die Identität des 
Servers und leitet erst hiernach die Authentifizierungsdaten des Nutzers weiter.\
![Datenaustausch zwischen sso server, client und dienst server](images/grafik_single_sign_on.png)