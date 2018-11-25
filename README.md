Proiect Tehnologii Web - echipa Rose Team
Monitorizarea apariţiei unei firme pe Twitter 
(integrat cu Twitter API)


1. Context:
Twitter este una dintre cele mai active platforme de social media, ocupând locul al doilea după Facebook. Feed-ul rapid și conversațiile în timp real au plasat platforma atât în preferințele utilizatorilor individuali, cât și în cele ale companiilor.
Brand-urile nu au nevoie de un buget prea mare pentru a reuși pe Twitter, procesul fiind unul repetitiv, odată ce este făcut așa cum trebuie. 
Interacțiunea dintre companie și posibilii clienți se face pe baza postărilor efectuate, API-ul folosit de Twitter putând monitoriza nivelul de implicare, prin reply-uri, numărul de urmăritori, link-uri, hashtag-uri sau numărul de accesări ale unui profil.

2. Descriere aplicație:
Aplicația va monitoriza apariția unei firme pe Twitter. Pentru realizarea acestui lucru, aplicația se va folosi de API-ul Twitter, resursele gratuite ale acestei rețele sociale putând fi accesate pe https://developer.twitter.com/en/docs.
La deschiderea aplicației utilizatorul va trebui să se conecteze la contul propriu sau să își creeze unul în cazul în care nu a mai folosit aplicația până în acel moment.
După logare, va fi redirecționat către dashboard, unde va putea introduce fie numele companiei căutate, fie un domeniu pentru a vedea lista tuturor firmelor care activează în acesta. Dacă se va utiliza căutarea după nume, va fi deschisă o fereastră în care să se prezinte date despre compania respectivă (id_companie, denumire_companie, descriere, locație, data_înregistrare, cod_domeniu), având ulterior și o opțiune de a vedea evoluția acesteia în timp.
În cazul în care căutarea se va face după domeniu, vor fi listate toate companiile care activează în domeniul respectiv, având opțiunea de a vedea detalii ulterioare despre compania selectată sau o statistică la nivel de domeniu pentru a observa cele mai populare pagini (nr. followers).
Utilitatea aplicației este dată de posibilitatea analizării evoluției brand-urilor, pentru a putea realiza ulterior strategii de marketing.

	Backend-ul aplicației va fi de tip RESTful și va accesa, cu ajutorul unui API de persistenţă, atât date stocate într-o bază de date relațională, cât și date generate de un serviciu extern. REST API-ul Twitter permite citirea și scrierea de date Twitter, mai exact permite crearea de noi utilizatori, citirea profilelor utilizatorilor și a datelor urmăritorilor.
Frontend-ul aplicației va fi de tip Single Page Application și va fi realizat cu un framework bazat pe componente (React.js).


3. Entități:
tabela Companie: id_companie, denumire_companie, descriere, locație, data_înregistrare, cod_domeniu, nr_followers (1 la mulți cu tabela Tweet);
tabela Utilizator: username, parolă, id_user (relație 1 la mulți cu tabela  Companie);
tabela Favorite: id_companie;
tabela Tweet: tweet_id, tweet_text, oră_înregistrare, id_companie;
tabela Domeniu: cod_domeniu, denumire_domeniu (relație 1 la mulți cu tabela Companie).




4. User story-uri:
un user se poate loga în aplicație, completând câmpul de username și cel de parolă;
un user se poate înregistra în cazul în care nu are deja un cont, completând câmpurile: nume, prenume, username, parola;
un user poate căuta date despre o companie, introducând într-o bară de search numele acesteia (datele pe care le va putea vedea vor fi: id-ul, denumirea, descrierea, locația, data înregistrării și domeniul în care activează);
utilizatorul poate să vadă evoluția companiei căutate, în funcție de interacțiunea paginii cu ceilalți următori/utilizatori ai platformei Twitter;
un user poate vedea istoricul de tweets postate de o companie, accesând butonul destinat acestei căutări din pagina unde vizualizează date despre companie (cea la care se ajunge în punctul descris anterior);
un utilizator poate introduce într-o bară de search domeniul de activitate dorit, pentru a vedea toate companiile care activează în acesta, putând urmări și o statistică în funcție de numărul de urmăritori;
un utilizator se poate deloga de pe contul propriu

5. Câteva pagini ale aplicației



