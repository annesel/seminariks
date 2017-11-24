---
title       : Mõni näide
description : Teeme läbi mõne näiteülesande



---
## Vektori moodustamine, tehted vektoriga
```yaml
type: NormalExercise
key: a92cacc5b0
lang: r
xp: 100
skills: 1
```

- Üksikuid arve või tekstiväärtusi saab kokku panna vektoriks funktsiooni `c()` (*combine*) abil. 
- Veel võimalusi vektorite moodustamiseks:
    * `1:5                 # arvujada 1, 2, 3, 4, 5`
    * `rep(1:3, times = 2) # vektorit elementidega 1, 2, 3 korrata 2 korda`
    * `seq(3, 9, by = 2)   # arvujada sammuga 2: 3, 5, 7, 9`
- Kui teha vektorobjektidega arvtusi, siis tehted tehakse läbi iga vektori elemendiga.



`@instructions`
- Tee läbi näited 1 kuni 3.
- **Ülesanne 1.** Teisenda temperatuurid celsiuse skaalalt fahrenheiti skaalale ($^\circ\hspace{-0.1em} F = ^\circ\hspace{-0.1em} C \times \frac{9}{5} + 32$). Omista tulemus muutujale `Fahrenheit` ja prindi see ekraanile.
- **Ülesanne 2.** Vektoris `lisa` on veel kaks õhutemperatuuri($^\circ\hspace{-0.1em} C$). Prindi see vektor ekraanile.
- **Ülesanne 3.** Kasutades funkstiooni `c()` moodusta vektor nimega `temp2`, mille esimesed 9 elementi  on temperatuurid vektorist `temp` ja järgmised 2 temperatuurid vektorist `lisa`. Väljasta tulemus ekraanile.



`@hint`
- Funktsiooni `c()` saab lisaks üksikutest väärtustest vektori tegemisele kasutada ka olemasolevate vektorite kombineerimiseks: `c(vektor1, vektor2)`.



`@pre_exercise_code`
```{r}
lisa <- c(-24.9, -16.1)
names(lisa) <- c("Mustvee", "Keila")
```

`@sample_code`
```{r}
# Näide 1: Moodustame 2 vektorit, millest ühes on kirjas temperatuurid (20.01.2010 kell 10), teises ilmajaamad, kus need on mõõdetud :
temp <- c(-6.2, -12.9, -13.0, -15.4, -16.1, -16.9, -17.0, -19.6, -19.9)
jaam <- c("Ruhnu", "Kihnu", "Pakri", "Tallinn", "Pärnu", "Kunda", "Kuusiku", "Võru", "Jõgeva")            

# Näide 2: Väljastame tulemused ekraanile
temp; jaam

# Näide 3: Paneme temperatuuridele jaamanimed juurde ja vaatame tulemust
names(temp) <- jaam
temp

# Ülesanne 1: Teisenda temperatuurid celsiuse skaalalt fahrenheiti skaalale (asenda alakriips vajaliku tehtega) ja prindi tulemus ekraanile
Fahrenheit <- ___________________ 
Fahrenheit 

# Ülesanne 2. Prindi ekraanile vektor nimega 'lisa'


# Ülesanne 3. Moodusta nõutud kujul uus vektor, selleks asenda alakriipsud vajalike objektidega. Prindi tulemus ekraanile.
temp2 <- c(_____, _____) 
temp2
```

`@solution`
```{r}
# Näide 1: Moodustame 2 vektorit, millest ühes on kirjas temperatuurid (20.01.2010 kell 10), teises jaamad, kus need on mõõdetud :
temp <- c(-6.2, -12.9, -13.0, -15.4, -16.1, -16.9, -17.0, -19.6, -19.9)
jaam <- c("Ruhnu", "Kihnu", "Pakri", "Tallinn", "Pärnu", "Kunda", "Kuusiku", "Võru", "Jõgeva")            # NB! Kui jutumärgid unustada, otsib R vastava nimega objekte!

# Näide 2: Väljastame tulemused ekraanile
temp; jaam

# Näide 3: Paneme temperatuuridele jaamanimed juurde ja vaatame tulemust
names(temp) <- jaam
temp

# Ülesanne 1: Teisenda temperatuurid celsiuse skaalalt fahrenheiti skaalale (asenda alakriipsud vajaliku tehteda) ja prindi tulemus ekraanile
Fahrenheit <- temp * 9/5 + 32
Fahrenheit 

# Ülesanne 2: Prindi ekraanile vektor nimega 'lisa'
lisa

# Ülesanne 3: Moodusta nõutud kujul uus vektor, selleks asenda alakriipsud vajalike objektidega. Prindi tulemus ekraanile.
temp2 <- c(temp, lisa) 
temp2
```

`@sct`
```{r}

# ega etteantud vektorei pole muudetud
test_predefined_objects("temp",
    undefined_msg = "Oled vektori `temp` kustutanud! Alusta uuesti.", 
    incorrect_msg = "Muutuja `temp` väärtused on muudetud! Alusta uuesti.")
    
    
test_predefined_objects("jaam",
    undefined_msg = "Oled vektori `jaam` kustutanud! Alusta uuesti.", 
    incorrect_msg = "Muutuja `jaam` väärtused on muudetud! Alusta uuesti.")
    
test_predefined_objects("lisa",
    undefined_msg = "Oled vektori `lisa` kustutanud! Alusta uuesti.", 
    incorrect_msg = "Muutuja `lisa` väärtused on muudetud! Alusta uuesti.")
        
        


# 1
test_object("Fahrenheit", 
    undefined_msg = "Muutujat `Fahrenheit` pole defineeritud!", 
    incorrect_msg = "Kontrolli, kas omistad muutujale `Fahrenheit` õige tehte.")

test_output_contains("Fahrenheit", 
    incorrect_msg = "Prindi vektor `Fahrenheit` ekraanile!")

# 2
test_output_contains("lisa", 
    incorrect_msg = "Vektor `lisa` pole välja prinditud!")

# 3
test_object("temp2", 
    undefined_msg = "Puudub vektor `temp2`. Proovi uuesti!", 
    incorrect_msg = "Vektori `temp2` väärtus ei vasta nõutule!")
    
test_output_contains("temp2",
    incorrect_msg = "Vektor `temp2` pole välja prinditud!")



success_msg("Super! Liigu järgmise ülesande juurde.")

```
















