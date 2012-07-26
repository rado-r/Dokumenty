## Git referencia

    git init    - inicializuje projekt v danom adresary a vytvory potrebne subory
    git status  - zisti stav suborov
	
### Pridavanie suborov - git add
    git add .               - zaradi vsetky subory na commit
    git add file.txt        - (stage) zaradi file.txt do dalsieho commitu
    git add directory/      - (stage) zaradi celi priecinok a rekurzivne vsetky subori v nom
    git reset HEAD file.txt - (unstage) odoberie uz pridany subor na commit 
    
### Commit - git commit
    git commit		    - commitne vsetky staged subory do lokalneho repozitara
    git commit -a       - na vsetky uz pridane subory pouzije git add a az potom git commit
    git commit --amend	- zluci tento commit s predchadzajucim ( ked nieco zabudneme pridat )

### Praca zo subormi
    git rm file.txt		        - zmaze subor aj z disku aj z repozitara
    git rm --cached file.txt	- zmaze subor iba z repozitara na disku ostane
    
    git mv file_from file_to	- presunie alebo premenuje subor

