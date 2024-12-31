# calculator.java-Start.java

=Izveštaj o analizi koda=


 - Metode za dobijanje metrika:
     Za izračunavanje linija koda (LOC) u projektu, možemo prebrojati sve linije koje sadrže kod, ignorišući prazne linije i komentare. U ovom slučaju, analiziraćemo dva Java fajla:
   
     **Calculator.java**
   
     **Start.java**


=Ukupan broj linija koda (LOC)=

Calculator.java: 66

Start.java: 26

Ukupno LOC za kompletan projekat: 66 + 26 = 92


=Neformalni pregled koda i statička analiza=

Sažetak zapažanja sa analize oba fajla:

**Fajl: Calculator.java**

- Broj linija koda: 66
  
_Zapažanje:_
- Linija 3: Static polje finalResult je javno i može da dovede do nepredvidivih rezultata kada se koristi u višekratnim pozivima metode Run, jer njegovo stanje može ostati između poziva.
- Linije od 18 do 22: Static metoda ToString() bi trebala da koristi konvencionalni naziv metoda (npr. toString()).
- Linija 25: Ova metoda (Run) vraća vrednost kao string bez rukovanja izraza koji mogu izazvati greške prilikom parsiranja.
- Linije od 43 do dalje su komplikovane; mnogo uslovnih grana čini kod teškim za razumevanje i održavanje.



**Fajl: Start.java**

- Broj linija koda: 26
  
_Zapažanje: _

- Linija 10: Postoji mogućnost curenja resursa – ako se scanner ne zatvori u svim situacijama može uzrokovati curenje memorije.
Način rukovanja izlazom (System.out.println(Calculator.Run(Expression));) nije dovoljno robustan – treba dodati više obrade grešaka kako bi se korisniku olakšao proces korišćenja.


_Preporučene izmene_
- Razmotriti korišćenje lokalne varijable umesto static varijable kada je to moguće kako bi se sprečila neželjena promena stanja između poziva funkcijama.
- Refaktorisati kompleksne metode tako da budu manje i lakše razumljive, koristeći pomoćne metode gde je to potrebno.
- Dodati jasnu dokumentaciju ili komentare na kritične delove koda radi bolje razumljivosti i održavanja u budućnosti.
