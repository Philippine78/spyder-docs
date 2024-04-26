from datetime import datetime, timedelta

# Définition de la date de début du projet
date_debut = datetime(2024, 5, 1)

# Définition de la durée de chaque phase du projet en jours
duree_phase = {
    "Analyse SWOT et définition des objectifs": 28,
    "Lancement des campagnes publicitaires": 14,
    "Optimisation du site web": 14,
    "Organisation d'événements promotionnels": 14,
    "Collecte et analyse des données": 14,
    "Collaboration avec des influenceurs": 14,
    "Lancement de la campagne de fidélisation": 14,
    "Suivi et ajustement continu": 28
}

# Calcul de la date de fin de chaque phase
date_fin = {phase: date_debut + timedelta(days=duree) for phase, duree in duree_phase.items()}

# Affichage du rétroplanning
for phase, date in date_fin.items():
    print(f"{phase} : du {date_debut.strftime('%d/%m/%Y')} au {date.strftime('%d/%m/%Y')}")
    date_debut = date + timedelta(days=1)
