```mermaid
classDiagram
    class VirtuosoKinoSystem {
        +registrerBillettkjøp(Billett b, Kunde k)
        +registrerKunde(String navn, String tlf, String epostadresse)
        +genererStatistikk()
    }
    
    class Kino {
        +finnLedigBilletter(): int
        +hentBillettType(): Array
    }
    
    class Billett {
        +printBillett()
    }
    
    class Kunde {
        +registrerInfo(String navn, Int telefonnr, String epost)
        +settBillett(Billett b)
    }

    VirtuosoKinoSystem "1" -- "many" Kino : har
    Kino "1" -- "many" Billett : inneholder
    Kunde "1" -- "many" Billett : kjøper