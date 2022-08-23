#!/bin/bash

echo ""
echo "Bonjour $USER,"
echo "Ce script à été réalisé par Ixernoss." 
echo "Si vous avez besoin d'aide il faut écrire help."
read -p "Que voulez-vous faire ? " task
echo ""
if [ "$task" == "ID" ]
then
    read -p "Votre nom rp : " nom
    if [ -z "$nom" ]
    then
        echo "Le nom est inexistant"
        exit
    fi
    read -p "Votre prénom rp : " prenom
    if [ -z "$prenom" ]
    then
        echo "Le prénom est inexistant"
        exit
    fi
    read -p "Votre année de naissance rp : " date
    if [ -z "$date" ]
    then
        echo "La dare de naissance est inexistant"
        exit
    fi
    read -p "Votre sexe rp [H/F] : " sexe
    if [ -z "$sexe" ]
    then
        echo "Le sexe est inexistant"
        exit
    elif [ "$sexe" != "F" ] && [ "$sexe" != "H" ] && [ "$sexe" != "f" ] && [ "$sexe" != "h" ]
    then
        echo "Erreur sur le sexe de la personnes"
        exit
    fi
    echo "Nom : $nom" >> CarteID.txt
    echo "Prénom : $prenom" >> CarteID.txt
    echo "Date de Naissance : $date" >> CarteID.txt
    echo "Sexe : $sexe" >> CarteID.txt
elif [ "$task" == "job" ]
then
    read -p "Votre nom rp : " nom
    if [ -z "$nom" ]
    then
        echo "Le nom est inexistant"
        exit
    fi
    read -p "Votre prénom rp : " prenom
    if [ -z "$prenom" ]
    then
        echo "Le prénom est inexistant"
        exit
    fi
    read -p "Votre age rp : " age
    if [ -z "$age" ]
    then
        echo "Le age est inexistant"
        exit
    elif [ "$age" -gt 18 ]
    then
        echo "Vous ne pouvez pas traviller car vous êtes mineur."
    fi
    read -p "Quel métier voulez-vous faire : " job
    if [ -z "$job" ]
    then
        echo "Le travail est inexistant"
        exit
    elif [ "$job" != "taxi" ] && [ "$job" != "secu" ] && [ "$job" != "pn" ] && [ "$job" != "sp" ] && [ "$job" != "routier" ]
    then
        echo "Ces Jobs n'existe pas."
    fi
elif [ "$task" == "help" ]
then
    echo 
    echo "      ID  --> Carte d'Identité"     
    exit
else
    echo "Erreur si vous avez besoin d'aide écrivez help"
    exit
fi
echo ""
read -p "Voulez vous nettoyer votre terminal : " nettoyer
if [ "$nettoyer" == "oui" ]
then
    clear
elif [ "$nettoyer" == "o" ]
then
    clear
else
    exit
fi

### By Yann Rimezt ###
