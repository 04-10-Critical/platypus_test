# BEITRAG5и5

Unabhängig davon, ob Sie Teil des Kernteams oder ein externer Mitwirkender sind, herzlich willkommen und vielen Dank für Ihren Beitrag zu https://learn.qiskit.org!

Auf learn.qiskit.org möchten wir einen hervorragenden Arbeitsraum schaffen, in dem wir uns alle willkommen, nützlich, respektiert und wertgeschätzt fühlen. Wenn Sie an learn.qiskit.org mitwirken möchten, erklären Sie sich mit unseren [Verhaltensregeln](CODE_OF_CONDUCT.md) einverstanden. Wir empfehlen Ihnen dringend, diese vor dem Fortfahren zu lesen.

Durch die Einhaltung dieser Richtlinien zeigen Sie, dass Sie die Zeit und Mühe der Hauptbeitragenden und -betreuer dieser Site wertschätzen. Vielen Dank!

## Inhaltsverzeichnis

- [Beginnen Sie mit dem Beitragen](#start-contributing)
- [Bevor Sie beginnen](#before-you-start)
- [Probleme beim Öffnen](#opening-issues)
- [Code beitragen](#contributing-code)
    - [Entscheiden, woran gearbeitet werden soll](#deciding-what-to-work-on)
    - [Aufstellen](#setup)
    - [Sich selbst zuordnen](#assigning-yourself)
    - [An einem Problem arbeiten](#working-on-an-issue)
    - [Pull-Anfragen](#pull-requests)
    - [Live-Vorschau](#live-previews)
    - [Codeüberprüfung](#code-review)
    - [Zusammenführen](#merging)
- [Codestil](#code-style)
    - [Typanmerkungen](#type-annotations)

## Beginnen Sie mit dem Beitragen

Dieses Repository dient der Entwicklung und Pflege der Qiskit Textbook (Beta)-Plattform. Wenn Sie zu Qiskit, der Open-Source-Python-Bibliothek, beitragen möchten, besuchen Sie stattdessen das [Qiskit-Repository](https://github.com/Qiskit/qiskit) . Oder wenn Sie zur [Website qiskit.org](https://qiskit.org) beitragen möchten, besuchen Sie stattdessen das [Repository von qiskit.org](https://github.com/Qiskit/qiskit.org) .

Es gibt viele Möglichkeiten, Beiträge zu leisten: vom Aufspüren eines Tippfehlers bis hin zur Verbesserung der Leistung oder Zugänglichkeit; Sie können ein Problem melden oder einen Patch vorbereiten. Lesen Sie in jedem Fall die Beitragsrichtlinien zum Melden neuer Probleme und zum Einreichen von Pull Requests.

Bitte verwenden Sie dieses Repository nicht für Fragen zu Qiskit: Es gibt bessere Möglichkeiten. Nutzen Sie unseren öffentlichen [Slack](https://ibm.co/joinqiskitslack) oder stellen Sie Ihre Frage in [Stack Overflow](https://stackoverflow.com/questions/tagged/qiskit) .

## Bevor Sie beginnen

Die Mitarbeit an diesem Repository setzt [Git-](https://git-scm.com) Kenntnisse voraus. Externe Mitwirkende benötigen Grundkenntnisse zu Repositories, Remote-Repositories, Branches und Commits. Kernmitwirkende sollten sich außerdem mit der Konfliktlösung und dem Rebasing auskennen.

[Es](https://try.github.io/) gibt jede Menge nützliche Ressourcen zu Git.

## Probleme beim Öffnen

Sie können unter https://github.com/Qiskit/platypus/issues/new eine Fehlfunktion melden. Bitte geben Sie Schritte zur Reproduktion und das erwartete Verhalten an.

Darüber hinaus können Probleme mit dem Inhalt, wie Tippfehler oder Umformulierungen, gemeldet werden.

Kernbeitragende klassifizieren die Aufgaben entsprechend ihrer Art und priorisieren sie von Sprint zu Sprint.

## Code beitragen

### Entscheiden, woran gearbeitet werden soll

Die Arbeitsbelastung und der Rückstand des Kernteams werden über [Projekte auf qiskit.org](https://github.com/Qiskit/qiskit.org/projects) verwaltet.

Um unseren Mitarbeitern einen Überblick darüber zu geben, wo das Team Unterstützung benötigt, verwenden wir das Label [„Willkommen zu Beiträgen“](https://github.com/Qiskit/qiskit.org/issues?q=is%3Aissue+is%3Aopen+label%3Aeducation+label%3A%22contributions+welcome%22) – dieses ist für alle Mitwirkenden geeignet. Darüber hinaus können sich alle, die relativ neu im Open-Source-Workflow oder in unserer Codebasis sind, die mit dem Label [„Gutes erstes Problem“](https://github.com/Qiskit/qiskit.org/issues?q=is%3Aissue+is%3Aopen+label%3Aeducation+label%3A%22good+first+issue%22) gekennzeichneten Probleme ansehen.

### Aufstellen

Sie haben sich also entschieden, selbst Hand anzulegen und mit der Arbeit an einem Patch zu beginnen? Dann sollten Sie wissen, dass qiskit.org dem [Forking-Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow) mit [Feature-Branches](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow) folgt.

Das bedeutet, dass wir von Ihnen erwarten, dass Sie das Projekt auf Ihrem eigenen GitHub-Konto forken und Ihren `main` zur Verfolgung dieses Repositorys einrichten. Ein typisches Git-Setup nach [dem Forken des Projekts](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/fork-a-repo) sieht folgendermaßen aus:

```sh
# After forking the repository in GitHub
git clone https://github.com/<your_username>/platypus.git
cd platypus
git remote add upstream https://github.com/Qiskit/platypus.git
git remote update upstream
git checkout main
git branch -u upstream/main
git pull
```

Aufgrund einiger Zugriffsbeschränkungen zwischen Forks und dem Head-Zweig empfehlen wir Ihnen als Hauptbeitragender, das Repository zu [klonen,](https://support.atlassian.com/bitbucket-cloud/docs/clone-a-repository/) anstatt es zu forken.

### Sich selbst zuordnen

Der allererste Schritt zur Bearbeitung eines Problems besteht darin, [sich selbst das Problem zuzuweisen](https://docs.github.com/en/issues/tracking-your-work-with-issues/assigning-issues-and-pull-requests-to-other-github-users#assigning-an-individual-issue-or-pull-request) . Dadurch erhalten alle Mitwirkenden Einblick, wer woran arbeitet.

### An einem Problem arbeiten

Wenn Sie mit der Bearbeitung eines Problems beginnen, stellen Sie sicher, dass Sie sich in Ihrem `main` befinden und dieser vollständig aktuell ist. Erstellen Sie anschließend einen neuen Zweig mit einem aussagekräftigen Namen. Der typische Terminalcode hierfür lautet:

```sh
git checkout main
git pull upstream main
git checkout -b issue-1234-new-header
```

Beginnen Sie nun mit dem Hinzufügen Ihrer Änderungen und denken Sie daran, diese häufig zu bestätigen:

```sh
git commit
```

Und fügen Sie bei Bedarf eine Zusammenfassung und einige Anmerkungen oder Klarstellungen hinzu:

```
Create a new header layout.

Includes a new component factoring out the header of this new page and others.
```

Von Zeit zu Zeit möchten Sie überprüfen, ob Ihr `main` noch aktuell ist. Wenn nicht, müssen Sie einen Merge (oder [ein Rebase](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase) ) durchführen und anschließend weiterarbeiten:

```sh
git checkout main
git pull
git checkout issue-1234-new-header
git merge main
```

### Pull-Anfragen

Pull Requests dienen einem doppelten Zweck:

1. Teilen Sie den Code mit dem Team. So ist fast jeder über die Entwicklung der Codebasis informiert.
2. Bieten Sie eine Möglichkeit zur Verbesserung der Codequalität.

Wenn Sie meinen, dass Ihre Arbeit erledigt ist, pushen Sie den Zweig in Ihr Repository:

```sh
git push origin issue-1234-new-header
# Start a pull request in GitHub
```

[Erstellen Sie einen Pull Request](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request) für `main` (oder einen Feature-Zweig). Geben Sie beim Erstellen des Pull Requests eine Beschreibung und [einen Link zum Problem an, das gelöst werden soll](https://docs.github.com/en/free-pro-team@latest/github/managing-your-work-on-github/linking-a-pull-request-to-an-issue) .

Das Verknüpfen des Problems hat den Vorteil, dass das zugehörige Problem beim Mergen des Pull Requests automatisch geschlossen wird. Leider funktioniert dies nicht beim Mergen von Pull Requests mit einem Feature-Branch. Denken Sie in diesen Fällen daran, die zugehörigen Pull Requests nach [dem Mergen des Pull Requests](#merging) manuell zu schließen.

### Live-Vorschau

Als Teil unserer Infrastruktur für kontinuierliche Integration erhält jeder Pull Request, der aus dem Head-Repository geöffnet wird und den Build-Prozess durchläuft, eine dedizierte Bereitstellung, die auf [IBM Code Engine](https://cloud.ibm.com/codeengine/overview) ausgeführt wird.

Dies ermöglicht dem Team Live-Vorschauen von Zweigen, erleichtert das Teilen von Links und die Überprüfung von Änderungen bei Bedarf. Sie können Ihren Arbeitszweig unter `https://qiskit-org-pr-<pull-request-number>.<unique_id>.us-south.codeengine.appdomain.cloud/` in der Vorschau anzeigen.

Dies bedeutet, dass für gegabelte Repositories der Pull Request keine Live-Vorschau generiert und dieser Schritt übersprungen wird.

### Codeüberprüfung

Sobald Sie einen PR gesendet haben, werden die Code-Mitwirkenden benachrichtigt und es kann eine Codeüberprüfung durchgeführt werden. Die Codeüberprüfung hilft bei der Lösung von Implementierungs-, Semantik- und Wartbarkeitsproblemen.

Das Repository enthält auch einige automatisierte Prüfungen wie Tests und [Linting](#solving-linting-issues) . Damit ein Pull Request zum Merge bereit ist, muss er **die automatischen Prüfungen bestehen und mindestens eine positive Bewertung erhalten** .

Bei Code-Reviews gibt es zwei wichtige Rollen: den Reviewer und den Mitwirkenden. Der Reviewer wacht über Best Practices und die Codequalität, stellt klärende Fragen, weist auf Implementierungsfehler hin und empfiehlt Änderungen. Wir erwarten vom Mitwirkenden, dass er Empfehlungen ernst nimmt und bereit ist, vorgeschlagene Änderungen umzusetzen oder stattdessen andere Maßnahmen zu ergreifen.

Beachten Sie, dass wir von den Mitwirkenden nicht erwarten, dass sie auf **alle** Kommentare eingehen, und auch nicht, dass der Prüfer **alle** Probleme hervorhebt. Wir hoffen, dass beide Kompromisse eingehen, um im geschätzten Aufwand so viel Wert und Qualität wie möglich bereitzustellen.

Wir erwarten keine Diskussionen in den Pull Requests. Bei Meinungsverschiedenheiten empfehlen wir dem Beitragenden, dem Reviewer nachzugeben und diesem Alternativen vorzuschlagen.

### Zusammenführen

Sobald alle automatisierten Prüfungen erfolgreich waren und eine positive Bewertung vorliegt, kann der Pull Request zusammengeführt werden. Wenn Sie ein externer Mitwirkender sind, wird Ihr PR voraussichtlich von einem Hauptmitwirkenden zusammengeführt.

## Codestil

**Lesbarkeit** ist unser wichtigstes Anliegen. Wir erwarten von unseren Prüfern, dass sie besonders auf die Lesbarkeit achten, damit sie neue Beiträge zur Codebasis verstehen.

### Typanmerkungen

Bei der Typprüfung streben wir die Einhaltung der [strengen TypeScript-Prüfungen](https://www.typescriptlang.org/tsconfig#strict) an. Das bedeutet, dass keine impliziten `any` verwendet werden, obwohl beispielsweise kein bestimmter Stil bei der Eingabe erzwungen wird.

Die goldene Regel lautet: **Geben Sie Ihre Absichten bekannt, und überlassen Sie den Rest der Typinferenz** . Kommentieren Sie Funktions- und Methodensignaturen sowie Klassen-/Objekteigenschaften und Moduldeklarationen, und verlassen Sie sich bei Zwischenwerten auf die Typinferenz.

Nicht tun:

```ts
function max(a, b) {
  return a > b ? a : b
}
```

Aber stattdessen:

```ts
function max(a: number, b: number): number {
  return a > b ? a : b
}
```

Wenn Sie mit reinen JavaScript-Objekten arbeiten, sollten Sie eine Schnittstelle mit den gewünschten Methoden und Eigenschaften deklarieren und dann eine Factory-Funktion implementieren, die eine Implementierung der Schnittstelle zurückgibt.

Nicht tun:

```ts
export default {
  scale: 2,
  magnify (v) {
    return v * this.scale
  }
}
```

Aber stattdessen:

```ts
interface MyType {
  scale: number
  magnify (v: number): number
}

function _factory () : MyType {
  return {
    scale: 2,
    magnify (v) {
      return v * this.scale
    }
  }
}

export default _factory()
```

## Schlussworte

Vielen Dank, dass Sie das Dokument bis zum Ende gelesen haben! Durch die Einhaltung dieser Richtlinien drücken Sie Ihre Bereitschaft zur Zusammenarbeit und zu einem konstruktiven Beitrag aus. Vielen Dank auch dafür!

Wenn Sie ein Hauptbeitragender sind, möchten Sie vielleicht mehr über [unsere Verfahren im Wiki](https://github.com/Qiskit/qiskit.org/wiki) erfahren.
