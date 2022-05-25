# musik
Musik with link to browser

import webbrowser
import time
import sys
kuenstler = ["Drake", "Rihanna", "Ariana Grande", "Future", "50 Cent", "Snopp Dog", "Eminem", "Jay Z", "Kanye West", "Samra","2 Pac", "K1 de Ultimate",""]
musik = {"Drake": "https://www.youtube.com/watch?v=JFm7YDVlqnI",
         "Rihanna": "https://www.youtube.com/watch?v=lWA2pjMjpBs",
         "Ariana Grande": "https://www.youtube.com/watch?v=QYh6mYIJG2Y",
         "Future": "https://www.youtube.com/watch?v=Y2QpQP8wPG8",
         "50 Cent": "https://www.youtube.com/watch?v=7CVGDPqnZj8",
         "Snopp Dog": "https://www.youtube.com/watch?v=_CL6n0FJZpk",
         "Eminem": "https://www.youtube.com/watch?v=_Yhyp-_hX2s",
         "Jay Z": "https://www.youtube.com/watch?v=vk6014HuxcE",
         "Kanye West": "https://www.youtube.com/watch?v=cwQgjq0mCdE",
         "Samra": "https://www.youtube.com/watch?v=u2qVU8OsRtw&ab_channel=Samra",
         "2 Pac": "https://www.youtube.com/watch?v=zkwo6VP_EfQ",
         "K1 de Ultimate": "https://www.youtube.com/watch?v=HT3Z8myTQI0"}

songs = {"Drake": '\nSie hören jetzt "Laugh now Cry later" von Drake',
         "Rihanna": '\nSie hören jetzt "Diamonds" von Rihanna',
         "Ariana Grande": '\nSie hören jetzt "7 rings" von Ariana Grande',
         "Future": '\nSie hören jetzt "Wait for U" von Future',
         "50 Cent": '\nSie hören jetzt "Many Man" von 50 Cent',
         "Snopp Dog": '\nSie hören jetzt "Still D.R.E" von Snoop Dog und Dr.Dre',
         "Eminem": '\nSie hören jetzt "Loose yourself" von Eminem',
         "Jay Z": '\nSie hören jetzt "Empire State of Mind" von Jay Z',
         "Kanye West": '\nSie hören jetzt "I Love it" von Kanye West und Lil Pump',
         "Samra": '\n Sie hören jetzt "Weiss" von Samra',
         "2 Pac": '\nSie hören jetzt "So much pain" von 2 Pac',
         "K1 de Ultimate": '\nSie hören jetzt "Adé Orí Òkin" von K1 de Ultimate'}

def zeit():
    for x in range(2):
        time.sleep(0.35)
        sys.stdout.write("-")
    print()
    for n in range(3):
        time.sleep(0.35)
        sys.stdout.write("-")
    print()
    for n in range(4):
        time.sleep(0.35)
        sys.stdout.write("-")
    return

var = True

print(kuenstler)
print("Welchen Künstler wollen Sie hören")
while var:
    benutzer = input("\nFür wenn entscheiden Sie sich: ")
    if benutzer in kuenstler:
        indexwert = kuenstler.index(benutzer)
        print(f"{benutzer} wurde gefunden")
        print(f"\nWollen sie bei {benutzer} aufhören oder die Musik von {benutzer} hören")

        neu = indexwert + 1
        neu2 = indexwert - 1

        print(f'\nSchreiben ">" um {kuenstler[neu]} zu hören'
                     f'\nSchreiben Sie "<" um {kuenstler[neu2]} zu hören'
                     f'\nSchreiben Sie "yes" um bei {benutzer} zu bleiben'
                     f'\nSchreiben Sie "stop" um aufzuhören')

        entscheidung = input("Für was entscheiden Sie sich: ")

        if entscheidung == ">":
            print(f"\nSie sind nun bei {kuenstler[neu]}")
            entscheidung2 = input("Wollen Sie weiter machen j/n: ")
            if entscheidung2 == "j":
                print(f"{kuenstler[neu]} ist eine gute Wahl")

                if kuenstler[neu] in musik:
                    if kuenstler[neu] in songs:
                        try:
                            print(f"\n{songs[kuenstler[neu]]}\n")
                            zeit()
                            webbrowser.open(url=musik[kuenstler[neu]])
                            var = False
                            break

                        except:
                            print("Sie haben was falsch gemacht")
                            var = False
                            break
            elif entscheidung2 == "n":
                print("Auf Wiedersehen")
                var = False
                break

        elif entscheidung == "<":
            print(f"\nSie sind nun bei {kuenstler[neu2]}")
            entscheidung2 = input("Wollen Sie weiter machen j/n: ")
            if entscheidung2 == "j":
                print(f"{kuenstler[neu2]} ist eine gute Wahl")

                if kuenstler[neu2] in musik:
                    if kuenstler[neu2] in songs:
                        try:
                            print(f"\n{songs[kuenstler[neu2]]} \n")
                            zeit()
                            webbrowser.open(url=musik[kuenstler[neu2]])
                            var = False
                            break

                        except:
                            print("Sie haben was falsch gemacht")
                            var = False
                            break
            elif entscheidung2 == "n":
                print("\nAuf Wiedersehen")
                var = False
                break

        elif entscheidung == "stop":
            print("\nAuf Wiedersehen")
            var = False
            break

        elif entscheidung == "yes":
            print(f"\nSie sind jetzt bei {benutzer}")
            entscheidung2 = input("Wollen Sie weiter machen j/n: ")
            if entscheidung2 == "j":
                print(f"\n{benutzer} ist eine gute Wahl")

                if benutzer in musik:
                    if benutzer in songs:
                        try:
                            print(f"{songs[benutzer]} \n")
                            zeit()
                            webbrowser.open(url=musik[benutzer])
                            var = False
                            break

                        except:
                            print("Sie haben was falsch gemacht")
                            var = False
                            break
            elif entscheidung2 == "n":
                print("Auf Wiedersehen")
                var = False
                break

        else:
            print("\nSie haben da vielleicht was falsch geschreiben")
            print("Versuchen Sie es nochmal")

    else:
        print(f"{benutzer} ist nicht in der Liste")
        print("Schreiben Sie vieleicht den Namen richtig ein")
