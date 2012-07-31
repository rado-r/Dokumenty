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

### Vetvy - git branch
    git branch                  - vypise aktualne vetvy (branches)
    git branch nazov_vetvy		- vytvori novu vetvu z aktualneho commitu
    git branch -d nazov_vetvy 	- zmaze vetvu
    git branch --merged         - vypise vsetky zaclenene vetvy do aktualnej vetvy
    git branch --no-merged      - vypise nezaclenene vetvy

    git checkout -b new odkaz   - vytvory vetvu s nazvom "new" ktora bude odrazat commit z odkazu

### Vzdialeny repozitar - git remote
    git remote add pb git://github.com/paulboone/ticgit.git	- prida remote repozitar a pomenuje ho pb
    git remote rename pb paul	                - premenuje vzdialeny repozitar z pb na paul
    git fetch pb		                        - Stiahne data z repozitara
    git pull pb					- pouzije git fetch a nan aplikuje git merge
    git push remote_server nazov_branche	    - posle aktualnu vetvu na server

    git checkout -b serverfix origin/serverfix	- vytvory vetvu serverfix a ulozi do nej vzdialenu vetvu origin/serverfix 
    git push origin :serverfix	                - zmaze vzdialenu vetvu serverfix na servery origin

### Submoduly 
    git submodule add git://github.com/chneukirchen/rack.git rack	- prida submodul do mojho projektu
    git submodule init	        - Inicializuje konfiguracny subor
    git submodule update	    - Vyzdvyhne data a checkoutne prislusne revizie uvedene v superprojekte
    
#### Ak chceme stiahnut zmeny z vzdialeneho repozitara
    git checkout rack_branch	- prepneme na vetvu submodulu
    git pull			        - stiahne zmeny a aplikuje ich pomocou "git merge"

#### Submoduly a podstromy
    git remote add rack_remote git@github.com:schacon/rack.git	- prida remote so submodulom
    git fetch rack_remote		                                - stiahneme zmeny
    git checkout -b rack_branch	rack_remote/master              - checkoutne do novej vetvy rack_branch z vetvy rack_remote/master

    git read-tree --prefix=rack/ -u rack_branch	- [ v hlavnej vetve ] natiahne do hlavneho projektu submodul ako podadresar
    
#### Zapisanie zmien 
    git checkout master     - prepne na hlavnu vetvu
    git merge --squash -s subtree --no-comit rack_branch	- Vsetky zmeny sa zaclenia a mozeme ich lokalne zapisat (commitnut)
    
    
