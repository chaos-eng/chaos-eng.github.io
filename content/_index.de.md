+++
title = "PRINZIPIEN DES CHAOS ENGINEERINGS"
date = 2020-01-28T16:25:57+02:00
draft = false
+++

# PRINZIPIEN DES CHAOS ENGINEERINGS
Letzte Aktualisierung: März 2019

*Chaos Engineering führt Experimente auf einem System durch, um Vertrauen in das System aufzubauen auch unter widrigen Umständen in der Produktivumgebung zu bestehen.*

Die Fortschritte in verteilten und hoch-skalierten Software-Systemen verändern die Spielregeln im Software Engineering. Die IT-Industrie übernimmt schnell Methoden, um die Flexibilität in der Software-Entwicklung oder die Geschwindigkeit von Deployments zu erhöhen. Aus diesen Vorteilen erwächst eine dringend zu beantwortende Frage: Wie sehr können wir dem System vertrauen, das wir in die Produktivumgebung eingespielt haben?

Selbst wenn alle einzelnen Services in einem verteilten System ordnungsgemäß funktionieren kann die Kommunikation zwischen diesen Services unerwartete Ergebnisse haben. Diese unerwarteten Ergebnisse sowie seltene, aber nachteilige Vorfälle in der Produktivumgebung machen verteilte Systeme inhärent chaotisch.

Wir müssen Schwachstellen finden, bevor sie zu systemweiten Fehlverhalten führen. Schwachstellen im System können zum Beispiel folgende Dinge sein: unzureichende Ersatzkonfigurationen wenn ein Service nicht erreichbar ist, zu viele wiederholte Aufrufversuche durch ungenau konfigurierte TimeOuts, Ausfälle durch zu hohen Traffic auf eine Abhängigkeit, sich ausweitende Systemfehler wenn ein Single Point of Failure abstürzt, o.ä. Wir müssen die Schwachstellen mit den größten Auswirkungen proaktiv angehen bevor sie zu Problemen für unsere Kunden auf der Produktivumgebung führen. Wir müssen einen Weg finden, das eingebaute Chaos verteilter Systeme zu kontrollieren, um die Vorteile von erhöhter Flexibilität und Geschwindigkeit einzufahren während wir gleichzeitig Vertrauen in unsere Produktions-Deployments haben obwohl sie eine hohe Komplexität darstellen.

Ein empirisches, systembasiertes Vorgehen adressiert das Chaos in hoch-skalierten verteilten Systemen und erhöht unser Vertrauen, dass diese Systeme realistischen Bedingungen Stand halten. Wir lernen das Verhalten von verteilten Systemen kennen, indem wir sie in kontrollierten Experimenten beobachten. Das ist *Chaos Engineering*.

## CHAOS IN DER PRAXIS

Man kann Chaos Engineering als die Durchführung von Experimenten betrachten, um Schwachstellen im System zu finden; genauer geht es um Schwachstellen in großen verteilten Systemen. Die Experimente laufen in vier Schritten ab:

1. Starte damit einen „stabilen Zustand“ als einen messbaren System-Output zu definieren, der ein normales Verhalten des Systems signalisiert.
2. Stelle die Hypothese auf, dass der stabile Zustand sowohl in der Kontrollgruppe also auch in der Experimentalgruppe erhalten bleibt.
3. Führe Variablen ein, die echte Vorfälle aus dem produktiven Betrieb repräsentieren etwa Server-Abstürze, Festplattenfehlfunktionen, unterbrochene Netzwerkverbindungen, o.ä.
4. Versuche die Hypothese zu falsifizieren, indem du den System-Output von Experimental- und Kontrollgruppe nach Unterschieden in Bezug auf den definierten stabilen Zustand untersuchst.

Je schwerer es ist, das System aus dem stabilen Zustand zu bringen desto mehr Vertrauen haben wir in das Verhalten des Systems. Gefundene Schwachstellen sind Verbesserungsziele, die angegangen werden können bevor sich fehlerhaftes Verhalten im Gesamtsystem manifestiert.

## FORTGESCHRITTENE PRINZIPIEN 

Die nachfolgenden Prinzipien beschreiben bezogen auf den oben erläuterten Prozess das ideale Vorgehen im Chaos Engineering. Das Maß zu dem diese Prinzipien verfolgt werden korreliert stark mit dem Vertrauen, das wir in unser hoch-skaliertes, verteiltes System haben können.

### Formuliere eine Hypothese über das Verhalten im stabilen Zustand 

Konzentriere dich besser auf messbaren System-Output als auf die inneren Eigenschaften des Systems. Messungen des System-Outputs über einen begrenzten Zeitraum können als Proxy für den stabilen Zustand angesehen werden. Interessante Metriken, die den stabilen Zustand repräsentieren können unter anderem sein: der Durchsatz des Gesamtsystems, die durchschnittliche Latenz, Fehlerraten, o.ä.
Durch die Fokussierung auf die Verhaltensmuster des Systems während der Experimente verifiziert Chaos Engineering, dass das System funktioniert und validiert nicht wie es funktioniert.

### Variiere die Simulation von echten Vorfällen aus dem produktiven Betrieb 

Chaos-Variablen repräsentieren echte Vorfälle aus dem produktiven Betrieb des Systems. Priorisiere die Vorfälle entweder nach ihrem Schadenspotential oder nach der geschätzten Häufigkeit. Betrachte Vorfälle, die verschiedene Ursachen haben wie solche, die durch Hardware-Fehler verursacht werden (z.B. kaputte Server) solche, die durch Software-Fehler verursacht werden (z.B. ungültig formatierte Service-Antworten) oder solche, die zwar keine Fehler, aber besondere Vorkommnisse darstellen (z.B. Lastspitzen).  Jeder Vorfall, der das System aus dem stabilen Zustand bringen kann ist eine potentielle Variable in einem Chaos Experiment.

### Mache Experimente auf der Produktivumgebung

Systeme verhalten sich abhängig von Umgebung und Systemzugriffsmustern unterschiedlich. Da sich die Nutzungsmuster jederzeit ändern können ist eine Stichprobenentnahme tatsächlicher Zugriffe der einzige Weg den Zugriffspfad zuverlässig zu erfassen.  Im Chaos Engineering werden Experimente bevorzugt direkt auf der Produktivumgebung durchgeführt, um zu garantieren, dass das System in realistischer Art und Weise ausgeführt wird und die Ergebnisse hohe Relevanz für das tatsächlich in der Produktivumgebung laufende System haben.

### Automatisiere Experimente, um sie kontinuierlich durchzuführen 

Experimente manuell durchzuführen ist arbeitsaufwändig und auf Dauer nicht durchführbar. Automatisiere Experimente und führe sie kontinuierlich durch. Chaos Engineering baut Automatisierungsmöglichkeiten in das System ein, um Orchestrierung und Analyse voranzutreiben.

### Minimiere die Schadenszone 

Experimente in der Produktivumgebung durchzuführen kann bei den Kunden zu unnötigem Schaden führen. Obwohl kurzfristige negative Folgen erlaubt sein müssen ist es die Aufgabe und Verantwortung der Chaos Ingenieure dafür Sorge zu tragen, dass die schadhaften Folgen der Experimente minimiert und unter Kontrolle gehalten werden.

Chaos Engineering ist eine mächtige Methode, die bereits bei einigen der größten IT-Vorhaben der Welt verändert wie Software konzipiert und entwickelt wird. Während andere Methoden Geschwindigkeit und Flexibilität verbessern, beschäftigt sich Chaos Engineering explizit mit der Ungewissheit in verteilten Systemen. Die Prinzipien des Chaos geben uns das Vertrauen schnell Innovationen in sehr großem Maßstab zu entwickeln und gleichzeitig den Kunden das hochwertige Erlebnis zu bieten, das sie verdienen.

Tritt der laufenden Diskussion der „Prinzipien des Chaos“ und ihrer Anwendung in der [Chaos Community](https://groups.google.com/forum/#!forum/chaos-community) Google Group (engl.) bei.
