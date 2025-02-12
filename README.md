# Algorithme Espérance-Maximisation
## Simulation 

Dans cette partie nous cherchons à simuler deux échantillons de loi de Poisson avec des paramètres $\lambda$ différents en R pour ensuite simuler un mélange de lois de Poisson à deux composantes :

$$
P(x) = \pi_1 \frac{e^{-\lambda_1} \lambda_1^x}{x!} + \pi_2 \frac{e^{-\lambda_2} \lambda_2^x}{x!}
$$

avec $\lambda_1 = 3$, $\lambda_2 = 15$ et $\pi_1 = 0.4$

## Algorithme EM pour une mélange de lois de Poisson à K composantes

L'algorithme Expectation-Maximization (EM) est une approche puissante pour estimer les paramètres d'un modèle probabiliste lorsque les données sont incomplètes ou contiennent des variables latentes. 

Ici dans cette partie on cherche à Programmer l'étape E et l'étape M de l'algorithme EM et on cherche à le tester sur les données simulées dans la partie précédente. On effectue l'algorithme EM sur un mélange de lois de Poisson à K composantes. 

### Modèle de Mélange de Lois de Poisson

Un mélange de lois de Poisson à K composantes est défini comme suit :

$$
p(x) = \sum_{k=1}^{K} \pi_k Poisson(x|\lambda_k)
$$

où : 

- x est une observation.
- $\pi_k$ est le poids de la composante k (avec $\sum_{k=1}^{K} \pi_k = 1$)
- $\lambda_k$ est le paramètre de la loi de Poisson pour la composante k.

### Algorithme EM

L'algorithme EM alterne entre deux étapes : l'étape E (Expectation) et l'étape M (Maximization).

#### Étape E (Expectation)

Dans cette étape, nous calculons la probabilité que chaque observation $x_i$ appartienne à chaque composante k. Cette probabilité est donnée par :

$$
\gamma_{ik} = \frac{\pi_k Poisson(x_i | \lambda_k)}{\sum_{j=1}^{K} \pi_j Poisson(x_i, \lambda_j)}
$$

Où $\gamma_{ik}$ est la responsabilité de la composante k pour l'observation $x_i$.

#### Etape M (Maximization) 

Dans cette étape, nous mettons à jour les paramètres du modèle en maximisant la vraisemblance attendue. Les nouvelles estimations des paramètres sont données par :

$$
\pi_k = \frac{\sum_{i=1}^{N} \gamma_{ik}}{N}
$$

$$
\lambda_k = \frac{\sum_{i=1}^{N}\gamma_{ik}x_i}{\sum_{i=1}^{N} \gamma_{ik}}
$$

Où N est le nombre total d'observations.

#### Algorithme Complet
