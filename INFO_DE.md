Die Somtoday-Quell- und Ziel-Connectoren vereinfachen das Management von Benutzerkonten und Berechtigungen innerhalb Ihrer Bildungseinrichtung erheblich. Die Connectoren verbinden Somtoday mit Ihren Zielsystemen über die Identity & Access Management (IAM)-Lösung HelloID von Tools4ever. Die Verbindung automatisiert verschiedene Inflow-, Durchfluss- und Outflow-(IDU)-Prozesse in Ihrer Organisation, sodass Sie sich darum nicht kümmern müssen. In diesem Artikel erfahren Sie mehr über diese Verbindung, die spezifischen Möglichkeiten, die sie bietet, und die Vorteile.

## Was ist Somtoday

Somtoday ist eine elektronische Lernumgebung (ELO), ein Portal, das Schülern und Betreuern unter anderem Einblicke in Hausaufgaben, Noten und Nachrichten sowie den Stundenplan und die Studienplanung bietet. Zudem können Schüler Arbeitsergebnisse hochladen und mit Lehrkräften teilen. Somtoday kann als Quellsystem für IDU-Prozesse eingesetzt werden und bildet eine wichtige Erweiterung eines HRM-Systems. Es verschafft den Mitarbeitern zusätzliche Einblicke und enthält alle Teilnehmerdaten, die im IDU-Prozess von Bildungseinrichtungen eine entscheidende Rolle spielen. Mitarbeiter und Schüler verwenden Somtoday zudem als Arbeitsumgebung.

## Warum ist eine Somtoday-Verbindung nützlich?

Der Somtoday-Connector wird häufig als Quellverbindung zur Ergänzung eines HR-Systems eingesetzt. Die Verbindung konzentriert sich spezifisch auf Teilnehmer und die Bereitstellung zusätzlicher Daten über Mitarbeiter. Zudem unterstützt der Somtoday-Connector das Account-Management von Schülern und Mitarbeitern im ELO zur Unterstützung der IDU-Prozesse. Der Somtoday-Connector ermöglicht die Anbindung an häufig genutzte Zielsysteme wie:

* Active Directory
* Entra ID
* Google Workspace

Weitere Details zur Verbindung mit diesen Zielsystemen finden Sie weiter unten im Artikel.

## HelloID für Somtoday hilft Ihnen bei

**Verbesserte Compliance:** Die Integration steigert auch Ihre Compliance. Durch Automatisierung sichern Sie den Prozess, gewährleisten Konsistenz und vermeiden Fehler. Von Vorteil ist zudem Role Based Access Control (RBAC), bei dem Sie Änderungen nicht individuell, sondern auf Basis von RBAC-Rollen zuweisen. Dies ermöglicht es unter anderem, die Rechte bestimmter Benutzergruppen auf einmal zu definieren. Alle Änderungen, die HelloID durchführt, werden in einem umfassenden Auditprotokoll der IAM-Lösung festgehalten, sodass Sie Ihre Compliance nachweisen können.

**Einheitliches Account-Management:** Der Eintritt eines neuen Schülers oder Mitarbeiters erfordert die Erstellung der richtigen Konten. Durch die Integration von Somtoday mit Ihren Zielsystemen via HelloID müssen Sie sich darum nicht kümmern. Die weitgehende Automatisierung des Prozesses gewährleistet ein konsistentes und einheitliches Account-Management. So vermeiden Sie Fehler und stellen sicher, dass Benutzer zur richtigen Zeit über die richtigen Konten verfügen.

**Anpassung an den IDU-Prozess in der Organisation:** Ihre Bildungseinrichtung ist kontinuierlich im Wandel, sowohl in Bezug auf Schüler als auch auf Mitarbeiter. Neue Personen treten ein, Schüler wechseln in ein höheres Schuljahr, Mitarbeiter erhalten neue Positionen, und Personen scheiden aus. All diese Entwicklungen erfordern Änderungen in Ihren Systemen, wodurch die Anzahl der notwendigen Schritte schnell zunimmt. Die Verbindung von Somtoday mit Ihren Zielsystemen nimmt Ihnen viel Arbeit ab und sorgt dafür, dass das Account-Management perfekt an den IDU-Prozess Ihrer Organisation angepasst ist.

**Verbesserte Effizienz:** Die Automatisierung des Account-Managements bietet erhebliche Vorteile. So erhöhen Sie Ihre Effizienz und können Benutzern noch schneller dienen. Praktisch, denn so stehen Schülern und Mitarbeitern die Konten und Berechtigungen, auf die sie in der Praxis angewiesen sind, früher zur Verfügung.

## Wie HelloID mit Somtoday integriert wird

Wenn Sie Somtoday mit Ihren Zielsystemen integrieren, fungiert Somtoday in der Regel als Ergänzung zu Ihrem HR-System. Dies ermöglicht die automatisierte Verwaltung des gesamten Lebenszyklus von Benutzerkonten in Ihren Zielsystemen über HelloID. So vermeiden Sie Fehler, sparen Zeit und können Benutzern noch schneller dienen.

| Änderung in Somtoday |	Verfahren in den Zielsystemen |
| ------------------------- | --------------------- | 
| **Neuer Schüler oder Mitarbeiter** |	HelloID erstellt basierend auf Informationen aus Somtoday die erforderlichen Konten für neue Schüler und Mitarbeiter in Ihren Zielsystemen und weist die nötigen Berechtigungen zu. Sie müssen sich nicht um diesen Prozess kümmern; HelloID erkennt automatisch die Änderung in Somtoday und nimmt basierend darauf die gewünschten Änderungen vor.|
| **Anderes Schuljahr, geänderte Funktion, Änderung in der Platzierung, Fächerwahl und Lerngruppen** | Bildungsorganisationen sind ständig in Bewegung. So wechseln bestehende Schüler in ein neues Schuljahr oder wiederholen das Schuljahr. Auch können Schüler andere Fächer wählen, was zu anderen Lerngruppen führen kann. Gleichzeitig ist auch Ihr Personalbestand dynamisch, und Mitarbeiter können neue Funktionen zugewiesen bekommen. Diese Änderungen können andere Konten und Berechtigungen in Ihren verbundenen Zielsystemen erfordern. HelloID automatisiert diesen Prozess weitgehend, wobei das Berechtigungsmodell von HelloID immer maßgeblich ist. Zuweisungen, die mit der alten Funktion verbunden sind, zieht HelloID automatisch zurück.|
| **Name ändert sich** | Aus diversen Gründen kann sich der Name eines Schülers oder Mitarbeiters ändern. HelloID erkennt diese Änderung und passt den Benutzernamen der Nutzer automatisch an. |
| **Schüler oder Mitarbeiter verlässt die Organisation** |	Benutzerkonten in Zielsystemen werden deaktiviert, wobei HelloID die betroffenen Mitarbeiter in der Organisation informiert. Nach einer gewissen Zeit löscht HelloID die Konten automatisch und entzieht die erteilten Berechtigungen. |

HelloID verwendet Standard-REST-Calls für die ConnectAPI und SOAP-Calls für die HRMService. Die IAM-Lösung zieht über die ConnectAPI pro Einrichtung und Standort Daten zu einem spezifischen Bezugsjahr ab. Basierend darauf verarbeitet HelloID die Platzierungen, Fächerwahl und Lerngruppen, sodass diese bei der Zuweisung von Berechtigungen mithilfe von Geschäftsregeln verwendet werden können. Die HRMService ermöglicht die Verwaltung von Daten auf der Personalakte im HR-Bereich von Somtoday.

## Somtoday über HelloID mit Zielsystemen verbinden

Sie können Somtoday über HelloID mit verschiedenen Zielsystemen verbinden. Praktisch, denn so kann HelloID basierend auf Informationen aus Somtoday Änderungen in Ihren Zielsystemen durchführen. Die Verbindungen nehmen Ihnen nicht nur Arbeit ab, sondern heben auch die Verwaltung von Benutzern und Berechtigungen auf ein höheres Niveau. Einige Beispiele für häufige Integrationen sind:

* **Somtoday - AFAS Verknüpfung:** Dank der Verknüpfung zwischen Somtoday und AFAS können Sie das Management von Benutzerkonten und Berechtigungen weitgehend automatisieren. Erstellen Sie ein neues Konto oder ändern Sie ein bestehendes Konto in Somtoday? Dann erkennt HelloID diese Änderung und verarbeitet sie automatisch in AFAS. Die Verknüpfung nimmt Ihnen Arbeit ab und optimiert das Account-Management.

* **Somtoday – Active Directory Verknüpfung:** Dank der Verknüpfung zwischen Somtoday und Active Directory ist es unter anderem möglich, diese Systeme automatisiert zu synchronisieren. So stellen Sie sicher, dass Konten und Berechtigungen immer vollständig auf dem neuesten Stand sind. Zudem vermeiden Sie menschliche Fehler, da Sie Daten nicht mehr manuell übertragen müssen.

* **Somtoday – Entra ID Verknüpfung:** Die Integration mit dem cloudbasierten Entra ID ermöglicht unter anderem die vollständige Automatisierung von allem, von der Bereitstellung der Konten bis zur Zuweisung der richtigen Berechtigungen. Erfolgt der Bereitstellungsprozess im lokalen Pendant Active Directory? Dann können Sie unter anderem Cloud-Only-Berechtigungen zuweisen.

Für HelloID stehen 200 Connectoren zur Verfügung, mit denen Sie die IAM-Lösung an eine breite Palette von Quell- und Zielsystemen anschließen können. Dank dieser umfassenden Integrationsmöglichkeiten können Sie Somtoday auch mit allen beliebten Zielsystemen verbinden.