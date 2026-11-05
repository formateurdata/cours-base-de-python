# Données Vélib’ utilisées dans les séances

Source : [Paris Data — Vélib’, vélos et bornes, disponibilité](https://opendata.paris.fr/explore/dataset/velib-disponibilite-en-temps-reel/information/). Producteur indiqué sur la page : Smovengo / Syndicat Autolib’ Vélib’ Métropole.

La réponse a été téléchargée le **22 octobre 2026 à 11 h 31 min 33 s UTC**, soit 13 h 31 min 33 s à Paris. Les observations ont chacune leur propre horodatage dans `duedate`. Le téléchargement ne signifie pas que toutes les stations ont été actualisées à cette heure.

Requête conservée :

```text
https://opendata.paris.fr/api/explore/v2.1/catalog/datasets/velib-disponibilite-en-temps-reel/records?limit=8&order_by=stationcode
```

Le fichier `velib_source.json` contient la réponse brute. `velib.csv` contient les huit fiches avec des noms de colonnes français ; aucune disponibilité n’a été inventée ou actualisée. `resultats_attendus.json` contient les agrégats calculés et l’empreinte SHA-256 du fichier brut.

Les huit lignes ont été choisies par la limite et le tri de cette requête. L’extrait n’est pas un échantillon représentatif du réseau. Les valeurs du cours décrivent cet extrait daté, pas la disponibilité actuelle.

| Colonne du CSV | Champ de la réponse | Ce qui est conservé |
| --- | --- | --- |
| `code` | `stationcode` | Identifiant texte |
| `nom` | `name` | Nom |
| `capacite` | `capacity` | Capacité indiquée |
| `velos` | `numbikesavailable` | Vélos disponibles |
| `mecaniques` | `mechanical` | Vélos mécaniques disponibles |
| `electriques` | `ebike` | Vélos électriques disponibles |
| `bornes_libres` | `numdocksavailable` | Bornes disponibles |
| `mise_a_jour` | `duedate` | Horodatage de la fiche |

Le nombre de bornes libres n’est pas calculé par différence entre capacité et vélos : la source le fournit séparément et certaines places peuvent ne pas être disponibles.

Dans les séances 8 et 9, `velib_groupe_a.csv` correspond aux quatre premières lignes et `velib_groupe_b.csv` aux quatre suivantes. Les deux groupes sont disjoints et viennent de la même réponse. Ils ne représentent pas deux dates.

Les exemples simplifiés des séances 1 à 5 recopient des champs de cette même réponse. Les fiches fictives des tests sont explicitement nommées comme telles et ne sont pas ajoutées aux données réelles.

Les données sont fournies dans les dossiers des séances qui les lisent. Aucun appel réseau n’est exécuté dans les notebooks.
