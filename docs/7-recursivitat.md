# 7. Recursivitat

La recursivitat és la capacitat d'una funció o mètode per a cridar-se a si mateixa. Això permet dividir un problema gran en problemes més xicotets similars i resoldre'ls directament.

## 7.1. La recursivitat requereix sempre:

- **Cas base**: Cas més simple que es pot resoldre directament i permet parar les recursions.
- **Casos recursius**: Cridaes a si mateixa per a reduir el problema en una instància més menuda i simple.

## 7.2. Tipus de recursivitat:

- **Recursivitat directa**: Una funció es crida directament a si mateixa.
- **Recursivitat indirecta**: Una funció crida a una altra que al seu torn crida a la primera. Es produeix un cicle cridaes recursives entre ambdues.
- **Recursivitat lineal**: Cada cridada recursiva es fa sobre un subproblema diferent. Per exemple, en recórrer un arbre binari.
- **Recursivitat en cua**: La cridada recursiva és l'última instrucció de la funció. Això permet optimitzar l'ús de la pila.

## 7.3. Avantatges:

- Simplicitat conceptual i llegibilitat en alguns casos.
- Permet resoldre problemes que es divideixen fàcilment en subproblemes.

## 7.4. Desventajas:

- Major ús de memòria per acumulació de cridaes.
- Risc de desbordament de pila (StackOverflowError).

## 7.5. Recursivitat vs iteració

La recursivitat i la iteració (usant bucles com while o for) són dues formes diferents de resoldre el mateix problema.

### 7.5.1. Exemple: Suma dels números de l'1 al n

**Solució iterativa utilitzant un bucle for:**

```java
public static int suma(int n) {
  int suma = 0;
  for (int i = 1; i <= n; i++) 
    suma += i;

  return suma; 
}
```

**Solución recursiva:**

```java
public static int suma(int n) {
  if (n == 1) {
    return 1;
  } else {
    return n + suma(n-1);
  }
}
```

**Anàlisi de les diferències:**

- La versió iterativa utilitza un bucle i una variable acumuladora (suma) per a anar guardant el resultat parcial.
- La versió recursiva es basa en la descomposició del problema en problemes més xicotets, fins a arribar a un cas base senzill de resoldre (quan n és 1).
- La recursivitat pot ser més elegant i fàcil d'entendre, però consumeix més recursos ja que es van acumulant anomenades en la pila.
- La iteració sol ser més eficient quant a ús de memòria i velocitat d'execució.
