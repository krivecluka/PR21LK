# Vmesno poročilo

Odločil sem se, da bom delal analizo ekip 1. moške rokometne lige slovenije. Na podlagi pridobljenih podatkov iz RZS bom obdelal sezone 2019/2020, 2020/2021, ter tekočo sezono 2021/2022, do 20. kroga. Najbolj me bodo zanimale ekipe, njihova uspešnost v ligi ter podobnosti.

Podatki, ki sem jih prejel s strani RZS so bogati, a nečisti. Zaradi GDPR so vsa imena, priimki ter id igralcev anonimizirani. Prav tako podatki ne vsebujejo ni id ekip. Moja naloga torej je bila, da uredim in dodam manjkajoče podatke.

V excel datoteki, ki sem jo prejel, so tri tabele. Tekme, kjer je viden id določene tekme, ter domače in gostujoče moštvo. V tabeli akcije je največ uporabnih podatkov. Najpomembnejši so čas tekme v sekundah, vrsta akcije ter pozicije strela. Akcij je preko 80 tisoč. Od zadnje tabele trenutno nimam nobene koristi, saj hrani le izračunane statistike iz tabele akcij. Morda se kasneje izkaže, da bo še uporabna. 

Z urejanjem sem začel pri tabeli akcij, kjer sem zgoščene IDje igralcev zaradi boljše berljivosti in preglednosti spremenil v numerične vrednosti. Izbrisal sem stolpca "ime" in "priimek", saj so to naključni nizi. Zgoščene IDje igralcev sem nadomestil z novo pridobljenimi.

Nato sem se lotil poimenovanja ekip. Poiskal sem vse unikatne domače ekipe iz tabele tekem, ter jim dodelil IDje.

<p align="center">
  <img src="https://github.com/krivecluka/PR21LK/blob/main/img/ekipe.PNG"/>
</p>

Nato sem primerjal ID tekem iz obeh tabel. Ugotovil sem, da ima tabela akcije zabeleženih 5 tekem manj kot tabela tekme. Zaradi potencialnih bodočih težav sem te tekme izrisal tudi iz druge tabele. S tem sem se lahko lotil povezovanja posameznega igralca z ekipo. Tu se je pojavila dilema, kako reševati težavo z osamelci. Igralci, ki imajo manj kot tri tekme igrajo na domačih tleh, saj gre ponavadi za igralce mlajših kategorij, ki so dobili priložnost za igro pred domačimi navijači. Take igralce sem pripisal domači ekipi, čeprav to morda ni v vseh primerih pravilno. Igralcem, ki so zaigrali na dveh različnih tekmah s štirimi različnimi ekipami ni mogoče natančno pripisati ekipe, saj so po vsej verjetnosti od leta 2019 do danes ekipo najmanj enkrat zamenjali. Pripisal sem jih kar k zadnji domači ekipi, saj je najverjetneje, da je to njihov aktualni klub. Na koncu sem vsako akcijo povezal z ekipo, kar mi bo kasneje prišlo prav. Posodobljena tabela izgleda takole:

<p align="center">
  <img src="https://github.com/krivecluka/PR21LK/blob/main/img/akcije.PNG"/>
</p>

Za lažjo predstavo sem izrisal tudi graf pogostosti pojavitve posamezne ekipe v tabeli akcije. Ugotovil sem, da imajo nekatere ekipe več zabeleženih akcij kot druge. To lahko pomeni več stvari. Najbolj očitna je ta, da sta 2 ekipi izpadli v nižjo ligo, ter v letošnji sezoni več nista članici prve rokometne lige. Drug razlog je lahko tehnične narave pri beleženju in shranjevanju podatkov. Nimajo vse ekipe istih pogojev za spremljanje statistike tekme. Nekatere ekipe si ne morejo privoščiti opreme, spet druge kadra. Tretji razlog je aktivnost in uspešnost ekip. Bolj kot je ekipa aktivna na igrišču, več akcij je zabeleženih, bolj je tudi uspešna. To bo tudi eno izmed vprašanj, na katere nameravam odgovoriti v svoji analizi. 

<p align="center">
  <img src="https://github.com/krivecluka/PR21LK/blob/main/img/akcije_barh.png"/>
</p>

Eden glavnih ciljev moje naloge je torej poiskati povezavo med številom akcij ter uspešnostjo ekipe v zadnji treh sezonah. Zanima me tudi razlog, zakaj so neuspešne ekipe neuspešne in ali se da kaj popraviti. Pri tem vprašanju sem bom osredotočil predvsem na težave s koncentracijo. Poskušal bom najti ekipo, ki dela največ neizsiljenih, tehničnih napak. Zanima me tudi nasplošno, v kateri minuti tekme se najbolj pogosto pojavljajo napake v celotni ligi.

Namen imam tudi gručiti ekipe, ki so si po uspešnosti podobne. Zanimalo me bo pet vidikov. Kako učinkovit napad ima ekipa, kako učinkovito obrambo, koliko točk zbere na tekmo, koliko napak dela ter fairplay ekipe.

Zelo zanimiv atribut tabele je tudi pozicija strelov. Na tekmah se beleži iz katere pozicije igralec strelja proti golu, v kateri del gola je žoga letela, ter ali je bil strel uspešen. Zaradi tehnilnih težav nekaterij ekip, je teh podatkov malo, a dovolj, da bom lahko naredil napovedni model, ki bo napovedal, kakšna verjetnost obstaja, da bo iz določene pozicije dosešen zadetek. Za lažjo predstavo, kaj podatki pomenijo, sem dobil tudi sliko oštevilčenih pozicij strelov:


<p align="center">
  <img src="https://github.com/krivecluka/PR21LK/blob/main/img/pozicije%20strelov.png"/>
</p>
