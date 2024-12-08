# Algorithme Espérance-Maximisation
## Simulation 

Dans cette partie nous cherchons à simuler deux échantillons de loi de Poisson avec des paramètres $\lambda$ différents en R pour ensuite simuler un mélange de lois de Poisson à deux composantes :

\[
P(x) = \pi_1 \frac{e^{-\lambda_1} \lambda_1^x}{x!} + \pi_2 \frac{e^{-\lambda_2} \lambda_2^x}{x!}
\]

avec $\lambda_1 = 3$, $\lambda_2 = 15$ et $\pi_1 = 0.4$

## Algorithme EM pour une mélange de lois de Poisson à K composantes

Ici dans cette partie On cherche à Programmer l'étape E et l'étape M de l'algorithme EM et on cherche à le tester sur les données simulées dans la partie précédente. 



