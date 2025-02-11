# Arthur_testing
## Test full stack
Notebook Python avec les exos du 10/02/2025
### try_1.ipynb 
*Contient la fonction pour calculer les intérêts d'un placements financier*


```
    def Columbus():
        try:
            #Définition des inputs
            placement=float(input("Cb voualez vous placer?"))
            print("Vous désirez placer {:.2f} €".format(placement))
            temps=int(input("Sur cb d'année?"))
            print("Votre placement de {:.2f} € s'étalera sur {} ans".format(placement,temps))
            taux_intérêt=float(input("A quel taux? Par exemple, pour 10% entrez 0.1"))
            print("Vous souhaitez placer {:.2f} € sur {} ans à un taux de {:.2f}".format(placement,temps,taux_intérêt))

        except ValueError:
            raise ValueError("Veuillez rensigner des nombres")
        else:
            if placement < 0 or temps < 0 or taux_intérêt < 0:
                raise ValueError ("Veuillez entrer des valeurs supérieures à 0")
            if taux_intérêt > 1:
                raise ValueError("Plus de 100% d'intérêt  c'est compliqué, veuillez entrer un taux entre 0 et 1")


        #Calcul des intérêts
        intérêts = placement*(1+taux_intérêt)**temps
        print("Sur {} ans, votre placement de {} € à un taux d'intérêt de {} vous rapportera {:.2f} €".format(temps,placement,taux_intérêt,intérêts))
```
### quizz.ipynb
*Contient le quizz*
```
def poser_question(question, reponse_correcte, vies):
    print(question)
    reponse = input(question).strip().lower()
    while reponse != reponse_correcte:
        vies -= 1
        print(f"Votre réponse est : {reponse}")
        print("NUUUUUUUUUUUUUl")
        print(f"Il vous reste {vies} vies.")
        if vies == 0:
            print("The end, Terminus, Game Over")
            return 0
        reponse = input(question).strip().lower()
    print(f"Votre réponse est : {reponse}")
    print("GGWP")
    print(f"Il vous reste {vies} vies.")
    return vies

def lancer_quiz(questions):
    vies = 3
    print(f"{len(questions)} questions primordiales en {vies} vies :")

    for question, reponse_correcte in questions:
        vies = poser_question(question, reponse_correcte, vies)
        if vies == 0:
            exit()

    print("Félicitations !")
    print(f"Vous avez terminé le quizz avec {vies} vie(s).")

# Liste des questions et réponses
questions = [
    ("Quelle est la couleur du cheval blanc d'Henry IV?", "blanc"),
    ("Qu'est-ce que la mère Michelle a perdu?", "son chat"),
    ("Qu'est ce qu'il a dans sa vilaine petite poche?", "mon précieux")
]

# Lancer le quiz
lancer_quiz(questions)
```
