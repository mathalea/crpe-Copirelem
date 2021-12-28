# CRPE

La COPIRELEM met à disposition sur http://www.arpeme.fr/index.php?id_page=27 des exercices d'annales du concours de recrutement de professeurs des écoles ainsi que des sujets de Master avec les corrections détaillées.


Avec `gs -dBATCH -dNOPAUSE -r600 -sDEVICE=png16m -sOutputFile=2017-%03d.png 2017.pdf`, le pdf est transformé en un png par page.

Avec `for file in *.png; do convert $file -crop  +500+500 +repage -crop -200-400 +repage crop/$file ; done`, chaque png est recadré pour enlever l'entête, le pied de page et les marges latérales.

Ensuite, à la main, on recadre les fichiers exercice par exercice et on les nomme annee-lieu-exN-n.png ou annee-lieu-exN-cor-n.png 

Par la suite, ces images sont intégrées dans MathALEA.
