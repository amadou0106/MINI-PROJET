import re
from collections import Counter

def compter_mots(texte):
    # Utilisez une expression régulière pour diviser le texte en mots
    mots = re.findall(r'\w+', texte.lower()) 
    
    # Utilisez Counter pour compter les occurrences de chaque mot
    compteur = Counter(mots)

    # Triez les mots par nombre d'occurrences (du plus fréquent au moins fréquent)
    mots_tries = sorted(compteur.items(), key=lambda item: item[1], reverse=True)

    return mots_tries

texte = "la maison de la petite souris"
resultat = compter_mots(texte)
for mot, occurrence in resultat:
    print(f"{mot}: {occurrence}")

def supprimer_mots_parasites(structure_donnees, mots_parasites):
    mots_filtrés = [(mot, occurrence) for mot, occurrence in structure_donnees if mot not in mots_parasites]
    return mots_filtrés


structure_donnees = [("le", 3), ("chat", 5), ("la", 2), ("souris", 4), ("les", 1)]
mots_parasites = ["le", "la", "les"]

resultat_filtre = supprimer_mots_parasites(structure_donnees, mots_parasites)
for mot, occurrence in resultat_filtre:
    print(f"{mot}: {occurrence}")

import csv

def recuperer_mots_parasites(chemin_fichier):
    mots_parasites = []
    
    try:
        with open(chemin_fichier, 'r', newline='', encoding='utf-8') as fichier_csv:
            lecteur_csv = csv.reader(fichier_csv)
            for ligne in lecteur_csv:
                if ligne:
                    mot_parasite = ligne[0]  # Supposons que les mots parasites se trouvent dans la première colonne
                    mots_parasites.append(mot_parasite)
    except FileNotFoundError:
        print(f"Le fichier {chemin_fichier} n'a pas été trouvé.")
    
    return mots_parasites

chemin_fichier_csv = 'parasite.csv'
mots_parasites = recuperer_mots_parasites(chemin_fichier_csv)
print("Mots parasites lus depuis le fichier CSV :")
print(mots_parasites)


