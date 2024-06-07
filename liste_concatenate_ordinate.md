# Liste concatenate ordinate
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
}
```

```java
public Lista() { 
  this.testa = null;
}
```
```java
public boolean empty(){return testa==null;}
public boolean full(){return false;}
```

```java
public void push(int data){
  Nodo newNode = new Nodo(data); 
  newNode.next=testa; testa=newNode;
}
```
```java
public void append(int data) {
  Nodo newNode = new Nodo(data);
  if (testa == null) {
    testa = newNode;
    } else { 
    Nodo temp = testa; 
    while (temp.next != null) { 
      temp = temp.next;
    } 
    temp.next = newNode;
  }
}
```

```java
```
