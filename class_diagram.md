# Class diagram
## Entity
    Uživatel - fyzická osoba, která používá aplikaci. Slouží k identifikaci uživatele, přidělení a ohlídání oprávnění.
    Způsob přihlášení - dvojice uživatelského jména a tajné hodnoty, která slouží k přihlášení uživatele pomocí různých způsobů.
    Záznamy o přihlášení - záznamy o přihlášení uživatele pomocí různých způsobů, vytvoří hash, kterým se uživatel ověří při každém přístupu k aplikaci. To umožní např. vzdálené odhlášení z~jiných zařízení. Kromě toho zaznaméname časy přihlášení a odhlášení, IP adresu a typ zařízení.
    Záznam o uživatelských aktivitách - záznamy o aktivitách uživatele v aplikaci, vázané na konkrétní přihlášení. Např. vytvoření testu,  úprava nebo smazání příkladu nebo testu, kategorie.
    Kategorie - kategorie pro příklady nebo testy, které jsou tematicky nebo jinak spojeny. Kategoriemi nejvyšší úrovně jsou předměty, které vyučuje uživatel. Obsahuje název, popis a odkaz na nadřazenou kategorii (hiearchii kategorií).
    Tagy - klíčová slova, která jsou přiřazena k příkladům nebo testům. Označují jejich obsah nebo vlastnosti, jako například stupeň obtížnosti.
    Příklad - konkrétní úloha nebo otázka, které vkládáme do testů. Obsahuje název, text, typ (otevřený, uzavřený), odpovědi (v případě uzavřeného příkladu), proměnné, odkaz na kategorii a zvláštní nastavení pro sestavení.
    Proměnná - reprezentuje proměnnou, která může být použita v příkladu. Obsahuje název, typ a hodnotu.
    Test - reprezentuje soubor příkladů a nastavení, který je připraven pro použití.

Mezi entitami existují následující vztahy:

    Uživatel může vytvořit Příklad.
    Příklad může být zařazen do Kategorie.
    Příklad může obsahovat Proměnné.
    Test může obsahovat Příklady.

Podrobnější popis entit:

    Uživatel má následující atributy:
        jméno
        příjmení
        e-mail
        heslo
        role (student, učitel, administrátor)

    Příklad má následující atributy:
        název
        text
        typ (otevřený, uzavřený)
        odpovědi (v případě uzavřeného příkladu)
        proměnné

    Kategorie má následující atributy:
        název
        popis

    Proměnná má následující atributy:
        název
        typ (číslo, řetězec, vstupní pole)
        hodnota (v případě generované proměnné)

    Písemka má následující atributy:
        název
        popis
        datum vytvoření
        datum úpravy
        kategorie
        příklady

Tento model lze samozřejmě ještě doladit a doplnit o další atributy a vztahy, například:

    Proměnné mohou mít atribut varianta, který určuje, do které varianty příkladu patří.
    Příklady mohou mít atribut třída obtížnosti.
    Písemky mohou mít atribut počet otázek.

Konkrétní implementace class diagramu bude záviset na konkrétním vývojářském prostředí a stylu programování.