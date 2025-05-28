# 2. Declaració d’una funció

Declarar una funció simplement significa crear-la perquè després puga ser anomenada (utilitzada) des d'un altre lloc del codi del nostre programa. Una funció s'estructura en **capçalera** i **cos**.

La capçalera es declara en una sola línia i es compon de:

- Modificadors de funció: Existeixen molts però els veurem en futures unitats. (Per ara només utilitzarem `public static`).
- Tipus retornat: El tipus de dada que retornarà la funció, com per exemple `int`, `double`, `char`, `boolean`, `String`, etc. Si la funció no retorna res s'indica mitjançant `void`.
- Nom de la funció: Identificador únic per a cridar a la funció.
- Llista de paràmetres: Indica els tipus i noms de les dades que se li passaran a la funció quan siga anomenada. Poden ser més d'un o cap.

El cos és un bloc de codi entre claus { … } que s'executarà quan des d'una altra part del codi utilitzem la funció.

```java
[*Modificador_de_funció] Tipus_retornat Nom_de_funció (llista_de_paràmetres)
{
...
}
```

Exemples de funcions:

```java
public static void imprimeixHolaMon() { 
System.out.println(“Hola mon”);
}
```

Aquest és un exemple molt senzill d'una funció anomenada ‘imprimeixHolaMon’, que no té paràmetres d'entrada (no hi ha res entre els parèntesis) i no retorna cap valor (indicat per void). Quan la diguem l'única cosa que farà serà escriure per pantalla el missatge “Hola mon”.

```java
public static void imprimeixHolaNom(String nom) { 
System.out.println(“Hola ” + nom);
}
```

Aquesta funció es diu ‘imprimeixHolaNom’, té com a paràmetre d'entrada una dada String anomenat ‘nom’ i no retorna res. Quan la cridem ens imprimirà per pantalla el text “Hola“ seguit del String nom que li’l passarem com a paràmetre.

```java
public static int doble(int a) { 
int resultat = a * 2; 
return resultat;
}
```

Aquesta funció es diu ‘doble’, té com a paràmetre d'entrada una dada int anomenada ‘a’ i retorna una dada de tipus int. Quan la cridem calcularà el doble de ‘a’ i el retornarà (amb el `return`).

```java
public static int multiplica(int a, int b) { 
int resultat = a * b;
return resultat;
}
```

Aquesta funció es diu ‘multiplica’, té dos paràmetres d'entrada de tipus int anomenats ‘a’ i ‘b’ i retorna una dada de tipus int. Quan la cridem calcularà a*b i ho retornarà (amb el return).

```java
public static double maxim(double valor1, double valor2) { 
double max;
if (valor1 > valor2)
  max = valor1;
else
  max = valor2;
return max;
}
```

Aquesta funció es diu ‘maxim, té dos paràmetres d'entrada de tipus double anomenats ‘valor1’ i ‘valor2’ i retorna una dada de tipus double. Quan la cridem calcularà el màxim entre ‘valor1’ i ‘valor2’ i ho retornarà.

```java
public static int sumaVector(int v[]) { 
int suma = 0;
for (int i = 0; i < v.length; i++) 
suma += v[i];
return suma;
}
```

Aquesta funció es diu ‘sumaVector’, té un paràmetre d'entrada tipus int[] (un vector de int) anomenat ‘v’ i retorna una dada tipus int. Quan la cridem recorrerà el vector ‘v’, calcularà la suma de tots els seus elements i la retornarà.

És important saber que les funcions es declaren **dins de ‘class’** però **fora del ‘main’**.

![Declaració de funcions](/uf6/Declaracio_funcio.jpg)

En aquest programa tenim 4 funcions: imprimeixHolaMon, doble, multiplica i main. Sí, el ‘main’ on sempre has programant fins ara és en efecte una funció, però una mica especial: ‘main’ es la funció principal, el punt d’inici d’un programa.

És obligatori que tot programa Java tinga una funció main. Si et fixes, és una funció que rep com a paràmetre un String[] (vector de String) i no retorna res (encara que podria retornar un int). El per què d'això ho veurem més endavant.

Les 3 funcions que hem declarat a dalt del main per si soles no fan res, simplemente estan ací esperant que siguen anomenades (utilitzades), normalment des del propi main.