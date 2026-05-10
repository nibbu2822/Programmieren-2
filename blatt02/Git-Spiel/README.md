Git-Spiel

Betrachten Sie erneut die Vorgaben zur "Git-Quest". Die Geschichte des Helden Markus findet im master-Branch kein Ende, sondern erst im Hilfsbranch end.

Machen Sie nun verschiedene Experimente mit Branches in Git, und starten Sie dabei jeweils mit einem frischen Klon der Vorgaben.

    Ändern Sie eine Datei, die im Branch end nicht verändert wurde. Erzeugen Sie mit diesen Änderungen auf dem master einen neuen Commit. Mergen Sie danach den Branch end in den master-Branch.
    Ändern Sie nun eine Datei, die auch im Branch end verändert wurde. Achten Sie dabei darauf, die Änderung an einer anderen Stelle in der Datei vorzunehmen. Erzeugen Sie mit diesen Änderungen auf dem master einen neuen Commit. Mergen Sie danach den Branch end in den master-Branch.
    Wie (2), aber ändern Sie nun eine Stelle, die auch im Branch end verändert wurde. Erzeugen Sie mit diesen Änderungen auf dem master einen neuen Commit. Mergen Sie danach den Branch end in den master-Branch. Was passiert, wenn die Änderung im master identisch zu der in end ist? Was passiert, wenn die Änderung im master anders ist als in end?
    Wie (2), aber setzen Sie bitte den Branch end auf die Spitze von master, bevor Sie end in master mergen.

Was beobachten Sie jeweils? Erklären Sie Ihre Beobachtungen. Wenn es Konflikte gibt: Wie lösen Sie diese auf? Demonstrieren Sie das Vorgehen im Praktikum live.