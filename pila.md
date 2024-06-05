# Pila
## Attributi
```java
private int testa;
private int max;
private int P[];
```
## Costruttore
```java
public Pila(int dim){
   max=dim; 
   testa=0; 
   P=new int[max];
}
```
## Push
```java
public void push(int e){
   P[testa]=e;
   testa++;
}
```
## Pop
```java
public int pop(){
   testa--;
   int e = P[testa];
   return e;
}
```
## Top
```java
public int top(){
   return P[testa-1];
}
```
```java
public boolean isEmpty(){
   return testa==0;
}
```
## Predicato
```java
public boolean isFull(){
   return testa==max;
}
```
## Print
```java
public void printPila(){
   for(int i=testa-1; i>=0; i--) 
     System.out.print(P[i]); 
}
```
