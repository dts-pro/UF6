# 3. Cridar una funció

Les funcions poden ser invocades o cridades des de qualsevol altra funció, inclosa ella mateixa. Sí, una funció pot cridar a qualsevol altra funció, i una funció pot cridar-se a si mateixa.

De totes maneres, ara com ara cridarem funcions només des de la funció principal ‘main'. Així és més senzill d'aprendre al principi.

Quan s'invoca una funció el flux d'execució salta a la funció (passant-li els paràmetres, en cas d'haver), s'executen les instruccions de la funció i finalment torna al punt que va cridar a la funció per a continuar executant-se.
Les funcions s'invoquen amb el seu nom, passant la llista de paràmetres entre
parèntesis. Si no té paràmetres han de posar-se els parèntesis igualment. Si la funció retorna un valor, per a recollir-lo cal assignar-lo a una variable o utilitzar-lo d'alguna manera (poden combinar-se funcions en expressions i fins i tot passar-ho a altres funcions).

Exemple utilitzant les funcions de l'apartat anterior:

::: tabs
== Java

```java
public static void main(String[] args) {
  // No té paràmetres ni retorna valor. Simplemente imprimeix "Hola Mon"
  imprimeixHolaMon();
  // És habitual cridar a una funció i guardar el valor retornat en una variable
  int a = doble(10); // a = 20 (10*2)
  int b = multiplica(3, 5); // b = 15 (3*5)
  // Poden passar-se variables com a paràmetres
  int c = doble(a); // c = 40 (20*2)
  int d = multiplica(a, b); // d = 300 (20*15)
  // Poden combinar-se funcions i expressions
  int e = doble(4) + multiplica(2,10); // e = 8 + 20
  System.out.println("El doble de 35 és " + doble(35) ); // "El doble de 35 és 70"
  System.out.println("12 per 12 és " + multiplica(12,12) ); // "12 per 12 és 144"
}
```

:::

>***Exemple: Programa amb una funció que suma dos números.***
>
>![Exemple funció suma](/uf6/exemple_suma.jpg)

>***Exemple: Programa amb una funció que determina si un número és parell o imparell.***
>
>![Exemple funció par](/uf6/exemple_par.jpg)
