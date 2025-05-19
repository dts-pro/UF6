# 5. Paràmetres: pas per valor i per referència

Existeixen dos tipus de paràmetres i és important comprendre la diferència.

- **Paràmetres de tipus simple (pas per valor)**: Com int, double, boolean, char, etc. En aquest cas es passen per valor. És a dir, el valor es copia al paràmetre i per tant si es modifica dins de la funció això no afectarà el valor fora d'ella perquè són variables diferents.

```java
public static void main(String[] args) { 
  int a = 10;
  System.out.println("Valor inicial de a: " + a); // a val 10 
  imprimeix_doble(a); // Se li passa el 10 a la funció 
  System.out.println("Valor final de a: " + a); // a continua valent 10
}

// El paràmetre ‘a’ és independent de la ‘a’ del main. Són variables diferents!
public static void imprimeix_doble(int a) {
  // Es copia el valor 10 a aquesta nova ‘a’
  a = 2 * a; // Es duplica el valor de la ‘a’ d'aquesta funció, no afecta fora
  System.out.println("Valor d'en la funció: " + a); // ‘a’ val 20
}
```

Eixida:

```plaintext
Valor inicial de a: 10
Valor de a en la función: 20
Valor final de a: 10
```

- **Paràmetres de tipus objecte (pas per referències)**: Com a objectes de tipus String, els Arrays, etc. En aquest cas no es copia l'objecte sinó que se li passa a la funció una referència a l'objecte original (un punter). Per això des de la funció s'accedeix directament a l'objecte que es troba fora. Els canvis que fem dins de la funció afectaran l'objecte.

```java
// Summa x a tots els elements del vector v
public static void summa_x_a el_vector(int v[], int x) { 
  for (int i = 0; i< v.length; i++)
  v[i] = v[i] + x;
}

public static void main(String[] args) { 
  int v[] = {0, 1, 2, 3};
  System.out.println("Vector abans: " + Arrays.toString(v)); 
  summa_x_a el_vector(v, 10);
  System.out.println("Vector després: " + Arrays.toString(v));
}
```

Eixida:

```plaintext
Vector antes: [0, 1, 2, 3]
Vector después: [10, 11, 12, 13]
```

IMPORTANT: Com un paràmetre de tipus objecte és una referència a l'objecte String o Array que està fora d'ella,sise li assigna un altre objecte es perd la referència i ja no es pot accedir a l'objecte fora de la funció. Encara que Java permet fer-ho, no s'aconsella fer-ho.

```java
// Assignem a x un nou vector, per la qual cosa x deixarà d'apuntar al vector original.
// El vector original no canvia! Simplement ja no podem accedir a ell des de x
// perquè s'ha perdut la referència a aquest objecte.
public static void funcion1(int x[]) {
  x = new int[10]; // x apuntarà a un nou vector, l'original queda intacte
  // el que fem ací amb x no afectarà el vector original
}
// El mateix succeeix en aquest exemple, perdem la referència al String original
public static void funcion2(String x) {
  x = “Hola”; // x apuntarà a un nou String, l'original queda intacte
  // el que fem ací amb x no afectarà el String original
}
```
