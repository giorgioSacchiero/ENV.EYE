# Env.Eye
20 Years Arduino Contest Project

versione in italiano:

ENV.EYE è il progetto di una stazione meteo autonoma sperimentale. L’idea è nata dall’esigenza di dar vita a qualcosa di originale sfruttando le potenzialità e le versatilità delle soluzioni Arduino. 
Nel nostro caso abbiamo voluto rivisitare il modello classico della stazione meteo IoT, con alcune peculiarità: un contatore Geiger capace di funzionare con un’alimentazione in bassissima tensione (attorno ai 2.2 Volt) e la possibilità di rendere il tutto indipendente attraverso un pannello fotovoltaico e due supercondensatori come riserva di energia. Ciò ci ha ovviamente vincolati a prestare la massima attenzione ai consumi, in ogni operazione e/o misura eseguita.
Complessivamente il progetto si occupa della raccolta delle variabili caratteristiche dell’ambiente (temperatura, umidità, pressione atmosferica, ecc.) e del loro caricamento on-line come un’occhio sull’ambiente, da cui il nome “Env.Eye”. Per raggiungere lo scopo sono stati realizzati due dispositivi: un modulo chiamato Spot che raccoglie e invia i dati ambientali al secondo modulo chiamato Hub, che ha il compito di rendere disponibili i dati acquisiti in una bacheca on-line realizzata con Arduino Cloud.

parte elettronica:

parte meccanica:
- materiali:
    - filo o-ring / diam: 1.6 mm / lenght: 1 m;
    - 4 inserti M3 in ottone da inrerire a caldo;
    - 4 viti M3 con testa svasata;
    - 3 piedini M3 per PCB spessi 5mm;
    - maschi M3, M4 per filettare;
    - tavola di legno spessa 10/15 mm;
    - profili a "L" in acciaio.

- componenti:
    I componenti della scatola si trovano nella cartella "componenti" divisi tra le cartelle "Spot" e "Hub". I componenti da utilizzare nella costruzione sono le ultime versioni dei componenti, identificate dal pedice "_v3" per la verione 3 di un file. 

- stampe 3D:
    Consiglio per lo Spot è quello di stampare in materiali resistenti come PETG o ABS (io ho utilizzato PETG), mentre per l'Hub consiglio un materiale traslucido anche se poco resistente. questo perché il modulo presenta 3 led di diagnostica che devono essere visibili         dall'esterno.

- montaggio:
  - Spot:
    - Inserire a caldo gli inserti in ottone nei 4 fori sotto il componente "scatola_corpo_v3" e fissare il "tappino_TPU" sulla posta della USB con una vitina molto piccola, attorno a una M2 (va bene una vite autofilettante come no, a scelta);
    - tagliare a misura l'o-ring, inserirlo nella corsia tra "scatola_corpo_v3" e "scatola_coperchio_principale" e incollarne le estremità l'una con l'altra con dell'attach;
    - filettare i 3 fori delle torrette del coperchio_principale con maschio M3 e avvitarci i 3 piedini in ottone;
    - tagliare la tavola di legno con le misure del componente "legno" (trascurare lo spessore) e realizzare indicativamente il resto della struttura con cui ancorare lo spot a un qualsiasi supporto verticale;
    - praticare un foro sulla superficie inclinata della scatola per permettere il passaggio dei fili del pannello e incollarci sopra il pannello solare con del silicone per impermeabilizzare;
    - montare la scatola sulla tavola con viti autofilettanti per legno, mantenendo una spaziatura al di sotto della scatola di almeno 5 mm (lo spessore di un dado M4 / M5);
    - praticare sulla parte restante della tavola 8 fori filettati M4 per montare anemometro e pala per la direzione del vento e montarli.
      
        [fare attenzione a filettare i fori dal punto in cui la vite verrà avvitata, perchè potrebbe non essere abbastanza lungo il maschio per filettare fin dall'altra parte della tavola. Inoltre curarci di praticare bene i fori per non risciare disallineamenti]; 
    - connettere i sensori esterni alla scheda e chiudere il tutto.
     
  - Hub:

      molto più semplice dello Spot, basta inserire la schedina dell'Hub nella cava disegnata allo scopo, volendo fissare la scheda con viti M3 nei due fori della scheda e incastrare parte sotto con parte sopra. Fine.

parte di software e comunicazione:
