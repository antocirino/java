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
    Nodo testa;
...
}
```

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
## Push
Azione: inserimento in testa

Precondizione: la lista non è piena nè ordinata
```java
private void push(int e) {
    Nodo q = new Nodo(e);
    q.next = testa;
    testa = q;
}
```
Cosa fa:
1. creiamo un oggetto nodo con un certo contenuto informativo e con puntatore a null

2a. se la lista è vuota la testa punta a null. Per assegnazione faccio puntare la testa al nuovo ogg.

2b. se la lista non è vuota, il next del nuovo nodo verrà fatto puntare al primo elemento, e la testa verrà fatta puntare alla testa del nuovo nodo (IN QUESTO ORDINE)

## Append
Azione: inserimento in coda

Precondizione: la lista non è piena
```java
public void append(int e) {
    if(empty()) push(e);
    else {
       Nodo temp = testa;
       Nodo q= new Nodo(e);
       while(temp.next!=null) temp = temp.next;
       temp.next = q;
    }   
}
```
## Inserisci
Azione:

Precondizione: la lista è ordinata in senso crescente
```java
 public void inserisci(int e) {
   // se la lista è vuota eseguo il push
   if(empty() || testa.data>=e) push(e);
       else {
         Nodo temp = testa;
         Nodo q = new Nodo(e);
         while(temp.next!=null && temp.next.data<e)
             temp = temp.next;
         q.next = temp.next;
         temp.next = q;
   }
 }
```
## Pop
Azione: preleva elemento in testa e aggiorna puntatore testa

Precondizione: la lista non è vuota
```java
public int pop() {
    int e = testa.data;
    testa = testa.next;
    return e;
}
```
## Top
Azione: preleva elemento in testa (non aggiorna puntatore!!)

Precondizione: la lista non è vuota

```java
public int top() {
    int e = testa.data;
    return e;
}
```
## Pop back
Azione:

Precondizione: la lista non è vuota
```java
public int pop_back() {
    if(testa.next==null) return pop();
    else {
        Nodo temp = testa;
        while(temp.next.next!=null)  temp = temp.next;
        int e = temp.next.data;
        temp.next=null;
        return e;
    } 
}
```

## Top back
Azione: 

Precondizione: la lista non è vuota
```java
public int top_back() {
    if(testa.next==null) return top();
    else {
        Nodo temp = testa;
        while(temp.next.next!=null)  temp = temp.next;
        int e = temp.next.data;
        return e;
    } 
}
```

## Elimina
Azione: viene eliminata la prima occorrenza dell'elemento

Precondizione: la lista non è vuota e l'elemento è presente
```java
public void elimina(int e){
    if(testa.data == e) pop();
    else {
        Nodo temp = testa;
        while(temp.next.data!=e) temp = temp.next;
        temp.next = temp.next.next;
    }
}
```

## inLista
Azione: restituisce true o false se l'elemento è in lista o meno
```java
public boolean inLista(int e) {
    boolean trovato = false;
    Nodo temp = testa;
    while(temp!=null && !trovato)
        if(temp.data==e)
            trovato = true;
        else temp = temp.next;
    return trovato;
}
```

## isOrdered
Azione: restituisce true o false se la lista è ordinata o meno
```java
public boolean isOrdered () {
    boolean ordinato = true;
    Nodo temp = testa;
    
    if (temp == null) return true;
    
    if (temp.next == null) return true;
    
    if (temp.next.next == null) {
        return temp.data<=temp.next.data;
    }
    
    // una lista vuota o con un solo elemento è ordinata
    
    while (ordinato && temp.next.next!=null) {
        if (temp.data>temp.next.data) {
            ordinato = false;
        } else {
            temp = temp.next;
        }
    }
    return ordinato;
}
```

## Stampa
Azione: stampa la lista

Precondizione: la listan non è vuota
```java
public void stampa(){
    Nodo temp = testa;
    while(temp!=null) {
         System.out.println(temp.data);
         temp = temp.next;
    }
}
```
