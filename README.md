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
## Méthodo du 12/02/25
🚀 Getting Started with Git & GitHub
Step 1: Create Your GitHub Account
If you haven’t already, sign up for a GitHub account here 👉 GitHub Sign Up
Step 2: Install Git
Download and install Git on your computer 👉 Git Download
Step 3: Let’s Create Your FIRST Project!
1️⃣ Create a New Repository on GitHub
Go to GitHub and click on "New Repository"
Name it first_project
⚠️ Important: Do not check the box "Add a README"
Click "Create Repository" and copy the repository URL
2️⃣ Set Up Your Project Locally
Now, let’s create your project on your computer:
Create a folder on your machine (name it as you like)
Open your terminal in that fold
Run these commands one by one :
echo "# first project demo" >> README.md  
git init                                   
git add README.md                          
git commit -m "first commit"               
git branch -M main                        
git remote add origin "URL_OF_THE_REPOSITORY"  
git push -u origin main                    
Congratulations! You’ve just pushed your first project to GitHub with a README file! 🎉
Step 4: Add your first python script
Now, let’s add and push your first Python file to the repository.
1️⃣ Create a new file in your folder named data_exploratory.py
2️⃣ Add some Python code inside it (even a simple print statement works!)
3️⃣ Push it to GitHub using:
git add data_exploratory.py                 
git commit -m "Add data exploration script"  
git push origin main     

🚀 Step-by-Step Guide to Creating, Merging, and Deleting a Git Branch        
git branch feature_experiment  # Create a new branch
git checkout feature_experiment  # Move to the new branch
git add .  # Stage all changes
git commit -m "Added experimental feature"
git push origin feature_experiment
git checkout main  # Switch to main
git merge feature_experiment  # Merge branch into main
git push origin main  # Push updated main branch to remote
git branch -d feature_experiment  # Delete local branch
git push origin --delete feature_experiment  # Delete remote branch




🔧 Having Trouble Pushing? Let’s Set Up SSH Access
If you run into issues pushing your code, it’s likely because GitHub requires authentication. Instead of using HTTPS, let’s configure SSH access to GitHub.

Open your terminal (Git Bash, VS Code, or another terminal) and run:
ssh-keygen -t ed25519 -C "your_email@example.com"
Press Enter when prompted (twice)
A magic message will appear 🔑 This means your key is generated!

|  ..             |
| .+              |
|oo o         .   |
|o+oo o o    = o  |
|+o*.+ + S  = B . |
|oB++o.oo  + B E .|
|=oo. + +.. o o + |
|. . . . o     .  |
+----[SHA256]-----+


On your terminal, run the following command: cat ~/.ssh/id_ed25519.pub
Copy the entire key that appears on the screen. 
Go back to your GitHub account and go to Settings > SSH and GPG keys.
Click on New SSH key.
Give a name to your key and Paste the SSH key there.







Now, let’s check if the SSH setup is working:
ssh -T git@github.com
Now, update Git to use SSH instead of HTTPS:
git remote set-url origin git@github.com:username/repo.git
git config --global user.name "username"
