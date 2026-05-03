1.	a) Erklären Sie die Ausgabe.
Git status: Den Stand der Workingcopy abfragen.
Ausgabe:
pm-lecture % git status
On branch b03

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   CONTRIBUTING.md
        modified:   homework/b03.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        foo.java

no changes added to commit (use "git add" and/or "git commit -a")

pm-lecture -> aktuelles Verzeichnis 
% -> Promt Symbol
Git status -> git Befehl
On branch b03 -> Wir befinden uns Aktuell auf dem Branch b03
Changes not staged for commit: -> Dateien wurden verändert aber noch nicht gestaged. Im Repo finden für diese Dateien keine Änderungen bei einem Commit Statt.
(use "git add <file>..." to update what will be committed) -> Befehl zum Hinzufügen
  (use "git restore <file>..." to discard changes in working directory) -> Befehl zum entfernen
        modified:   CONTRIBUTING.md -> Dateipfad zur veränderten nicht hinzugefügten Datei
        modified:   homework/b03.md -> Dateipfad zur veränderten nicht hinzugefügten Datei

Untracked files: -> Liste von neuen Dateien
(use "git add <file>..." to include in what will be committed) -> Befehl zum hinzufügen
foo.java -> Dateipfad zur neuen Datei
no changes added to commit (use "git add" and/or "git commit -a") -> Es wurden noch keine Änderungen hinzugefügt (gestaged). Es müssen die Änderungen erst hinzugefügt werden oder man benutzt git commit -a um von git alle getrackten Änderungen hinzufügen zu lassen und im Anschluss automatisch zu commiten.

1.	b) Geben Sie eine Befehlssequenz an, mit der Sie nur die Änderungen in foo.java committen können.
git add foo.java
git commit -m „foo.java wurde erstellt und bearbeitet.“



2.	)
git log
git show 4aa80149369d7412df0a9ff837c4bc9ec37c774d
git show 4aa80149369d7412df0a9ff837c4bc9ec37c774d..HEAD --reverse -p

•  Was passierte an tag 01? 
+Mit seinem Schwert in der Hand und und einer leichten Rüstung bekleidet stieg Markus tapfer in den Dungeon ein. Schon bald stieß er auf die ersten Monster - grässliche, rattenähnliche Wesen.
•  Wann hat der Held zum ersten Mal 4 experience Punkte? 
Tag 01.3
•  Wann hat der Held zum ersten Mal 10 hunger Punkte? 
Tag 02
•  Wie viele Heiltränke hat der Held insgesamt in seinem Rucksack gehabt? 
2
•  Was hat der Held im Shop gekauft? Und wie viel Gold hat er dafür bezahlt? 
Tag 03.9 -> 1 Brot für 5 Goldstücke
Tag 03.14 -> 1 Heiltrank für 5 Goldstücke
•  Was passierte zwischen tag 03 und tag 04, d.h. was änderte sich zwischen diesen Commits? 
Git log
$ git diff 2ffebcfd908ad2abcc619429157b0832dac0dad3 39568d5e84832a2f168f3f473a612bc373e1bb63
10 Gold wurden ausgegeben, 5 Lebenspunkte wurden regeneriert und 10 Hungerpunkte wurden abgebaut.
diff --git a/questlog.md b/questlog.md
index 70e2913..f1a7359 100644
--- a/questlog.md
+++ b/questlog.md
@@ -7,3 +7,5 @@ Mit seinem Schwert in der Hand und und einer leichten Rüstung bekleidet stieg M
 Immer wieder stieß Markus auf verschiedene Monster wie Goblins, Gnolle und sogar einen gefährlichen Schlammklumpen. Jeder Kampf war ein harter und erbitterter Kampf, bei dem Markus an seine Grenzen ging. Doch sein Wille, seine Quest zu erfüllen und das Amulet zu finden, gab ihm die Kraft, weiterzumachen.

 Schließlich erreichte Markus einen versteckten Raum im Dungeon, in dem ein mysteriöser alter Zwerg auf ihn wartete. Dieser Zwerg entpuppte sich als ein Händler und besaß einen kleinen Shop, in dem er nützliche Gegenstände und Lebensmittel verkaufte. Markus trat ein und begann mit dem Zwerg zu verhandeln.
+
+Erfrischt und gestärkt machte sich Markus auf den Weg, um die letzte Etappe seiner Quest zu erfüllen.
diff --git a/rucksack.md b/rucksack.md
index efcd45a..86f99b2 100644
--- a/rucksack.md
+++ b/rucksack.md
@@ -2,7 +2,7 @@

 | Slot | Content                             |
 |------|-------------------------------------|
-| 0    | 10 Gold                             |
+| 0    |                                     |
 | 1    |                                     |
 | 2    |                                     |
 | 3    |                                     |
diff --git a/stats.md b/stats.md
index 0de3005..a655110 100644
--- a/stats.md
+++ b/stats.md
@@ -2,8 +2,8 @@

 | Property   | Value         |
 |------------|---------------|
-| health     | 5             |
+| health     | 10            |
 | experience | 10            |
-| hunger     | 10            |
+| hunger     | 0             |
 | weapon     | sword (3 dmg) |
 | armor      | light (2 dmg) |

•  Hat der Held etwas gegessen? Falls ja, was und wann?
Tag 03.17 -> Brot gegessen und Heiltrank getrunken


Beim letzten Commit (tag 04.5) ist etwas schief gelaufen, es wurden versehentlich zu wenig experience Punkte eingestellt. Ändern Sie diesen letzten Commit und passen Sie die experience Punkte auf 42 an.
$ git add stats.md

NIBBU@DESKTOP-15MRIVA MINGW64 /i/uni/programmieren2/prog2_ybel_gitquest (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   stats.md


NIBBU@DESKTOP-15MRIVA MINGW64 /i/uni/programmieren2/prog2_ybel_gitquest (master)
$ git commit --amend --no-edit
[master ba1ba15] tag 04.5
 Author: Carsten Gips <cagix@hsbi.de>
 Date: Tue Mar 12 19:04:43 2024 +0100
 3 files changed, 2 insertions(+), 4 deletions(-)


Schreiben Sie die Geschichte in der Datei questlog.md fort und erzeugen Sie einen neuen Commit für tag 04.6. Ändern Sie bitte hierzu nur die eine Datei questlog.md.
Git add questlog.md
Git commit -m „tag 04.06“

Schreiben Sie die Geschichte noch weiter fort (tag 04.7), aber ändern Sie diesmal mehrere Dateien, die an diesem Tag (neuer Commit) gemeinsam eingecheckt werden sollen.
Git add .
git commit -m "tag 04.07"

Fälschlicherweise wurden die Statuspunkte und die Ausrüstung bisher gemeinsam in der Datei stats.md geführt. Korrigieren Sie das und verschieben Sie die Ausrüstungsgegenstände aus der Datei stats.md in eine neue Datei gear.md. Checken Sie Ihre Änderungen als tag 04.8 (neuer Commit) gemeinsam ein. (Hinweis: Es reicht, wenn diese Änderung als letzter Commit auf der Spitze des master-Branches existiert. Sie brauchen/sollen die Trennung von Statuspunkten und Ausrüstung nicht rückwirkend in die Historie einbauen!)
Git add .
Git commit -m „tag 04.08“