# 🛡️ Rapport technique – Cybersécurité
# Sommaire
## Contexte
## Objectifs
## Architecture
## Tests réalisés
## Recommandations

[Nom de la section](Contexte-du-projet)


## 📌 Contexte du projet
Ce rapport présente les mesures de cybersécurité mises en œuvre dans le cadre du projet [Nom du projet], réalisé dans un environnement AWS. Il couvre les aspects liés à la protection des données, à la gestion des identités, et à la surveillance des ressources.
## 🎯 Objectifs
- Renforcer la sécurité des données stockées
- Implémenter des mécanismes de contrôle d’accès
- Assurer la traçabilité des actions
- Tester la résilience des services

---

## 🧩 Architecture de sécurité

✅ Test de versioning réussi

✅ :white_check_mark: → ✅

🟢 :green_circle: → 🟢

✔️ :heavy_check_mark: → ✔️

Voici une phrase avec une note de bas de page[^1].

Une autre phrase avec une deuxième note[^2].

[^1]: Ceci est le texte de la note de bas de page n°1.
[^2]: Et voici la note de bas de page n°2.



## tableau & image 
**Nom:** gerald 

| 🔐 Nom de la policy       | 🎯 Objectif principal                  | 📁 Ressource ciblée       | 🧑‍💻 Actions autorisées         | 🛡️ Type de policy | 📝 Commentaire |
|--------------------------|----------------------------------------|---------------------------|-------------------------------|------------------|----------------|
| `S3ReadOnlyPolicy`       | Lecture seule sur les buckets S3       | `arn:aws:s3:::*`          | `s3:GetObject`, `s3:ListBucket` | Managed AWS      | Utilisée pour les auditeurs |
| `EC2AdminPolicy`         | Gestion complète des instances EC2     | `arn:aws:ec2:::*`         | `ec2:*`                        | Custom           | Réservée aux admins |
| `LambdaInvokePolicy`     | Invocation des fonctions Lambda        | `arn:aws:lambda:::*`      | `lambda:InvokeFunction`        | Inline           | Attachée à un rôle spécifique |
| `DenyS3DeletePolicy`     | Interdiction de suppression S3         | `arn:aws:s3:::data-bucket/*` | `s3:DeleteObject`           | Inline           | Utilisée pour protéger les logs |
| `CloudTrailAuditPolicy`  | Accès aux logs CloudTrail              | `arn:aws:cloudtrail:::*`  | `cloudtrail:LookupEvents`      | Managed AWS      | Pour les analystes sécurité |

Sources : [Documentation IAM AWS](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)




```mermaid
graph TD;
    A[Start] --> B[sudo apt-get update ];







