Git-Spiel

Betrachten Sie erneut die Vorgaben zur "Git-Quest". Die Geschichte des Helden Markus findet im master-Branch kein Ende, sondern erst im Hilfsbranch end.

Machen Sie nun verschiedene Experimente mit Branches in Git, und starten Sie dabei jeweils mit einem frischen Klon der Vorgaben.

    Ändern Sie eine Datei, die im Branch end nicht verändert wurde. Erzeugen Sie mit diesen Änderungen auf dem master einen neuen Commit. Mergen Sie danach den Branch end in den master-Branch.

        Ich habe die Readme Datei im "master" Branch geändert und committed
        Dann habe ich mit "git merge end" die Änderungen von end in den Masterbranch gemerged.


    Ändern Sie nun eine Datei, die auch im Branch end verändert wurde. Achten Sie dabei darauf, die Änderung an einer anderen Stelle in der Datei vorzunehmen. Erzeugen Sie mit diesen Änderungen auf dem master einen neuen Commit. Mergen Sie danach den Branch end in den master-Branch.

        Diesmal habe ich wieder die README.md im "end" Branch geändert.
        beim aufrufen von "git merge end" mit dem master branch wurde ein Mergekonflikt erkannt. 
            <<<<<<< HEAD
            kleine Änderung der Readme!
            =======
            kleine Änderung im End Branch
            >>>>>>> end
        Marker wurden zur Behebung des merge Konflikts entfernt aber beide Inhalte behalten

    Wie (2), aber ändern Sie nun eine Stelle, die auch im Branch end verändert wurde. Erzeugen Sie mit diesen Änderungen auf dem master einen neuen Commit. Mergen Sie danach den Branch end in den master-Branch. Was passiert, wenn die Änderung im master identisch zu der in end ist? Was passiert, wenn die Änderung im master anders ist als in end?
       
        Da Ich versehentlich in der letzten Aufgabenstellung die Selbe Stele wie zuvor im Master geändert habe, habe ich diesmal bewusst eine andere Stelle geändert und vorher die README.md im end Branch mit der README.md aus dem master branch korregiert.
        Diesmal gab es wieder einen Merge Konflikt, Da es aber lediglich etwas zum Einfügen war, konnte Git diesen Konflikt selbstständig beheben.

    Wie (2), aber setzen Sie bitte den Branch end auf die Spitze von master, bevor Sie end in master mergen.
        Mit Rebase habe ich nach erneuter Änderung der Readme den Stand von End auf den aktuellen stand gebracht und so konnte Git Fastforward beim merge nutzen.