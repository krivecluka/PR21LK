# Končno poročilo

Odločil sem se, da bom delal analizo ekip Prve moške rokometne lige Slovenije. Na podlagi pridobljenih podatkov iz Rokometne zveze Slovenije bom obdelal sezone 2019/2020, 2020/2021 ter tekočo sezono 2021/2022, do 20. kroga. Najbolj me bodo zanimale ekipe, njihova uspešnost v ligi ter podobnosti.

Podatki, ki sem jih prejel s strani RZS, so bogati a nečisti. Zaradi GDPR so vsa imena, priimki ter ID-ji igralcev anonimizirani. Prav tako podatki ne vsebujejo ID-je ekip. Moja naloga je torej bila, da uredim in dodam manjkajoče podatke.

V excel datoteki, ki sem jo prejel, so tri tabele. Tekme, kjer je viden ID določene tekme, domače moštvo in gostujoče moštvo. V tabeli akcije je največ uporabnih podatkov. Najpomembnejši so čas tekme v sekundah, vrsta akcije ter pozicije strela. Akcij je preko 80 tisoč. Od zadnje tabele trenutno nimam nobene koristi, saj hrani le izračunane statistike iz tabele akcij. Morda se kasneje izkaže, da bo še uporabna. 

Z urejanjem sem začel pri tabeli akcij, kjer sem zgoščene ID-je igralcev zaradi boljše berljivosti in preglednosti spremenil v numerične vrednosti. Izbrisal sem stolpca "ime" in "priimek", saj so to naključni nizi. Zgoščene IDje igralcev sem nadomestil z novo pridobljenimi.

Nato sem se lotil poimenovanja ekip. Poiskal sem vse unikatne vrednosti za domače ekipe iz tabele tekem in jim dodelil ID-je.

<p align="center">
  <img src="https://github.com/krivecluka/PR21LK/blob/main/img/ekipe.PNG"/>
</p>

Za tem sem primerjal ID-je tekem med obema tabelama. Ugotovil sem, da ima tabela akcije zabeleženih pet tekem manj kot tabela tekme. Zaradi potencialnih težav sem te tekme izbrisal tudi iz druge tabele. S tem sem se lahko lotil povezovanja posameznega igralca z ekipo. Tu se je pojavila dilema, kako reševati težavo z osamelci. Igralci, ki imajo manj kot tri tekme igrajo na domačih tleh, saj gre ponavadi za igralce mlajših kategorij, ki so dobili priložnost za igro pred domačimi navijači. Take igralce sem pripisal domači ekipi, čeprav to morda ni v vseh primerih pravilno. Igralcem, ki so zaigrali na dveh različnih tekmah s štirimi različnimi ekipami ni mogoče natančno pripisati ekipe, saj so po vsej verjetnosti od leta 2019 do danes ekipo najmanj enkrat zamenjali. Pripisal sem jih kar k zadnji domači ekipi, saj je najverjetneje, da je to njihov aktualni klub. Na koncu sem vsako akcijo povezal z ekipo, kar mi bo kasneje prišlo prav. Posodobljena tabela izgleda takole:

<p align="center">
  <img src="https://github.com/krivecluka/PR21LK/blob/main/img/akcije.PNG"/>
</p>

Za lažjo predstavo sem izrisal tudi graf pogostosti pojavitve posamezne ekipe v tabeli akcije. Ugotovil sem, da imajo nekatere ekipe več zabeleženih akcij kot druge. To lahko pomeni več stvari. Najbolj očitna je ta, da sta dve ekipi izpadli v nižjo ligo ter v letošnji sezoni več nista članici prve rokometne lige. Drug razlog je lahko tehnične narave. Težave so nastajale pri beleženju in shranjevanju podatkov. Nimajo vse ekipe istih pogojev za spremljanje statistike tekme. Nekatere ekipe si ne morejo privoščiti ustrezne opreme ali kadra. Tretji razlog je aktivnost in uspešnost ekip. Bolj kot je ekipa aktivna na igrišču, več akcij je zabeleženih, bolj je tudi uspešna. To bo tudi eno izmed vprašanj, na katere nameravam odgovoriti v svoji analizi. 

<p align="center">
  <img src="https://github.com/krivecluka/PR21LK/blob/main/img/akcije_barh.png"/>
</p>

Eden glavnih ciljev moje naloge je torej poiskati povezavo med številom akcij ter uspešnostjo ekipe v zadnjih treh sezonah. 
Namen imam tudi gručiti ekipe, ki so si po uspešnosti podobne. Zanimali me bodo trije vidiki: kako učinkovit napad ima ekipa, kako učinkovito obrambo ter koliko napak dela.

Zelo zanimiv atribut tabele je tudi pozicija strelov. Na tekmah se beleži, iz katere pozicije igralec strelja proti golu, v kateri del gola je žoga letela ter ali je bil strel uspešen. Zaradi tehničnih težav nekaterih ekip je teh podatkov malo, a dovolj, da bom lahko naredil napovedni model, ki bo napovedal, kakšna verjetnost obstaja, da bo iz določene pozicije dosešen zadetek. Za lažjo predstavo, kaj podatki pomenijo, sem dobil tudi sliko oštevilčenih pozicij strelov:

<h2>Gručenje ekip po uspešnosti </h2>

Želel sem pogrupirati ekipe glede na kvaliteto in uspešnost v ligi. Gručenja sem se lotil z ustvarjanjem novega znanja iz danih podatkov. Vsaki ekipi sem preštel povprečje akcij na tekmo v izbrani kategoriji. Kategorije akcij so: napad, obramba in tehnične napake. Pri napadu sem štel strele na gol, pridobljene 7 metrovke, pridobljene prekrške ter zabeležene asistence. K obrambi sodijo storjeni prekrški (storjen prekršek je, za razliko od drugih športov, pri rokometu dobrodošel), obrambe vratarja in narejeni bloki. Pod napake štejejo izključitve za dve minuti, koraki, met v blok, narejen prekršek za 7 metrovko, izgubljena žoga, zgrešen met ter rumen, rdeč, in moder karton. Vse omenjene akcije sem povprečil z odigranimi tekmami ekipe in jih razvrstil po vrsti. Ekipa z najboljšim rezultatom je dobila največ točk za omenjeno kategorijo. Na podlagi pridobljenih podatkov sem zgradil matriko, s pomočjo katere sem ekipe pogrupiral. 

<p align="center">
  <img src="https://github.com/krivecluka/PR21LK/blob/main/img/dendogram.png"/>
</p>

Rezultati so na prvi pogled zadovoljivi in predvidljivi. 
V SKUPINI 1 sta kluba iz Maribora in Ljubljane. Maribor v zadnjih letih ni več tako konkurenčen kot včasih, Ljubljana pa po uvrstitvi v prvo ligo nekaj let nazaj počasi pleza po lestvici, ter se vztrajno izbolšuje, a je v aktualni sezoni zopet izpadla iz elite. V tej skupini se nahajata kluba, ki spadata na spodnji del lestvice, a ne povsem na dno. 
V SKUPINI 2 so klubi iz dna lestvice. Tako Izola kot Koper sta nekonsistentna kluba, ki skozi leta prehajata med prvo in drugo ligo. Tudi letos igra Izola v drugi ligi, kjer ji je za las ušel preboj nazaj med elito. Tudi RK Slovenj Gradec je klub, ki zadnja leta ne dosega več vrhunskih rezultatov.
SKUPINA 3 je največja, zato je težko povezati vse ekipe po karakteristiki, a povezava med njimi vseeno obstaja. Gre za skupino, ki se že nekaj let izmenjuje na mestih od 2.- 6. v prvi slovenski rokometni ligi. Najuspešnejši ekipi med njimi sta Ribnica in Velenje, ki sta si karakteristično najbolj podobni. RK Gorenje Velenje je slovit slovenski rokometni klub, ki že vrsto let kot edini kljubuje Celju. Ekipi iz Novega mesta in Dobove sta kluba iz sredine lestvice. Podobna sta si po geografskem položaju, finančni moči in uspešnosti v preteklih sezonah. Oba sta pred približno 10 leti prešla iz druge lige. Oba dosegata konsistentne rezultate iz leta v leto. Par Loka in Trebnje sta prav tako že vrsto let v člana prve lige. Dosegata kanček boljše rezultate kot prejšni par.
Zadnja, SKUPINA 4 je največje presenečenje. RK Celje Pivovarna Laško je absolutni osamelec prve slovenske rokometne lige. Presenetljivo je to, da si po statistiki skupino deli z Ormožem. Celje je daleč najbolj uspešna ekipa v slovenski ligi. Redke so sezone, kadar Celje ni prvak. Predvidljivo bi bilo, da bi si lastilo svojo skupino. Ormož je presenečenje. Gre za dobro ekipo, ki je iz leta v leto boljša. Uspešnost podatkov lahko pripišemo borbeni in disciplinirani igri, ki pa ne prinese vedno rezultatov. O tem dejstvu priča tudi položaj na lestvici, ki niti približno ni tako visok kot položaj soseda v skupini 4.

<h2>Korelacija med uspešnostjo ekip in številom akcij </h2>

Eno izmed vprašanj, ki se mi je porajalo tekom izdelave te naloge je bilo poiskati povezavo med številom akcij ter uspešnostjo ekip. KOrelacijo sem izračunal s pomočjo Pearsonove formule. Vrednost korelacije je 0.47, kar pomeni da je korelacija pozitivna, a šibka.

<p align="center">
  <img src="https://github.com/krivecluka/PR21LK/blob/main/img/korelacija.png"/>
</p>

Na grafu je vidna šibka korelacija, kljub temu da so logotipi klubov na prvi pogled pometani. Lep primer uspešnosti ekipe in število zabeleženih akcij sta ekipi na samem vrhu, ter tista iz dna lestvice. Med tem, ko je RK Celje v desnem kotu zgoraj, kar pomeni zelo uspešno in nadpovprečno veliko zabeleženih akcij, je ekipa iz Izole v levem kotu spodaj, kar pomeni slabši uspeh, ter malo zabeleženih akcij. Njuni uspehi na lestvici lige govorijo podobno zgodbo.


<h2>Napoved uspešnosti strela </h2>

Za pravilno napoved sem uporabil klasifikacijski napovedni algoritem naključni gozd. Množico sem razdelil na učno (75%) in testno (25%). Model sem zgradil uspešno z točnostjo napovedi 75%. Poskusil sem tudi z algoritmom SVM in odločitvenim drevesom, a sta rezultata malenkost slabša. Podatke sem razdelil tri atribute in klasifikacijski razred. Prvi atribut je ID ekipe, saj bomo upoštevali uspešnost vratarja posamezne ekipe. Ker se vratarji med sabo razlikujejo po kvaliteti, se mi je zdel to koristen podatek. Teža atributa pri napovedi rezultatov je znašala okoli 30 %. Drugi atribut je bila pozicija začetka meta. Teža je znašala dobrih 20 %, kar nam pove, da je bolj pomembno kdo je branil strel oz. v kateri kot gola je bil strel vržen. Tretji atribut se je izkazal za najpomembnejšega in sicer gre za kot gola, kamor je bil strel vržen. Teža je bila dobrih 45 %. Kot klasifikacijski razred je nastopala uspešnost meta. Če je strelec dosegel gol je bila zabelčežena vrednos ZADETEK, sicer pa OBRAMBA.

Ker želimo kot klub napredovati in biti bolj uspešni, ciljamo na vrh. Tam sedi RK Celje. Za prikaz rezultatov sem se torej odločil, da preizkusimo celjskega vratarja. Vprašanje je kam streljati, da bo verjetnost zadetka največja. Analiziral sem strele iz vsake pozicije rokometnega igrišča in dobil koristne informacije, ki mi lahko pomagajo pri napredovanju in izboljšajo kvalitete meta.

<p align="center">
  <img src="https://github.com/krivecluka/PR21LK/blob/main/img/streli_GIF.gif"/>
</p>

Polje obarvano z vijolično je pozicija meta, opisana tudi v levem zgornjem kotu. Sivo obarvana polja so meti, ki so zgrešili cilj - gol. Pri teh metih lahko predvidimo, da bo uspešnost zadetka zelo nizka oz. nična. Zelena polja so optimalna za strel. Vsi streli, ki bodo uspešno naciljani na zeleno polje, imajo zelo dobro verjetnost, da bodo pristali v golu. Rumena polja so srednje kvalitetni meti, ki ne pristanejo vedno v golu. So dober začetek, a ciljati je potrebno bolje. Rdeča polja so ljuba vratarju, saj je tam največ strelov v preteklosti zaustavil. To so polja, ki jih vratar pokrije - streli, ki letijo v vratarja. Pri vsaki sliki je tudi opis najšibkejše točke vratarja, ter odstotek uspešnosti dobvro namerjenega strela.

Rezultati so zadovoljivi. Lepo vidimo, kako nihajo odstotki strelov v primerjavi z začetno pozicijo igralca. Manjši kot je kot meta, manjša verjetnost zadetka obstaja. Če se igralec pomakne bolj na sredino igrišča, kjer je kot gola večji, potem bo tudi bolj uspešen. Omeniti je potrebno tudi razdaljo meta od gola. Dlje kot je igralec, bolj uspešen je vratar. Omeniti je treba tudi pozicijo 7, ki ponazarja izvajanje 7 metrov. V tem primeru se igra ustavi, igralec pa mora iz mesta - brez skoka izvesti strel. Vratarji so v tem primeru dokaj uspešni, tako glede na razdaljo kot na kot meta. Velikokrat tukaj igra človeška psiha svojo vlogo, saj se od strelca pričakuje, da zadane.

Optimalni kot meta so, kot je prikazano na slikah, levi in desni kot zgoraj, ki jih vratar težko doseže, ter kot 18, ki ponazarja praznino pod vratarjevimi nogami. Zadnja ugotovitev je predvidljiva, saj je glavna taktika vratarja pri branjenju skok. S tem poskuša pokriti srednje visoke mete, ki so, kot je prikazano, tvegani in manj uspešni. Daleč najbolj branjena pozicija je 13, ki prikazuje sredino gola. Logično je, da so streli v to pozicijo najmanj uspešni, saj so to streli v vratarja.

Največja pomankljivost modela je odstotek uspešnosti optimalnih metov, ki je po mojem mnenju previsok. To lahko pripišemo premalemu in nekonsistentnemu številu podatkov, ter malomarnosti oz. netočnosti beleženja statistike, saj se ne vidi vedno najbolje, kam je žoga letela. Razlike med pozicijami so majhne, uspešen strel pa vedno izgleda, kot da je letel ob vratnici gola.
