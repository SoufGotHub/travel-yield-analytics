# Travel Yield Analytics

Analyse de yield management pour un tour-operateur : preparation des donnees de reservation, tableau de bord Power BI et prediction de la marge nette par passager avec XGBoost.

Le projet vise a identifier les leviers de rentabilite lies aux reseaux de distribution, aux destinations, a la saisonnalite, aux delais de reservation et au prix des sejours.

## Objectifs

- Fiabiliser et exploiter une base de reservations touristiques.
- Suivre le chiffre d'affaires, les achats, les commissions et la marge nette dans Power BI.
- Mettre en evidence les axes de performance par reseau, destination, hotel, ville de depart et periode.
- Predire la marge nette par passager afin d'appuyer les decisions de pricing et de yield management.

## Donnees

Le jeu de donnees nettoye contient **18 620 reservations** et 17 colonnes, dont :

- hotel, reference de dossier, dates de reservation et de depart ;
- reseau et regroupement de reseau (`B2B`, `B2C`, `GROUPES`) ;
- nombre d'adultes et d'enfants, villes de depart et d'arrivee, destination et nombre de nuits ;
- prix brut TTC, compagnie aerienne, achats previsionnels, commission et marge nette.

Les donnees presentes dans ce depot sont fournies dans le cadre de ce projet analytique.

## Resultats du modele

La version finale du modele, `NG_Travel_modele_marge_XGBoost_v3.ipynb`, predit la **marge nette par passager** a partir des variables de reservation et de vente : delai de reservation, nombre de passagers, nombre de nuits, prix brut TTC, destination, reseau, regroupement de reseau et saison de depart.

| Metrique sur le jeu de test | Resultat |
| --- | ---: |
| R2 | 0,727 |
| MAE | 87,27 EUR |
| RMSE | 121,14 EUR |

Le notebook v2 documente une premiere version du modele ; le notebook v3 correspond a la version enrichie et finale.

## Contenu du depot

```text
.
|- Rapp_NG_TR.pbix                         # Rapport Power BI
|- NG_Travel_modele_marge_XGBoost_v2.ipynb # Premiere version du modele XGBoost
|- NG_Travel_modele_marge_XGBoost_v3.ipynb # Version finale du modele XGBoost
|- donnees_nettoyees.csv                   # Donnees nettoyees utilisees par l'analyse
|- donnees_nettoyees.xlsx                  # Donnees nettoyees au format Excel
|- base_de_donnees.xlsx                    # Base source du projet
`- README.md
```

## Outils

- Python : `pandas`, `numpy`, `scikit-learn`, `xgboost`, `matplotlib`, `seaborn`
- Jupyter Notebook / Google Colab
- Power BI : Power Query et DAX

## Utilisation

1. Ouvrir `Rapp_NG_TR.pbix` avec Power BI Desktop pour consulter le rapport.
2. Ouvrir le notebook v3 dans Jupyter ou Google Colab pour reproduire la modelisation.
3. Dans le notebook, ajuster au besoin la variable `FILE_PATH` afin qu'elle pointe vers `donnees_nettoyees.csv` sur votre environnement.

## Auteur

Soufiane - [SoufGotHub](https://github.com/SoufGotHub)
