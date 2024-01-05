import os

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

def main():
    adatok = []
    while True:
        print("\n1. Adatok beolvasása")
        print("2. Adatok összegezése")
