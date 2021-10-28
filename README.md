# papi-gelato
## F1.5.02.O2
``` python
print("Welkom bij Papi Gelato")
print("Je mag alle smaken kiezen zolang het maar vanille ijs is")
def snapIkNiet():
    print("Sorry, dat snap ik niet") 
def vraagMeerBestellen(bolletjes,hornOfBak,repeatOrNot):
    print("Hier is uw " + hornOfBak + " met " + str(bolletjes), "bolletjes.")
    repeatOrNot = input("Wilt u nog meer bestellen? (Y/N): ")
    if repeatOrNot == "Y" or repeatOrNot == "y":
        vraagHoeveelheidBolletjes(0)
    elif repeatOrNot == "N" or repeatOrNot == "n":
        print("Bedankt en tot ziens!")        
    else:
        snapIkNiet()
        vraagMeerBestellen(bolletjes,hornOfBak,repeatOrNot)
def vraagHornOfBak(hornOfBak,bolletjes):
    hornOfBak = input("Wilt u deze " + str(bolletjes) + " bolletjes in (A) een hoorntje of (B) een bakje? ")
    if hornOfBak == "A" or hornOfBak == "a":
        vraagMeerBestellen(str(bolletjes),"hoorntje","")
    elif hornOfBak == "B" or hornOfBak == "b":
        vraagMeerBestellen(str(bolletjes),"bakje","")
    else:
        snapIkNiet()
        vraagHornOfBak("", bolletjes)
def vraagHoeveelheidBolletjes(bolletjes):
    bolletjes = input("Hoeveel bolletjes wilt u? ")
    if int(bolletjes) <= 3:
        vraagHornOfBak("", bolletjes)
    elif int(bolletjes) <=8: 
        print("Dan krijgt u van mij een bakje met " + str(bolletjes) + " bolletjes.")
        vraagMeerBestellen(bolletjes, "bak", "") 
    elif int(bolletjes) <=9:
        print("Sorry, zulke grote bakken hebben we niet") 
        vraagHoeveelheidBolletjes(0)
    else:
        snapIkNiet()
        vraagHoeveelheidBolletjes(0)
vraagHoeveelheidBolletjes(0)
```
