mysql -u root -p
use parcours_comba

 
SELECT nomObst , idnivdif FROM obstacle,niveaudiff 
nomObst 
idnivdif 

combat
1

combat
2

combat
3

fosse
1

fosse
2

fosse
3

grimper
1

grimper
2

grimper
3

nager
1

nager
2

nager
3

tirer
1

tirer
2

tirer
3

saut
1

saut
2

saut
3






SELECT nomObst,libellé,noteins,bonus,noteins+bonus FROM passer AS p,soldat AS sol, participation AS partic, niveaudiff as niv,obstacle AS obst, soldat AS ins WHERE sol.idsoldat=partic.idsoldat AND partic.idPartic=p.idPartic AND p.idObst=obst.idObst AND obst.codeniv=niv.idnivdif AND ins.idsoldat=p.idsold AND partic.idPartic=1 


nomObst 
libellé 
noteins 
bonus 
noteins+bonus 

combat
difficile
6
4
10

fosse
difficile
9
4
13

grimper
moyen
8
2
10

nager
facile
10
1
11

tirer
moyen
7
2
9

saut
facile
7
1
8


SELECT nomObst,libellé,noteins,bonus,noteins+bonus FROM passer AS p,soldat AS sol, participation AS partic, niveaudiff as niv,obstacle AS obst, soldat AS ins WHERE sol.idsoldat=partic.idsoldat AND partic.idPartic=p.idPartic AND p.idObst=obst.idObst AND obst.codeniv=niv.idnivdif AND ins.idsoldat=p.idsold AND partic.idPartic=1 AND noteins+bonus>='10' 

nomObst 
libellé 
noteins 
bonus 
noteins+bonus 

combat
difficile
6
4
10

fosse
difficile
9
4
13

grimper
moyen
8
2
10

nager
facile
10
1
11


SELECT nomObst,libellé,noteins,bonus,noteins+bonus FROM passer AS p,soldat AS sol, participation AS partic, niveaudiff as niv,obstacle AS obst, soldat AS ins WHERE sol.idsoldat=partic.idsoldat AND partic.idPartic=p.idPartic AND p.idObst=obst.idObst AND obst.codeniv=niv.idnivdif AND ins.idsoldat=p.idsold AND partic.idPartic=1 AND noteins+bonus<'10' 


nomObst 
libellé 
noteins 
bonus 
noteins+bonus 

tirer
moyen
7
2
9

saut
facile
7
1
8



SELECT nomObst,noteins,idPartice FROM passer AS p,soldat AS sol, participation AS partic, niveaudiff as niv,obstacle AS obst, soldat AS ins WHERE sol.idsoldat=p.idPartice AND partic.idPartic=p.idPartice AND p.idObst=obst.idObst AND obst.codeniv=niv.idnivdif AND ins.idsoldat=p.idsold AND noteins='0' 


nomObst 
noteins 
idPartice 





SELECT nomObst,noteins,idPartice FROM passer AS p,soldat AS sol, participation AS partic, niveaudiff as niv,obstacle AS obst, soldat AS ins WHERE sol.idsoldat=p.idPartice AND partic.idPartic=p.idPartice AND p.idObst=obst.idObst AND obst.codeniv=niv.idnivdif AND ins.idsoldat=p.idsold AND noteins='10' 


nomObst 
noteins 
idPartice 

nager
10
1

fosse
10
2

nager
10
2

grimper
10
3

tirer
10
4

