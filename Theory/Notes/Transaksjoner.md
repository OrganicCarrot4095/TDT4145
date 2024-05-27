# Transaksjoner

## Hvorfor transaksjoner? 

- Støtter deling og samtidig akess av data 
    - Flerbrukskontroll. READ COMMITTED, SNAPSHOT ISOLATION, SERIALIZABLE
- Støtter sikker pålitelig, atomisk aksess til store mengder data
    - Recovery: Rollback og krasjrecovery


## Databaseoperasjoner

- X - databaseobjekt: post eller blokk
    - read (x)
    - r (x)
    - write (x)
    - w (x)
- Tilhørende transaksjon 1
    - $read_{1}(X)$
    - $r_{1}(X)$
- Commit1 $c_{1}$ suksess: avsluttning av transaksjon 1
- Abort1 $a_{1}$