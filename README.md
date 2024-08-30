# Mengi og vensl

## Leiðbeiningar

- **Öll svör verða að vera rökstudd með skýrri röksemdafærslu.** Ekki verður veitt stig fyrir svör
  án rökstuðnings.
- **Tryggið skýrleika og skipulag í uppsetningu.** Þið megið nota verkfæri eins og iPad fyrir
  útreikninga þar sem það á við. Hlaðið svo upp PDF útgáfu af lausninni ykkar.
- Þetta er hópverkefni, sem fer fram hér. **Notið PR til að fara yfir lausnir hvers annars.**
  Mikilvægt er að allir séu virkir þátttakendur.
- **Óskýr uppsetning hefur áhrif á stigagjöf verkefnisins.**
- Gangi ykkur vel!

Verkefnið byggir á virku samstarfi í gegnum GitHub þar sem notkun á branches, commitum, og pull
requestum er mikilvæg. Branches ættu að vera vel skipulagðar með skýrum og rökréttum nöfnum sem
endurspegla þemu eða virkni sem unnið er að. Commit skilaboð skulu vera skýr og lýsa þeim
breytingum sem gerðar eru, þar sem samhengi á milli breyttra skráa er augljóst. Mikilvægt er að
README skjalið sé uppfært reglulega og innihaldi skýrar leiðbeiningar um uppsetningu, notkun, og
breytingar á verkefninu.

Samvinna í teyminu er lykilatriði þar sem allir liðsmenn taka virkan þátt í þróun verkefnisins. Það
skal tryggja jafna dreifingu á commitum, branches, og pull requestum meðal liðsmanna. Ákvarðanir
skulu teknar í sameiningu, með virku samráði í gegnum code reviews og viðbrögð við breytingum. Það
er mikilvægt að hver og einn liðsmanna leggi sitt af mörkum í samræmi við sína styrkleika og að
þátttaka sé jöfn og vel skipulögð. Þetta stuðlar að sterkri teymisvinnu þar sem allir taka ábyrgð á
árangri verkefnisins.

Heildarstigagjöf fyrir GitHub notkun og samvinnu/virkni byggir á því hversu vel verkefnið uppfyllir
þessi skilyrði, með 5 stig fyrir GitHub notkun og 5 stig fyrir samvinnu og virkni í teyminu.

## 1. Mengjafræði (20 stig)

**Látum $A$ og $B$ vera hlutmengi alsherjarmengisins $U$. Notið skilgreiningar á
mengjahugtökum og þekktar umritunarreglur til að sýna að:**

a. **Sýnið að sniðmengi $A \cap B$ má skrifa sem:**

$$ A \cap B = A \setminus (A \setminus B) $$

   
b. **Sýnið að sammengi \(A \cup B\) má skrifa með hjálp mismunamengja:**  

$$ A \cup B = (A \setminus B) \cup B $$

Sýnið útreikningana og notið skilgreiningar á sammengi $\(\cup\)$, sniðmengi $\(\cap\)$,
og mismengi $\(\setminus\)$, og stærðfræðilega rökfærslu.

## 2. Veldismengi (20 stig)

**Látum $P(A)$ vera veldismengið af menginu $A$. Sýnið hvort að $P(A) \subseteq P(P(A))$ sé
alltaf það sama og tómamengið. Rökstyðjið af hverju eða af hverju ekki.** (20 stig)

Skýrið ítarlega með röksemdum hvort mengið $P(A)$ sé eða sé ekki hlutmengi af $P(P(A))$. Notið
dæmi til að styðja röksemdir ykkar.

## 3. Vensl (25 stig)

**Sýnið og skýrið eftirfarandi:**

a. **Dæmi um vensl á mengi sem eru bæði samhverf og andsamhverf.** (10 stig)

b. **Munur á milli falla og vensla.** (5 stig)

Skýrið ítarlega hvað gerir vensl samhverf og andsamhverf og nefnið dæmi. Skýrið einnig muninn á
falli og vensli og gefið gott sýnidæmi um muninn.

## 4. Vensl á heiltölum (25 stig)

**Búið til vensl á mengi heiltalnanna $A = \{1, 2, 3, 4\}$ með fylki í `Python` eða `R` samkvæmt
eftirfarandi leiðbeiningum:**

1. Notið afmælisdagana ykkar til að setja slembifræ (e. random seed).
2. Búið til $4 \times 4$ fylki með slembibreyttum gildum sem eru 0 eða 1.
3. Forritið virkni sem skoðar eiginleika venslanna: athugið hvort þau
   séu sjálfhverf, samhverf, andsamhverf, og gegnvirk.
4. Sannreynið niðurstöður forritsins með því að skoða venslin myndrænt með örvaneti.

Athugið, þið þurfið að uppfæra `README` skjalið til að útskýra hvernig eigi að keyra kóðann ykkar
(og hvaða pakka þarf að setja upp, ef við á). Þar sem þið eruð að endurtaka þetta fyrir allar
afmælisdaga hópmeðlima þá er ráðlagt að setja upp fall sem tekur inn dagsetninguna og skilar
niðurstöðum.

### Python Kóði

```python
# Búa til slembifræ/seed út frá dagsetningunni
seed = int(f"{dd:02d}{mm:02d}{yyyy}")
np.random.seed(seed)

# Búa til 4x4 slembifylki með 0 eða 1
fylki = np.random.randint(0, 2, size=(4, 4))

# Endirskrifa dagssetninguna á formið "dd-mm-yyyy"
formatted_date = f"{dd:02d}-{mm:02d}-{yyyy}"

# Prenta niðurstöður:
print(f"Fylkið fyrir dagsetninguna {formatted_date} og seed {seed}:")
print(fylki)
print()
```

### R Kóði

```r
# Setja slembifræ með dagsetningu
dd <- 17
mm <- 6
yyyy <- 1944
seed <- as.numeric(paste0(dd, sprintf("%02d", mm), yyyy))
set.seed(seed)

# Búa til fylki
fylki <- matrix(round(runif(4 * 4, 0, 1)), nrow = 4)

# Endurskrifa dagsetningu
formatted_date <- sprintf("%02d-%02d-%04d", dd, mm, yyyy)

# Prenta niðurstöður
cat("Fylkið fyrir dagsetninguna", formatted_date, "og seed", seed, ":\n")
print(fylki)
cat("\n")
```
