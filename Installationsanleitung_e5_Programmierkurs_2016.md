# Installationsanleitung für den e5-Bachelorprogrammierkurs 2016

Um euch die Installation so einfach wie möglich zu gestalten, verwenden wir ab hier ein Terminalfenster. Gebt einfach nach und nach die Befehle ein und achtet auf den Output. Sollte dort irgendetwas wie `ERROR` oder `FATAL` stehen, solltet ihr eure Eingabe lieber noch einmal überprüfen ;). Also: los gehts!

_Hinweis: einige der folgenden Programme sind mehrere GB groß, demnach solltet ihr euch zu einer schnellen Internetverbindung begeben oder etwas mehr Zeit einplanen._

### Anaconda + ROOT + IPython

[Anaconda](https://www.continuum.io/downloads) beinhaltet eine Kollektion aus über 400 Python-Paketen, welche in der Wissenschaft, Mathematik und Datenanalyse gebräuchlich sind; also genau das Richtige für uns! Die Installation sieht wie folgt aus:

    ### Installiert wget, falls es nicht bereits installiert ist
    $ sudo apt-get install wget

    ### Legt den Ordner Downloads an und wechselt zu diesem
    $ mkdir Downloads
    $ cd Downloads

    ### Lädt die Installationsdatei herunter
    $ wget http://repo.continuum.io/archive/Anaconda3-2.5.0-Linux-x86_64.sh

    ### Führt die Installationsdatei aus
    $ bash Anaconda3-2.5.0-Linux-x86_64.sh

Eventuell müssen jetzt eure Umgebungsvariablen neu gesetzt werden, da Anaconda etwas in eure `.bashrc` geschrieben hat.

    $ source ~/.bashrc

Jetzt sollte eurem Terminal der Befehl `conda` bekannt sein. Aktualisiert und konfiguriert Anaconda wie folgt:

    $ conda update --all
    $ conda config --add channels https://conda.anaconda.org/NLeSC

    ### Erstellt eine virtuelle Umgebung mit dem Namen programmierkurs
    $ conda create --name=programmierkurs root=6 python=3

    ### Wechselt zu dieser Umgebung
    $ source activate programmierkurs

    ### Installiert Jupyter
    $ conda install jupyter

Ab hier sollten die folgenden Befehle keine Fehlermeldungen mehr geben: 

    * root -b -q
    * jupyter notebook

Außerdem sollte euer `ROOT` bereits korrekt verlinkt sein.

    $ ipython
    In [1]: import ROOT
    In [2]: test = ROOT.TString("hello, world!")
    In [3]: test
    Out[3]: 'hello, world!'

### Git 

Falls ihr noch kein Git installiert habt, installiert ihr es mit folgendem Befehl:
    
    $ sudo apt-get install git
