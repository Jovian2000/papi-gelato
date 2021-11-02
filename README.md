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
## F1.5.02.O6
Ik heb nu deze functie erbij:
``` python
def vraagToppings(bolletjes,hornOfBak):
    global slagroom
    global totaalPrijsSlagroom
    global sprinkels
    global totaalPrijsSprinkels
    global caramelSausHorn
    global totaalPrijsCaramelSausHorn
    global caramelSausBak
    global totaalPrijsCaramelSausBak
    keuzeToppings = input("Wat voor topping wilt u? A) geen, B) Slagroom, C) Sprinkels of D) Caramel Saus: ")
    if (keuzeToppings == "A" or keuzeToppings == "a") and hornOfBak == "A":
        vraagMeerBestellen(bolletjes,"hoorntje","")
    elif (keuzeToppings == "A" or keuzeToppings == "a") and hornOfBak == "B":
        vraagMeerBestellen(bolletjes,"bakje","")        
    elif (keuzeToppings == "B" or keuzeToppings == "b") and hornOfBak == "A":
        slagroom = slagroom + 1 
        totaalPrijsSlagroom = slagroom * 0.50
        vraagMeerBestellen(bolletjes,"hoorntje","")
    elif (keuzeToppings == "B" or keuzeToppings == "b") and hornOfBak == "B":
        slagroom = slagroom + 1
        totaalPrijsSlagroom = slagroom * 0.50
        vraagMeerBestellen(bolletjes,"bakje","")        
    elif (keuzeToppings == "C" or keuzeToppings == "c") and hornOfBak == "A":
        sprinkels = sprinkels + 1 
        totaalPrijsSprinkels = sprinkels * (int(bolletjes) * 0.30)
        vraagMeerBestellen(bolletjes,"hoorntje","")
    elif (keuzeToppings == "C" or keuzeToppings == "c") and hornOfBak == "B":
        sprinkels = sprinkels + 1 
        totaalPrijsSprinkels = sprinkels * (int(bolletjes) * 0.30)
        vraagMeerBestellen(bolletjes,"bakje","")        
    elif (keuzeToppings == "D" or keuzeToppings == "d") and hornOfBak == "A":
        caramelSausHorn = caramelSausHorn + 1 
        totaalPrijsCaramelSausHorn = caramelSausHorn * 0.60
        vraagMeerBestellen(bolletjes,"hoorntje","")
    elif (keuzeToppings == "D" or keuzeToppings == "d") and hornOfBak == "B":
        caramelSausBak = caramelSausBak + 1 
        totaalPrijsCaramelSausBak = caramelSausBak * 0.90
        vraagMeerBestellen(bolletjes,"bakje","")        
    else:
        snapIkNiet()
        vraagToppings(bolletjes,hornOfBak)
```
Ik heb paar variabelen erbij gemaakt, nieuwe functie toegevoegd en sommige functies aangepast. Nu is dit het programma:
``` python
print("Welkom bij Papi Gelato")
hoorntjes = 0
bakjes = 0
bolletjes = 0
# toppings = 0
# prijsToppings = 0
slagroom = 0
totaalPrijsSlagroom = 0
sprinkels = 0
totaalPrijsSprinkels = 0
caramelSausHorn = 0
totaalPrijsCaramelSausHorn = 0
caramelSausBak = 0
totaalPrijsCaramelSausBak = 0
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
def vraagHornOfBak(hornOfBak,bolletjes):
    hornOfBak = input("Wilt u deze " + str(bolletjes) + " bolletjes in (A) een hoorntje of (B) een bakje? ")
    if hornOfBak == "A" or hornOfBak == "a":
        vraagWelkeSmaak(bolletjes,"",1,"A")
    elif hornOfBak == "B" or hornOfBak == "b":
        vraagWelkeSmaak(bolletjes,"",1,"B")
    else:
        snapIkNiet()
        vraagHornOfBak("", bolletjes)
def vraagWelkeSmaak(bolletjes,smaak,nummerBolletje,hornOfBak):
    while nummerBolletje <= int(bolletjes):
        smaak = input("Welke smaak wilt u voor bolletje nummer " + str(nummerBolletje) + "? A) Aardbei, C) Chocolade, M) Munt, V) Vanille: ")
        if smaak == "A" or smaak == "C" or smaak == "M" or smaak == "V" or smaak == "a" or smaak == "c" or smaak == "m" or smaak == "v":
            nummerBolletje = nummerBolletje + 1
        else:
            snapIkNiet()
    if hornOfBak == "A":
        global hoorntjes
        hoorntjes = hoorntjes + 1
        # vraagMeerBestellen(bolletjes,"hoorntje","")
        vraagToppings(bolletjes,"A")

    else:
        global bakjes
        bakjes = bakjes + 1
        # vraagMeerBestellen(bolletjes,"bakje","")
        vraagToppings(bolletjes,"B")
def vraagToppings(bolletjes,hornOfBak):
    global slagroom
    global totaalPrijsSlagroom
    global sprinkels
    global totaalPrijsSprinkels
    global caramelSausHorn
    global totaalPrijsCaramelSausHorn
    global caramelSausBak
    global totaalPrijsCaramelSausBak
    keuzeToppings = input("Wat voor topping wilt u? A) geen, B) Slagroom, C) Sprinkels of D) Caramel Saus: ")
    if (keuzeToppings == "A" or keuzeToppings == "a") and hornOfBak == "A":
        vraagMeerBestellen(bolletjes,"hoorntje","")
    elif (keuzeToppings == "A" or keuzeToppings == "a") and hornOfBak == "B":
        vraagMeerBestellen(bolletjes,"bakje","")        
    elif (keuzeToppings == "B" or keuzeToppings == "b") and hornOfBak == "A":
        slagroom = slagroom + 1 
        totaalPrijsSlagroom = slagroom * 0.50
        vraagMeerBestellen(bolletjes,"hoorntje","")
    elif (keuzeToppings == "B" or keuzeToppings == "b") and hornOfBak == "B":
        slagroom = slagroom + 1
        totaalPrijsSlagroom = slagroom * 0.50
        vraagMeerBestellen(bolletjes,"bakje","")        
    elif (keuzeToppings == "C" or keuzeToppings == "c") and hornOfBak == "A":
        sprinkels = sprinkels + 1 
        totaalPrijsSprinkels = sprinkels * (int(bolletjes) * 0.30)
        vraagMeerBestellen(bolletjes,"hoorntje","")
    elif (keuzeToppings == "C" or keuzeToppings == "c") and hornOfBak == "B":
        sprinkels = sprinkels + 1 
        totaalPrijsSprinkels = sprinkels * (int(bolletjes) * 0.30)
        vraagMeerBestellen(bolletjes,"bakje","")        
    elif (keuzeToppings == "D" or keuzeToppings == "d") and hornOfBak == "A":
        caramelSausHorn = caramelSausHorn + 1 
        totaalPrijsCaramelSausHorn = caramelSausHorn * 0.60
        vraagMeerBestellen(bolletjes,"hoorntje","")
    elif (keuzeToppings == "D" or keuzeToppings == "d") and hornOfBak == "B":
        caramelSausBak = caramelSausBak + 1 
        totaalPrijsCaramelSausBak = caramelSausBak * 0.90
        vraagMeerBestellen(bolletjes,"bakje","")        
    else:
        snapIkNiet()
        vraagToppings(bolletjes,hornOfBak)
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
def bon(bolletjes):
    prijsBolletje = 1.10
    prijsHoorntje = 1.25
    prijsBakje = 0.75
    prijsSlagroom = 0.50
    prijsSprinkels = 0.30
    prijsCaramelsausHorn = 0.60
    prijsCaramelsausBak = 0.90 
    global bakjes
    global hoorntjes
    global slagroom
    global totaalPrijsSlagroom
    global sprinkels
    global totaalPrijsSprinkels
    global caramelSausHorn
    global totaalPrijsCaramelSausHorn
    global caramelSausBak
    global totaalPrijsCaramelSausBak
    print("-----------['Papi Gelato']-----------")
    print("")
    totaalPrijsBolletjes = prijsBolletje * bolletjes
    totaalPrijsHoorntjes = prijsHoorntje * hoorntjes
    totaalPrijsBakjes = prijsBakje * bakjes
    totaalPrijs = totaalPrijsBolletjes + totaalPrijsHoorntjes + totaalPrijsBakjes + totaalPrijsSlagroom + totaalPrijsSprinkels + totaalPrijsCaramelSausHorn + totaalPrijsCaramelSausBak
    if int(bolletjes) > 0:
        print("Bolletjes                " + str(bolletjes) + " x €" + str('{0:.2f}'.format(prijsBolletje)) + "                  = €" + str('{0:.2f}'.format(totaalPrijsBolletjes))) 
    if hoorntjes > 0:
        print("Hoorntjes                " + str(hoorntjes) + " x €" + str('{0:.2f}'.format(prijsHoorntje)) + "                  = €" + str('{0:.2f}'.format(totaalPrijsHoorntjes))) 
    if bakjes > 0:
        print("Bakjes                   " + str(bakjes) +    " x €" + str('{0:.2f}'.format(prijsBakje)) + "                  = €" + str('{0:.2f}'.format(totaalPrijsBakjes)))
    if slagroom > 0:
        print("Slagroom                 " + str(slagroom) +    " x €" + str('{0:.2f}'.format(prijsSlagroom)) + "                  = €" + str('{0:.2f}'.format(totaalPrijsSlagroom)))
    if sprinkels > 0:
        print("Sprinkels                " + str(sprinkels) +    " x €" + str('{0:.2f}'.format(prijsSprinkels)) + " (per bolletje)" + "   = €" + str('{0:.2f}'.format(totaalPrijsSprinkels)))
    if caramelSausHorn > 0:
        print("Caramel saus (hoorntje)  " + str(caramelSausHorn) +    " x €" + str('{0:.2f}'.format(prijsCaramelsausHorn)) + "                  = €" + str('{0:.2f}'.format(totaalPrijsCaramelSausHorn)))
    if caramelSausBak > 0:
        print("Caramel saus (bakje)     " + str(caramelSausBak) +    " x €" + str('{0:.2f}'.format(prijsCaramelsausBak)) + "                  = €" + str('{0:.2f}'.format(totaalPrijsCaramelSausBak)))                
    print    ("                                                    -------- +") 
    print    ("Totaal                                              = €" + str('{0:.2f}'.format(totaalPrijs))) 
def snapIkNiet():
    print("Sorry, dat snap ik niet") 
vraagHoeveelheidBolletjes()
```
## F1.5.02.O7
Dit zijn de functies die ik erbij heb gemaakt
### 1
``` python
def particulierOfZakelijk():
    vraagParticulierOfZakelijk = input("Bent u 1) particulier of 2) zakelijk? ")
    if vraagParticulierOfZakelijk == "particulier" or vraagParticulierOfZakelijk == "Particulier" or vraagParticulierOfZakelijk == "1":
        vraagHoeveelheidBolletjes()
    elif vraagParticulierOfZakelijk == "zakelijk" or vraagParticulierOfZakelijk == "Zakelijk" or vraagParticulierOfZakelijk == "2":
        vraagHoeveelLiter()
    else:
        snapIkNiet()
        particulierOfZakelijk() 
```
### 2
``` python
def vraagHoeveelLiter():
    liter = input("Hoeveel liter ijs wilt u? ")
    smaakZakelijk(liter,1)
```
### 3
``` python
def smaakZakelijk(liter,literNummer):
    while literNummer <= int(liter):
        if literNummer == 1:
            smaakPerLiter = input("Welke smaak wilt u voor de " + str(literNummer) + "st liter? A) Aardbei, C) Chocolade, M) Munt, V) Vanille: ")
            if smaakPerLiter == "A" or smaakPerLiter == "C" or smaakPerLiter == "M" or smaakPerLiter == "V" or smaakPerLiter == "a" or smaakPerLiter == "c" or smaakPerLiter == "m" or smaakPerLiter == "v":
                literNummer = literNummer + 1
            else:
                snapIkNiet()
        else:
            smaakPerLiter = input("Welke smaak wilt u voor de " + str(literNummer) + "de liter? A) Aardbei, C) Chocolade, M) Munt, V) Vanille: ")
            if smaakPerLiter == "A" or smaakPerLiter == "C" or smaakPerLiter == "M" or smaakPerLiter == "V" or smaakPerLiter == "a" or smaakPerLiter == "c" or smaakPerLiter == "m" or smaakPerLiter == "v":
                literNummer = literNummer + 1
            else:
                snapIkNiet()
    bonZakelijk(liter)
```
### 4
``` python
def bonZakelijk(liter):
    prijsPerLiter = 9.80
    totaalPrijsLiter = int(liter) * prijsPerLiter
    btw = 0.09
    totaalPrijs = totaalPrijsLiter 
    btwTotaalPrijs = totaalPrijs * btw
    print("-----------['Papi Gelato']-----------")
    print("")
    if int(liter) > 0:
        print("Liter        " + str(liter) + " x €" + str('{0:.2f}'.format(prijsPerLiter)) + "   = €" + str('{0:.2f}'.format(totaalPrijsLiter)))
    print("                         ---------")
    print("Totaal                   = €" + str('{0:.2f}'.format(totaalPrijs)))
    print("Btw (9%)                 = €" + str('{0:.2f}'.format(btwTotaalPrijs))) 
```
Nu is dit de volledige programma
``` python 
print("Welkom bij Papi Gelato")
hoorntjes = 0
bakjes = 0
bolletjes = 0
slagroom = 0
totaalPrijsSlagroom = 0
sprinkels = 0
totaalPrijsSprinkels = 0
caramelSausHorn = 0
totaalPrijsCaramelSausHorn = 0
caramelSausBak = 0
totaalPrijsCaramelSausBak = 0
def particulierOfZakelijk():
    vraagParticulierOfZakelijk = input("Bent u 1) particulier of 2) zakelijk? ")
    if vraagParticulierOfZakelijk == "particulier" or vraagParticulierOfZakelijk == "Particulier" or vraagParticulierOfZakelijk == "1":
        vraagHoeveelheidBolletjes()
    elif vraagParticulierOfZakelijk == "zakelijk" or vraagParticulierOfZakelijk == "Zakelijk" or vraagParticulierOfZakelijk == "2":
        vraagHoeveelLiter()
    else:
        snapIkNiet()
        particulierOfZakelijk()
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
def vraagHornOfBak(hornOfBak,bolletjes):
    hornOfBak = input("Wilt u deze " + str(bolletjes) + " bolletjes in (A) een hoorntje of (B) een bakje? ")
    if hornOfBak == "A" or hornOfBak == "a":
        vraagWelkeSmaak(bolletjes,"",1,"A")
    elif hornOfBak == "B" or hornOfBak == "b":
        vraagWelkeSmaak(bolletjes,"",1,"B")
    else:
        snapIkNiet()
        vraagHornOfBak("", bolletjes)
def vraagWelkeSmaak(bolletjes,smaak,nummerBolletje,hornOfBak):
    while nummerBolletje <= int(bolletjes):
        smaak = input("Welke smaak wilt u voor bolletje nummer " + str(nummerBolletje) + "? A) Aardbei, C) Chocolade, M) Munt, V) Vanille: ")
        if smaak == "A" or smaak == "C" or smaak == "M" or smaak == "V" or smaak == "a" or smaak == "c" or smaak == "m" or smaak == "v":
            nummerBolletje = nummerBolletje + 1
        else:
            snapIkNiet()
    if hornOfBak == "A":
        global hoorntjes
        hoorntjes = hoorntjes + 1
        vraagToppings(bolletjes,"A")

    else:
        global bakjes
        bakjes = bakjes + 1
        vraagToppings(bolletjes,"B")
def vraagToppings(bolletjes,hornOfBak):
    global slagroom
    global totaalPrijsSlagroom
    global sprinkels
    global totaalPrijsSprinkels
    global caramelSausHorn
    global totaalPrijsCaramelSausHorn
    global caramelSausBak
    global totaalPrijsCaramelSausBak
    keuzeToppings = input("Wat voor topping wilt u? A) geen, B) Slagroom, C) Sprinkels of D) Caramel Saus: ")
    if (keuzeToppings == "A" or keuzeToppings == "a") and hornOfBak == "A":
        vraagMeerBestellen(bolletjes,"hoorntje","")
    elif (keuzeToppings == "A" or keuzeToppings == "a") and hornOfBak == "B":
        vraagMeerBestellen(bolletjes,"bakje","")        
    elif (keuzeToppings == "B" or keuzeToppings == "b") and hornOfBak == "A":
        slagroom = slagroom + 1 
        totaalPrijsSlagroom = slagroom * 0.50
        vraagMeerBestellen(bolletjes,"hoorntje","")
    elif (keuzeToppings == "B" or keuzeToppings == "b") and hornOfBak == "B":
        slagroom = slagroom + 1
        totaalPrijsSlagroom = slagroom * 0.50
        vraagMeerBestellen(bolletjes,"bakje","")        
    elif (keuzeToppings == "C" or keuzeToppings == "c") and hornOfBak == "A":
        sprinkels = sprinkels + 1 
        totaalPrijsSprinkels = sprinkels * (int(bolletjes) * 0.30)
        vraagMeerBestellen(bolletjes,"hoorntje","")
    elif (keuzeToppings == "C" or keuzeToppings == "c") and hornOfBak == "B":
        sprinkels = sprinkels + 1 
        totaalPrijsSprinkels = sprinkels * (int(bolletjes) * 0.30)
        vraagMeerBestellen(bolletjes,"bakje","")        
    elif (keuzeToppings == "D" or keuzeToppings == "d") and hornOfBak == "A":
        caramelSausHorn = caramelSausHorn + 1 
        totaalPrijsCaramelSausHorn = caramelSausHorn * 0.60
        vraagMeerBestellen(bolletjes,"hoorntje","")
    elif (keuzeToppings == "D" or keuzeToppings == "d") and hornOfBak == "B":
        caramelSausBak = caramelSausBak + 1 
        totaalPrijsCaramelSausBak = caramelSausBak * 0.90
        vraagMeerBestellen(bolletjes,"bakje","")        
    else:
        snapIkNiet()
        vraagToppings(bolletjes,hornOfBak)
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
def bon(bolletjes):
    prijsBolletje = 1.10
    prijsHoorntje = 1.25
    prijsBakje = 0.75
    prijsSlagroom = 0.50
    prijsSprinkels = 0.30
    prijsCaramelsausHorn = 0.60
    prijsCaramelsausBak = 0.90 
    global bakjes
    global hoorntjes
    global slagroom
    global totaalPrijsSlagroom
    global sprinkels
    global totaalPrijsSprinkels
    global caramelSausHorn
    global totaalPrijsCaramelSausHorn
    global caramelSausBak
    global totaalPrijsCaramelSausBak
    print("-----------['Papi Gelato']-----------")
    print("")
    totaalPrijsBolletjes = prijsBolletje * bolletjes
    totaalPrijsHoorntjes = prijsHoorntje * hoorntjes
    totaalPrijsBakjes = prijsBakje * bakjes
    totaalPrijs = totaalPrijsBolletjes + totaalPrijsHoorntjes + totaalPrijsBakjes + totaalPrijsSlagroom + totaalPrijsSprinkels + totaalPrijsCaramelSausHorn + totaalPrijsCaramelSausBak
    if int(bolletjes) > 0:
        print("Bolletjes                " + str(bolletjes) + " x €" + str('{0:.2f}'.format(prijsBolletje)) + "                  = €" + str('{0:.2f}'.format(totaalPrijsBolletjes))) 
    if hoorntjes > 0:
        print("Hoorntjes                " + str(hoorntjes) + " x €" + str('{0:.2f}'.format(prijsHoorntje)) + "                  = €" + str('{0:.2f}'.format(totaalPrijsHoorntjes))) 
    if bakjes > 0:
        print("Bakjes                   " + str(bakjes) +    " x €" + str('{0:.2f}'.format(prijsBakje)) + "                  = €" + str('{0:.2f}'.format(totaalPrijsBakjes)))
    if slagroom > 0:
        print("Slagroom                 " + str(slagroom) +    " x €" + str('{0:.2f}'.format(prijsSlagroom)) + "                  = €" + str('{0:.2f}'.format(totaalPrijsSlagroom)))
    if sprinkels > 0:
        print("Sprinkels                " + str(sprinkels) +    " x €" + str('{0:.2f}'.format(prijsSprinkels)) + " (per bolletje)" + "   = €" + str('{0:.2f}'.format(totaalPrijsSprinkels)))
    if caramelSausHorn > 0:
        print("Caramel saus (hoorntje)  " + str(caramelSausHorn) +    " x €" + str('{0:.2f}'.format(prijsCaramelsausHorn)) + "                  = €" + str('{0:.2f}'.format(totaalPrijsCaramelSausHorn)))
    if caramelSausBak > 0:
        print("Caramel saus (bakje)     " + str(caramelSausBak) +    " x €" + str('{0:.2f}'.format(prijsCaramelsausBak)) + "                  = €" + str('{0:.2f}'.format(totaalPrijsCaramelSausBak)))                
    print    ("                                                    -------- +") 
    print    ("Totaal                                              = €" + str('{0:.2f}'.format(totaalPrijs))) 
def snapIkNiet():
    print("Sorry, dat snap ik niet")
def vraagHoeveelLiter():
    liter = input("Hoeveel liter ijs wilt u? ")
    smaakZakelijk(liter,1)
def smaakZakelijk(liter,literNummer):
    while literNummer <= int(liter):
        if literNummer == 1:
            smaakPerLiter = input("Welke smaak wilt u voor de " + str(literNummer) + "st liter? A) Aardbei, C) Chocolade, M) Munt, V) Vanille: ")
            if smaakPerLiter == "A" or smaakPerLiter == "C" or smaakPerLiter == "M" or smaakPerLiter == "V" or smaakPerLiter == "a" or smaakPerLiter == "c" or smaakPerLiter == "m" or smaakPerLiter == "v":
                literNummer = literNummer + 1
            else:
                snapIkNiet()
        else:
            smaakPerLiter = input("Welke smaak wilt u voor de " + str(literNummer) + "de liter? A) Aardbei, C) Chocolade, M) Munt, V) Vanille: ")
            if smaakPerLiter == "A" or smaakPerLiter == "C" or smaakPerLiter == "M" or smaakPerLiter == "V" or smaakPerLiter == "a" or smaakPerLiter == "c" or smaakPerLiter == "m" or smaakPerLiter == "v":
                literNummer = literNummer + 1
            else:
                snapIkNiet()
    bonZakelijk(liter)
def bonZakelijk(liter):
    prijsPerLiter = 9.80
    totaalPrijsLiter = int(liter) * prijsPerLiter
    btw = 0.09
    totaalPrijs = totaalPrijsLiter 
    btwTotaalPrijs = totaalPrijs * btw
    print("-----------['Papi Gelato']-----------")
    print("")
    if int(liter) > 0:
        print("Liter        " + str(liter) + " x €" + str('{0:.2f}'.format(prijsPerLiter)) + "   = €" + str('{0:.2f}'.format(totaalPrijsLiter)))
    print("                         ---------")
    print("Totaal                   = €" + str('{0:.2f}'.format(totaalPrijs)))
    print("Btw (9%)                 = €" + str('{0:.2f}'.format(btwTotaalPrijs))) 
particulierOfZakelijk()
```