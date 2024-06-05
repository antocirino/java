## Ricerca elemento minimo
```java
public int ricercaMinimoVettore() {
    int min = vettore[0];
    for (int i = 0; i<riemp; i++) {
        if (min>vettore[i]) {
            min = vettore[i];
        }
    }
    return min;
}
```
## Ricerca elemento massimo
```java
public int ricercaMassimoVettore () {
    int max = vettore[0];
    for (int i = 0; i<riemp; i++) {
        if (max<vettore[i]) {
            max = vettore[i];
        }
    }
    return max;
}
```
## Eliminazione elemento
```java
public int rimuoviElementoVettore(int posizione) {
    if(posizione>=0 && posizione<riemp){
            //possibile eliminare
            for(int i=posizione; i<riemp-1; i++) {
                    vettore[i]=vettore[i+1];
            }
            riemp--;
            return 0;
    } else {
            return -1;
    }
}
```
## Ricerca elemento
```java
public boolean ricercaLineareVettore(int elem){
    bool trovato = false;
    posizione=0;
    while (!trovato && posizione<riemp) {
            if(vettore[posizione]==elem) {
                    trovato=true;
            } else {
                    posizione++;
            }
    }
    return trovato;
}
```
## Ordinamento vettore
```java
```
