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
## F1.5.02.O3
Hier heb ik deze functie erbij geplaatst
```python
def vraagWelkeSmaak(bolletjes,smaak,nummerBolletje,hornOfBak):
    while nummerBolletje <= int(bolletjes):
        smaak = input("Welke smaak wilt u voor bolletje nummer " + str(nummerBolletje) + "? A)Aardbei, C)Chocolade, M)Munt, V)Vanille: ")
        if smaak == "A" or smaak == "C" or smaak == "M" or smaak == "V" or smaak == "a" or smaak == "c" or smaak == "m" or smaak == "v":
            nummerBolletje = nummerBolletje + 1
        else:
            snapIkNiet()
    if hornOfBak == "A":
        vraagMeerBestellen(bolletjes,"hoorntje","")
    else:
        vraagMeerBestellen(bolletjes,"bakje","")
```
Dit is nu de volledige programma
```python
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
def vraagWelkeSmaak(bolletjes,smaak,nummerBolletje,hornOfBak):
    while nummerBolletje <= int(bolletjes):
        smaak = input("Welke smaak wilt u voor bolletje nummer " + str(nummerBolletje) + "? A)Aardbei, C)Chocolade, M)Munt, V)Vanille: ")
        if smaak == "A" or smaak == "C" or smaak == "M" or smaak == "V" or smaak == "a" or smaak == "c" or smaak == "m" or smaak == "v":
            nummerBolletje = nummerBolletje + 1
        else:
            snapIkNiet()
    if hornOfBak == "A":
        vraagMeerBestellen(bolletjes,"hoorntje","")
    else:
        vraagMeerBestellen(bolletjes,"bakje","")
def vraagHornOfBak(hornOfBak,bolletjes):
    hornOfBak = input("Wilt u deze " + str(bolletjes) + " bolletjes in (A) een hoorntje of (B) een bakje? ")
    if hornOfBak == "A" or hornOfBak == "a":
        vraagWelkeSmaak(bolletjes,"",1,"A")
    elif hornOfBak == "B" or hornOfBak == "b":
        vraagWelkeSmaak(bolletjes,"",1,"B")
    else:
        snapIkNiet()
        vraagHornOfBak("", bolletjes)
def vraagHoeveelheidBolletjes(bolletjes):
    bolletjes = input("Hoeveel bolletjes wilt u? ")
    if int(bolletjes) <= 3:
        vraagHornOfBak("", bolletjes)
    elif int(bolletjes) <=8: 
        print("Dan krijgt u van mij een bakje met " + str(bolletjes) + " bolletjes.")
        vraagWelkeSmaak(bolletjes,"",1,"B")
    elif int(bolletjes) >=9:
        print("Sorry, zulke grote bakken hebben we niet") 
        vraagHoeveelheidBolletjes(0)
    else:
        snapIkNiet()
        vraagHoeveelheidBolletjes(0)
vraagHoeveelheidBolletjes(0)
```
### F1.5.02.O4
Hier heb ik alleen de text "Je mag alle smaken kiezen zolang het maar vanille ijs is" weggehaald, die op lijn 2 zat
```python
print("Welkom bij Papi Gelato")
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
def vraagWelkeSmaak(bolletjes,smaak,nummerBolletje,hornOfBak):
    while nummerBolletje <= int(bolletjes):
        smaak = input("Welke smaak wilt u voor bolletje nummer " + str(nummerBolletje) + "? A)Aardbei, C)Chocolade, M)Munt, V)Vanille: ")
        if smaak == "A" or smaak == "C" or smaak == "M" or smaak == "V" or smaak == "a" or smaak == "c" or smaak == "m" or smaak == "v":
            nummerBolletje = nummerBolletje + 1
        else:
            snapIkNiet()
    if hornOfBak == "A":
        vraagMeerBestellen(bolletjes,"hoorntje","")
    else:
        vraagMeerBestellen(bolletjes,"bakje","")
def vraagHornOfBak(hornOfBak,bolletjes):
    hornOfBak = input("Wilt u deze " + str(bolletjes) + " bolletjes in (A) een hoorntje of (B) een bakje? ")
    if hornOfBak == "A" or hornOfBak == "a":
        vraagWelkeSmaak(bolletjes,"",1,"A")
    elif hornOfBak == "B" or hornOfBak == "b":
        vraagWelkeSmaak(bolletjes,"",1,"B")
    else:
        snapIkNiet()
        vraagHornOfBak("", bolletjes)
def vraagHoeveelheidBolletjes(bolletjes):
    bolletjes = input("Hoeveel bolletjes wilt u? ")
    if int(bolletjes) <= 3:
        vraagHornOfBak("", bolletjes)
    elif int(bolletjes) <=8: 
        print("Dan krijgt u van mij een bakje met " + str(bolletjes) + " bolletjes.")
        vraagWelkeSmaak(bolletjes,"",1,"B")
    elif int(bolletjes) >=9:
        print("Sorry, zulke grote bakken hebben we niet") 
        vraagHoeveelheidBolletjes(0)
    else:
        snapIkNiet()
        vraagHoeveelheidBolletjes(0)
vraagHoeveelheidBolletjes(0)
```
## F1.5.02.O5
Ik heb deze functie erbij gemaakt
```python
def bon(bolletjes):
    prijsBolletje = 1.10
    prijsHoorntje = 1.25
    prijsBakje = 0.75
    global bakjes
    global hoorntjes
    print("-----------['Papi Gelato']-----------")
    print("")
    totaalPrijsBolletjes = prijsBolletje * bolletjes
    totaalPrijsHoorntjes = prijsHoorntje * hoorntjes
    totaalPrijsBakjes = prijsBakje * bakjes
    totaalPrijs = totaalPrijsBolletjes + totaalPrijsHoorntjes + totaalPrijsBakjes
    if int(bolletjes) > 0:
        print("Bolletjes        " + str(bolletjes) + " x €" + str('{0:.2f}'.format(prijsBolletje)) + "    = €" + str('{0:.2f}'.format(totaalPrijsBolletjes))) 
    if hoorntjes > 0:
        print("Hoorntjes        " + str(hoorntjes) + " x €" + str('{0:.2f}'.format(prijsHoorntje)) + "    = €" + str('{0:.2f}'.format(totaalPrijsHoorntjes))) 
    if bakjes > 0:
        print("Bakjes           " + str(bakjes) +    " x €" + str('{0:.2f}'.format(prijsBakje)) +    "    = €" + str('{0:.2f}'.format(totaalPrijsBakjes)))
    print    ("                              -------- +") 
    print    ("Totaal                        = €" + str('{0:.2f}'.format(totaalPrijs))) 
vraagHoeveelheidBolletjes()
```
Je ziet ook dat ik ('{0:.2f}'.format) hebt gebruikt. Dat is zodat hij het gedeelte wat achter de format staat, laat printen met 2 cijfers achter de komma
``` python
('{0:.2f}'.format)
```
Verder heb ik ook andere namen gegeven voor sommige variabelen, de global functie gebruikt en extra variabelen gemaakt. Dit is nu de volledige programma
``` python
print("Welkom bij Papi Gelato")
hoorntjes = 0
bakjes = 0
bolletjes = 0
def snapIkNiet():
    print("Sorry, dat snap ik niet") 
def vraagMeerBestellen(aantalBolletjes,hornOfBak,repeatOrNot):
    print("Hier is uw " + hornOfBak + " met " + str(aantalBolletjes), "bolletjes.")
    repeatOrNot = input("Wilt u nog meer bestellen? (Y/N): ")
    global bolletjes
    bolletjes = bolletjes + int(aantalBolletjes)
    if repeatOrNot == "Y" or repeatOrNot == "y":
        vraagHoeveelheidBolletjes()
    elif repeatOrNot == "N" or repeatOrNot == "n":
        bon(bolletjes)
        print("Bedankt en tot ziens!")        
    else:
        snapIkNiet()
        vraagMeerBestellen(bolletjes,hornOfBak,repeatOrNot)
def vraagWelkeSmaak(bolletjes,smaak,nummerBolletje,hornOfBak):
    while nummerBolletje <= int(bolletjes):
        smaak = input("Welke smaak wilt u voor bolletje nummer " + str(nummerBolletje) + "? A)Aardbei, C)Chocolade, M)Munt, V)Vanille: ")
        if smaak == "A" or smaak == "C" or smaak == "M" or smaak == "V" or smaak == "a" or smaak == "c" or smaak == "m" or smaak == "v":
            nummerBolletje = nummerBolletje + 1
        else:
            snapIkNiet()
    if hornOfBak == "A":
        global hoorntjes
        hoorntjes = hoorntjes + 1
        vraagMeerBestellen(bolletjes,"hoorntje","")
    else:
        global bakjes
        bakjes = bakjes + 1
        vraagMeerBestellen(bolletjes,"bakje","")
def vraagHornOfBak(hornOfBak,bolletjes):
    hornOfBak = input("Wilt u deze " + str(bolletjes) + " bolletjes in (A) een hoorntje of (B) een bakje? ")
    if hornOfBak == "A" or hornOfBak == "a":
        vraagWelkeSmaak(bolletjes,"",1,"A")
    elif hornOfBak == "B" or hornOfBak == "b":
        vraagWelkeSmaak(bolletjes,"",1,"B")
    else:
        snapIkNiet()
        vraagHornOfBak("", bolletjes)
def vraagHoeveelheidBolletjes():
    aantalBolletjes = input("Hoeveel bolletjes wilt u? ")
    if int(aantalBolletjes) <= 3:
        vraagHornOfBak("", aantalBolletjes)
    elif int(aantalBolletjes) <=8: 
        print("Dan krijgt u van mij een bakje met " + str(aantalBolletjes) + " bolletjes.")
        global bakjes
        bakjes = bakjes + 1
        vraagWelkeSmaak(aantalBolletjes,"",1,"B")
    elif int(aantalBolletjes) >=9:
        print("Sorry, zulke grote bakken hebben we niet") 
        vraagHoeveelheidBolletjes()
    else:
        snapIkNiet()
        vraagHoeveelheidBolletjes()
def bon(bolletjes):
    prijsBolletje = 1.10
    prijsHoorntje = 1.25
    prijsBakje = 0.75
    global bakjes
    global hoorntjes
    print("-----------['Papi Gelato']-----------")
    print("")
    totaalPrijsBolletjes = prijsBolletje * bolletjes
    totaalPrijsHoorntjes = prijsHoorntje * hoorntjes
    totaalPrijsBakjes = prijsBakje * bakjes
    totaalPrijs = totaalPrijsBolletjes + totaalPrijsHoorntjes + totaalPrijsBakjes
    if int(bolletjes) > 0:
        print("Bolletjes        " + str(bolletjes) + " x €" + str('{0:.2f}'.format(prijsBolletje)) + "    = €" + str('{0:.2f}'.format(totaalPrijsBolletjes))) 
    if hoorntjes > 0:
        print("Hoorntjes        " + str(hoorntjes) + " x €" + str('{0:.2f}'.format(prijsHoorntje)) + "    = €" + str('{0:.2f}'.format(totaalPrijsHoorntjes))) 
    if bakjes > 0:
        print("Bakjes           " + str(bakjes) +    " x €" + str('{0:.2f}'.format(prijsBakje)) +    "    = €" + str('{0:.2f}'.format(totaalPrijsBakjes)))
    print    ("                              -------- +") 
    print    ("Totaal                        = €" + str('{0:.2f}'.format(totaalPrijs))) 
vraagHoeveelheidBolletjes()
```

 