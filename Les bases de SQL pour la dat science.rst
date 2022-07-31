
SELECT Major, ShareWomen, Employed -- Selectionner les colonnes : Major, ShareWomen, Employed
FROM recent_grads  -- Dans la table " recent_grads"

LIMIT 10 -- selctionner les 10 premiéres lignes 
;

-----------------------------------------------
SELECT Major, ShareWomen, Employed --- selectionner les colonnes : Major, ShareWomen, Employed
FROM recent_grads --- Dans la table 'recent_grads'
WHERE ShareWomen>0.5 --- selectionner que des femmes dans la plupart de diplômés. Sur l'ensemble des diplômés, il y a plus de 50% des femmes
;

------------------------------------------------------
SELECT Major, ShareWomen, Employed -- selectionner les colonnes : Major, ShareWomen, Employed 
FROM recent_grads
WHERE ShareWomen>0.5 and Employed>10000 -- afficher la plupart des femmes qui ont plus de 10000 emplois
LIMIT 10 -- limiter les résultats à 10
;

-----------------------------------------------------
SELECT Major, Median, Unemployed
FROM recent_grads
WHERE  Median>=10000 or Unemployed<=1000 -- Appliquer une de deux conditions à savoir le salaire median >=10000 ou les non employés <= 1000
LIMIT 20
;

--------------------------------------------------

SELECT Major, Major_category, ShareWomen, Unemployment_rate
FROM recent_grads
WHERE (Major_category="Engineering") and (ShareWomen >=0.5 or Unemployment_rate<0.051) -- Utilisation des parenthèses pour simplifier les multiples conditions
;

------------------------------------------------------------------------------

SELECT Major, Major_category, Employed, Unemployment_rate
FROM recent_grads
WHERE (Major_category="Business" or Major_category="Arts" or Major_category="Health") -- utilisation des guillemets pour les chaines de caractéres
and (Employed >20000 or Unemployment_rate<0.051)
;

--------------------------------------------------------

SELECT Major
FROM recent_grads
ORDER BY Major DESC -- trier par ordre décroissant
;

SELECT Major_category, Median, Major
FROM recent_grads
ORDER BY Major_category ASC, Median DESC -- trier plusier colonnes seleon différents ordres
LIMIT 20
;
