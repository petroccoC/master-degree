Lavoro di tesi realizzato al termine del corso di laurea magistrale in ingegneria informatica e dell'automazione presso l'Università Politecnica delle Marche.

In questo lavoro di tesi viene proposto un approccio alla digitalizzazione e alla conservazione di un documento sensibile quale la ricetta medica, basato sull’utilizzo della Blockchain, una tecnologia affermatasi recentemente e che sta riscuotendo notevole successo nei più svariati campi applicativi, dallo scambio di moneta digitale alla stipulazione di contratti, dalla gestione di dati sanitari alla pubblica amministrazione. Il prototipo di applicazione per la gestione delle ricette bianche dematerializzate è basato sull’utilizzo di una determinata tipologia di blockchain, quelle private ed offre le seguenti caratteristiche:
* Meccanismi di garanzia di autenticità e validità delle ricette mediche dematerializzate;
* Elevata affidabilità e tolleranza ai guasti del sistema;
* Accorgimenti specifici per il trattamento dei dati sensibili.

## Utilizzo
L'ambiente utilizzato durante la scrittura è stato:

* Sublime Text 3 
* LaTeXTools (plugin for Sublime Text)

### Setup
1. Installare una distribuzione LaTeX (nella stesura del documento è stata utilizzata la distribuzione [Tex Live](https://www.tug.org/texlive/acquire.html));
2. Installare [Sublime Text 3](https://www.sublimetext.com/);
3. Installare [Sublime Text Package Control](https://packagecontrol.io/), package manager pensato per Sublime;
4. Install [LaTeXTools](https://github.com/SublimeText/LaTeXTools). Attraverso il package manager basta premere <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd>, scrivere `Install Package` e ricercare `LaTeXTools`;
6. Compilare il documento tramite <kbd>CTRL</kbd>+<kbd>B</kbd>.

### Compile script
Una volta installato andare in `Preferences-> Package Settings-> LaTeXTools-> Settings - User` e modificare il valore assegnato a `builder` con `script` e inserire dentro `builder_settings` questo:

```
"windows" : {
			"script_commands": [
            "pdflatex -shell-escape -synctex=1 -interaction=nonstopmode",
            "makeglossaries",
            "pdflatex -shell-escape -synctex=1 -interaction=nonstopmode",
            "pdflatex -shell-escape -synctex=1 -interaction=nonstopmode",
            "bibtex",
            "pdflatex -shell-escape -synctex=1 -interaction=nonstopmode",
            "pdflatex -shell-escape -synctex=1 -interaction=nonstopmode"
        ]
		},
```      	
## Credits
Questo documento è stato realizzato partendo dal template scaricabile sul sito  [andreadd](https://www.andreadd.it/appunti/polimi/tesi/tesi.html), basato sul modello di Tesi Moderna proposto da Lorenzo Pantieri.
