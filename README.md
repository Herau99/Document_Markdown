# 📦 Ingest Pipeline – `pipeline-fleet-final-v1`

## 🧾 Objectif

Cette pipeline est utilisée pour **traiter les événements collectés par Elastic Agent via Fleet**, avant leur indexation dans Elasticsearch. Elle applique les transformations finales nécessaires à la normalisation, l’enrichissement ou le filtrage des données.

---

## 🧱 Nomenclature

| Élément        | Valeur                  | Description                                      |
|----------------|--------------------------|--------------------------------------------------|
| Type           | `pipeline`               | Type d’objet Elasticsearch                       |
| Source         | `fleet`                  | Origine des données (Elastic Agent via Fleet)    |
| Fonction       | `final`                  | Étape finale de traitement avant indexation      |
| Version        | `v1`                     | Version de la pipeline                           |
| Nom complet    | `pipeline-fleet-final-v1`| Nom recommandé pour clarté et traçabilité        |

---

## ⚙️ Processors utilisés

Liste des transformations appliquées par la pipeline :

| Ordre | Processor         | Description                                                                 |
|-------|-------------------|-----------------------------------------------------------------------------|
| 1     | `set`             | Ajoute ou modifie un champ spécifique                                       |
| 2     | `rename`          | Renomme un champ pour correspondre au mapping cible                         |
| 3     | `remove`          | Supprime les champs inutiles ou sensibles                                   |
| 4     | `geoip` *(optionnel)* | Ajoute des données géographiques à partir d’une adresse IP (si activé)     |
| 5     | `date` *(optionnel)*  | Convertit un champ texte en format date Elasticsearch                     |

> 💡 Pour voir la configuration exacte :
> ```bash
> GET _ingest/pipeline/.fleet_final_pipeline-1
> ```

---

## 🧪 Exemple d’usage

Cette pipeline est automatiquement utilisée par les **data streams gérés par Fleet**, comme :

- `logs-system.*`
- `logs-elastic_agent.*`
- `metrics-system.*`

---

## 🛠️ Étapes pour renommer la pipeline

Elasticsearch ne permet pas de renommer une pipeline directement. Voici comment procéder :

1. **Exporter la configuration actuelle** :
   ```bash
   GET _ingest/pipeline/.fleet_final_pipeline-1


