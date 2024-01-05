import os
import random

def adatok_beolvasasa(fajlnev):
    try:
        with open(fajlnev, 'r') as fajl:
            sorok = fajl.readlines()
            return [float(szam.strip()) for szam in sorok]
    except FileNotFoundError:
        print("Hiba: A fájl nem található.")
        return []

def adatok_osszegezes(adatok):
    return sum(adatok)

def adatok_listazasa(adatok):
    print("Az adatok:")
    for szam in adatok:
        print(szam)

def adatok_fajlba_irasa(adatok, kimeneti_fajlnev):
    try:
        akt_mappa = os.getcwd()
        kimeneti_fajl_teljes_ut = os.path.join(akt_mappa, kimeneti_fajlnev)
        
        with open(kimeneti_fajl_teljes_ut, 'w') as kimeneti_fajl:
            for szam in adatok:
                kimeneti_fajl.write(str(szam) + "\n")
        
        print("Az adatok sikeresen ki lettek írva a fájlba: {}".format(kimeneti_fajl_teljes_ut))
    except Exception as e:
        print("Hiba a fájlba írás során:", str(e))

def adatok_idotartomanyba(adatok, kezdo_ev, vegso_ev):
    return [szam for szam in adatok if kezdo_ev <= szam <= vegso_ev]

def teszt_feladat(adatok):
    if len(adatok) < 3:
        print("Nincs elég adat a teszthez.")
        return

    evszam = random.choice(adatok)
    helyes_valaszok = random.sample(adatok, 3)

    print("Melyik vívmányhoz tartozik a következő év szám: {}?".format(evszam))

    for i, valasz in enumerate(helyes_valaszok):
        print("{}. {}".format(i + 1, valasz))

    try:
        felhasznalo_valasz = int(input("Válassza ki a helyes választ (1-3): "))
        if 1 <= felhasznalo_valasz <= 3:
            valasztott_ev = helyes_valaszok[felhasznalo_valasz - 1]
            if valasztott_ev == evszam:
                print("Gratulálok! Helyes válasz.")
            else:
                print("Sajnálom, helytelen válasz. A helyes válasz: {}".format(evszam))
        else:
            print("Érvénytelen válasz.")
    except ValueError:
        print("Érvénytelen válasz formátum.")

def main():
    adatok = []
    while True:
        print("\n1. Adatok beolvasása")
        print("2. Adatok összegezése")
        print("3. Adatok listázása")
        print("4. Adatok kiírása fájlba")
        print("5. Vívmányok listázása időtartományban")
        print("6. Teszt feladat")
        print("7. Kilépés")

        valasztas = input("Válasszon egy menüpontot (1-7): ")

        if valasztas == '1':
            fajlnev = input("Kérem, adja meg a fájl nevét: ")
            adatok = adatok_beolvasasa(fajlnev)
            if adatok:
                print("Az adatok beolvasása sikeres.")
            else:
                print("Nem sikerült beolvasni az adatokat.")

        elif valasztas == '2':
            if adatok:
                osszeg = adatok_osszegezes(adatok)
                print("Az adatok összege: {}".format(osszeg))
            else:
                print("Nincsenek elérhető adatok.")

        elif valasztas == '3':
            if adatok:
                adatok_listazasa(adatok)
            else:
                print("Nincsenek elérhető adatok.")

        elif valasztas == '4':
            if adatok:
                kimeneti_fajlnev = input("Kérem, adja meg a kimeneti fájl nevét: ")
                adatok_fajlba_irasa(adatok, kimeneti_fajlnev)
            else:
                print("Nincsenek elérhető adatok.")

        elif valasztas == '5':
            if adatok:
                try:
                    kezdo_ev = float(input("Kérem, adja meg a kezdő évet: "))
                    vegso_ev = float(input("Kérem, adja meg a végső évet: "))
                    idotartomany_adatok = adatok_idotartomanyba(adatok, kezdo_ev, vegso_ev)
                    print("Az időtartományba eső vívmányok:")
                    for szam in idotartomany_adatok:
                        print(szam)
                except ValueError:
                    print("Érvénytelen év formátum.")
            else:
                print("Nincsenek elérhető adatok.")

        elif valasztas == '6':
            teszt_feladat(adatok)

        elif valasztas == '7':
            print("Kilépés...")
            break

        else:
            print("Érvénytelen választás. Kérem, válasszon 1 és 7 közötti értéket.")

if __name__ == "__main__":
    main()
    
