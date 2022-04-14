# Vmesno poročilo

Odločil sem se, da bom delal analizo ekip 1. moške rokometne lige slovenije. Na podlagi pridobljenih podatkov iz RZS bom obdelal sezone 2019/2020, 2020/2021, ter tekočo sezono 2021/2022, do 20. kroga. Najbolj me bodo zanimale ekipe, njihova uspešnost v ligi ter podobnosti.

Podatki, ki sem jih prejel s strani RZS so bogati, a nečisti. Zaradi GDPR so vsa imena, priimki ter id igralcev anonimizirani. Prav tako podatki ne vsebujejo ni id ekip. Moja naloga torej je bila, da uredim in dodam manjkajoče podatke.

V excel datoteki, ki sem jo prejel, so tri tabele. Tekme, kjer je viden id določene tekme, ter domače in gostujoče moštvo. V tabeli akcije je največ uporabnih podatkov. Najpomembnejši so čas tekme v sekundah, vrsta akcije ter pozicije strela. Akcij je preko 80 tisoč. Od zadnje tabele trenutno nimam nobene koristi, saj hrani le izračunane statistike iz tabele akcij. Morda se kasneje izkaže, da bo še uporabna. 

Z urejanjem sem začel pri tabeli akcij, kjer sem zgoščene IDje igralcev zaradi boljše berljivosti in preglednosti spremenil v numerične vrednosti. Izbrisal sem stolpca "ime" in "priimek", saj so to naključni nizi. Zgoščene IDje igralcev sem nadomestil z novo pridobljenimi.

Nato sem se lotil poimenovanja ekip. Poiskal sem vse unikatne domače ekipe iz tabele tekem, ter jim dodelil IDje.

<p align="center">
  <img src="https://github.com/krivecluka/PR21LK/blob/main/img/ekipe.PNG"/>
</p>
