# Linked list (lista concatenata) su JAVA

## Nodo
```java
public class Lista { 
    class Nodo {
    
        private int data;  //informazione
        private Nodo next;  //riferimento al prossimo nodo nella lista
    
        Nodo(int elem) {
            data = elem; 
            next=null;
        }
    }
...
...
}
```

Operazioni ammesse sulla lista
## Inizializzazione
```java
Lista(){ 
    testa = null;
}
```
## Predicati
```java
public boolean empty() {
    return testa == null;
}

public boolean full() {
    return false;
}
```


