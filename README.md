Il permet aux utilisateurs de créer des comptes clients, d'afficher les détails du compte, d'effectuer des dépôts et d'effectuer des retraits.

Le projet sama bank est une application efficace et conviviale. Le projet est une application bancaire simple qui permet aux utilisateurs d'effectuer diverses opérations bancaires comme la recherche de numéros de compte, l'affichage de tous les comptes, le dépôt et le retrait d'argent, etc.

Avec ce projet, il existe une trésorerie sécurisée dans le système bancaire. Il permet de créer et de gérer des comptes bancaires avec des opérations de base.

Création de comptes :
  • Les utilisateurs précisent le nombre de comptes bancaires qu'ils souhaitent créer.
  • Pour chaque compte, les utilisateurs fournissent le numéro de compte, le nom du titulaire du compte et le solde initial.

Menu principal :
  • Les utilisateurs se voient présenter un menu dans lequel ils peuvent choisir parmi cinq options (1 à 5).

Afficher tous les comptes (Option 1) :
  • Il affiche le numéro de compte, le nom du titulaire du compte et le solde de chaque compte.

Recherche par numéro de compte (Option 2) :
•Les utilisateurs peuvent saisir un numéro de compte pour rechercher un compte spécifique. Si le compte est trouvé, il affiche les détails de ce compte, y compris le numéro de compte, le nom du titulaire du compte et le solde. Si le compte n'est pas trouvé, un message indiquant « Échec de la recherche : compte introuvable » s'affiche.

Déposer de l'argent (Option 3) :
• Les utilisateurs peuvent saisir un numéro de compte pour spécifier où ils souhaitent déposer de l'argent. Si le compte est trouvé, les utilisateurs peuvent saisir le montant à déposer.
Le solde du compte est mis à jour en ajoutant le montant déposé.

Retirer de l'argent (Option 4) :
• Les utilisateurs peuvent saisir un numéro de compte pour spécifier où ils souhaitent retirer de l'argent. Le solde du compte est mis à jour en soustrayant le montant retiré.

Quitter l'application (Option 5) :
• Les utilisateurs peuvent choisir cette option pour quitter l'application bancaire.

Sortie : Le programme affiche tous les comptes et les informations associées aux comptes.

 

importer java.util.Scanner ; 

classe Banque { 
    chaîne privée numéro de compte ; 
    chaîne privée accountHolderName ; 
    Solde du compte long privé ; 

    Scanner scanner = nouveau scanner (System.in); 

    // Méthode pour ouvrir un compte 
    void openAccount() { 
        System.out.print("Enter Account Number: "); 
        numéro de compte = scanner.next(); 
        System.out.print("Entrez le nom du titulaire du compte : "); 
        accountHolderName = scanner.next(); 
        System.out.print("Entrez le solde du compte : "); 
        compteBalance = scanner.nextLong(); 
    } 

    // Méthode pour afficher les détails du compte 
    void showAccount() { 
        System.out.println("Account Number: " + accountNumber + ", Account Holder: " + accountHolderName + ", Balance: " + accountBalance); 
    } 

    // Méthode pour déposer de l'argent 
    void deposit() { 
        long montant; 
        System.out.print("Entrez le montant que vous souhaitez déposer : "); 
        montant = scanner.nextLong(); 
        solde du compte += montant ; 
    } 

    // Méthode pour retirer de l'argent 
    void retrait() { 
        long montant; 
        System.out.print("Entrez le montant que vous souhaitez retirer : "); 
        montant = scanner.nextLong(); 
        if (accountBalance >= montant) { 
            accountBalance -= montant ; 
        } else { 
            System.out.println("Solde insuffisant..Échec de la transaction.."); 
        } 
    } 

    // Méthode pour rechercher un compte par numéro de compte 
    boolean search(String accountNumberToFind) { 
        if (accountNumber.equals(accountNumberToFind)) { 
            showAccount(); 
            renvoie vrai ; 
        } 
        renvoie faux ; 
    } 
} 

public class ExBank { 
    public static void main(String args[]) { 
        Scanner scanner = new Scanner(System.in); 

        // Créer des comptes initiaux 
        System.out.print("Combien de clients vous souhaitez saisir : "); 
        int numberOfCustomers = scanner.nextInt(); 
        Comptes bancaires [] = nouvelle banque [numéro de clients] ; 
        pour (int i = 0; i < comptes.longueur; i++) { 
            comptes[i] = new Bank(); 
            comptes[i].openAccount(); 
        } 

        // Exécute la boucle jusqu'à ce que le menu 5 ne soit pas enfoncé. 
        int Choice ; 
        faire { 
            System.out.
            System.out.println("1. Afficher tous les comptes"); 
            System.out.println("2. Recherche par numéro de compte"); 
            System.out.println("3. Déposer de l'argent"); 
            System.out.println("4. Retirer de l'argent"); 
            System.out.println("5. Quitter"); 
            System.out.print("Votre choix : "); 
            choix = scanner.nextInt(); 
            switch (choix) { 
                cas 1 : 
                    for (int i = 0; i < comptes.length; i++) { 
                        comptes[i].showAccount(); 
                    } 
                    casser; 

                cas 2 : 
                    System.out.print ("Entrez le numéro de compte que vous souhaitez rechercher : "); 
                    Chaîne accountNumberToSearch = scanner.next(); 
                    booléen trouvé = faux ; 
                    pour (int i = 0; i < comptes.length; i++) { 
                        found = comptes[i].search(accountNumberToSearch); 
                        si (trouvé) { 
                            pause ; 
                        } 
                    } 
                    if (!found) { 
                        System.out.println("Échec de la recherche..Compte introuvable.."); 
                    } 
                    casser; 

                cas 3 : 
                    System.out.print("Entrez le numéro de compte à déposer : "); 
                    Chaîne accountNumberToDeposit = scanner.next(); 
                    trouvé = faux ; 
                    pour (int i = 0; i < comptes.length; i++) { 
                        found = comptes[i].search(accountNumberToDeposit); 
                        si (trouvé) { 
                            comptes[i].deposit(); 
                            casser; 
                        } 
                    } 
                    if (!found) { 
                        System.out.println("Échec de la recherche..Compte introuvable.."); 
                    } 
                    casser; 

                cas 4 : 
                    System.out.print("Entrez le numéro de compte à retirer : "); 
                    Chaîne accountNumberToWithdraw = scanner.next(); 
                    trouvé = faux ; 
                    pour (int i = 0; i < comptes.longueur; i++) { 
                        found = comptes[i]. recherche(accountNumberToWithdraw); 
                        si (trouvé) { 
                            comptes[i].withdrawal();
                            casser; 
                        } 
                    } 
                    if (!found) { 
                        System.out.println("Échec de la recherche..Compte introuvable.."); 
                    } 
                    casser; 

                cas 5 : 
                    System.out.println("Au revoir.."); 
                    casser; 

                par défaut : 
                    System.out.println("Choix invalide.."); 
            } 
        } while (choix != 5); 

        scanner.close(); 
    } 
}
