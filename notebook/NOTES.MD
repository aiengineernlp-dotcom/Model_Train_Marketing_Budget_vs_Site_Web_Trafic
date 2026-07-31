# NOTION DE BRUITS

Un bruit (noises) ne veut pas toujours dire que le model est mauvais. 

# Situation ou on parle  du bruit
Il peut arrivé que le modèle prédise "Prediction = 2950" mais que la vraie valeur soit 3100.  

-> Tu ne dois pas dire immédiatement que "le modèle est faux". 
> Tu peux dire que "il existe probablement du bruit ou des variables que le modèle ne prend pas en compte"
> 

Pourquoi? Supposons que tu as ces données :
| Budget (k AED) | Visitors |
| -------------: | -------: |
|              5 |     1200 |
|              8 |     1850 |
|             12 |     2600 |
|             15 |     3100 |
|             20 |     4300 |
|             25 |     5000 |

Même si le budget augmente, le nombre de visiteurs n'augmente pas toujours exactement de la même quantité.
Pourquoi ?

Parce que d'autres facteurs interviennent :

la qualité de la campagne marketing ;
la saison ;
les jours fériés ;
la concurrence ;
le référencement naturel (SEO) ;
les réseaux sociaux ;
le hasard.

Toutes ces influences que ton modèle ne connaît pas sont perçues comme du bruit.

Comment cette information m'aide? c'est a dire le fait de savoir que tu as le bruit dans tes données

1. Elle m'empêche de croire que le modèle est mauvais 
    -> "Prediction = 2950" mais que la vraie valeur soit 3100.  
2. Elle explique pourquoi le R² n'est pas égal à 1. 
   ->Car si les donnees sont bruitées la droite parfaite n'existe plus, tu obtiendras peut-etre R² = 0.94 au lieu de R²=1
3. Elle montre les limites du modèle
    -> Imagine deux campagnes et les deux dépensent 20 k AED mais obtiennent 4300 visiteurs et 3800 visiteurs 
    -> Pourquoi? alors que le budget est identique
    -> On traduit en disant que il existe forcement une autre variable qui influence le resultat
    -> Le bruit te dit : "Attention, ton modèle ne voit pas toute la réalité." 
4. Elle t'aide à choisir un meilleur modèle
   -> Si les points ressemblent à ça :
*
 *
  *
   *
    *
c'est une droite parfaite

    -> Mais si les points ressemblent à ça :
*
 *
  *
     *
        *
             *
une droite devient moins adaptée.
Tu peux alors essayer :

une régression polynomiale ;
un arbre de décision ;
une forêt aléatoire ;
un autre modèle plus flexible.

Le bruit t'aide donc à réfléchir au choix du modèle.

5. Elle t'aide à détecter les valeurs aberrantes (outliers)
  -> Regarde :
| Budget | Visitors |
| -----: | -------: |
|      5 |     1200 |
|      8 |     1850 |
|     12 |     2600 |
|     15 | **9000** |
|     20 |     4300 |
|     25 |     5000 |

Le point 15 → 9000
semble très étrange.

Tu te demandes alors :

est-ce une erreur de saisie ?
une campagne exceptionnelle ?
une donnée incorrecte ?

Le bruit t'incite à examiner les données avant d'entraîner le modèle.
Dois-tu supprimer le bruit ?

Pas forcément.

En pratique :

un bruit normal, on le garde ;
une erreur de mesure, on la corrige ou on la supprime ;
une valeur aberrante, on l'analyse avant de décider.


# Ce qu'un recruteur attend souvent

S'il te demande :

"Your data contains noise. What does that mean?"

Une bonne réponse est :

It means that the relationship between the input and the target is not perfectly deterministic. Other factors, 
measurement errors, or random variations may affect the target variable. A linear regression model tries to capture the 
overall trend, not every individual observation.

# =====================================================================================================================================================================

