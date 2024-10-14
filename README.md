# turnos-app

Aquesta aplicació de torns permet gestionar una cua de persones que demanen torn, mostrant el número de torn i el nom de la persona a una pantalla principal. Està dissenyada per ser senzilla d'usar tant en dispositius mòbils com en escriptoris, gràcies a un disseny responsive que s'adapta a diferents mides de pantalla.

## Característiques principals
Formulari per demanar torn: Els usuaris poden introduir el seu nom en un formulari senzill i demanar un torn fent clic a un botó. Aquest nom s'enviarà a la llista de torns pendents, amb un número assignat de manera automàtica.

* **Visualització del torn actual:** La pantalla principal mostra el número i el nom del torn actual, és a dir, la primera persona de la llista que està esperant ser atesa.

* **Gestió dels torns:** Un botó permet atendre el torn actual i, automàticament, es mostrarà la següent persona en la cua. D'aquesta manera, la gestió dels torns es fa de manera seqüencial i transparent.

* **Llista de tots els torns:** També es pot veure una llista completa de les persones que han demanat torn, actualitzada en temps real. Això permet veure qui està esperant i l'ordre en què seran atesos.

## Com utilitzar l'aplicació

**Demanar un torn:**

A la part superior de l'aplicació, trobaràs un formulari amb un camp per introduir el teu nom.
Escriu el teu nom i prem el botó "Pedir Turno".
A partir d'aquí, el teu torn s'afegirà a la cua i podràs veure el teu número de torn.
Atendre un torn:

Quan estiguis llest per atendre una persona, apareixerà un botó "Atender Turno" a la pantalla principal.
En prémer aquest botó, la persona que està en el primer lloc de la cua serà atesa, i el següent torn apareixerà automàticament a la pantalla.
Visualitzar la llista de torns:

A la part inferior de la pantalla, es mostra una llista amb els noms i números dels torns pendents, així com la persona que està sent atesa en aquell moment.
Adaptabilitat a dispositius
L'aplicació ha estat dissenyada per ser completament responsive, la qual cosa significa que es veurà i funcionarà bé tant en pantalles petites, com telèfons mòbils, com en pantalles més grans, com tablets o ordinadors d'escriptori. Els elements de la interfície s'ajusten automàticament perquè siguin fàcils de llegir i utilitzar en qualsevol dispositiu.

## Casos d'ús
* Clíniques o consultoris: Per gestionar els torns d'atenció als pacients.
* Botigues o oficines: On cal gestionar cues de persones esperant ser ateses.
* Esdeveniments: Per organitzar l'ordre d'atenció o participació en esdeveniments amb molta gent.

Aquesta aplicació és ideal per a qualsevol situació en què es necessiti un sistema simple i efectiu per gestionar cues de manera transparent i àgil.
# Instal·lació

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
