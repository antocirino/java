# Coda circolare
```java
private int testa;
private int coda;
private int nelem;
private int max;
private Veicolo[] C;
```
## Costruttore
```java
public CodaCircolare(int dim) {
    max=dim; nelem=0; testa=coda=0; C=new int[max];
}
```
## Append
```java
public void append(int e){
   C[coda]=e;
   coda=(coda+1)%max;
   nelem++;
}
```
## Pop
```java
public int pop(){
  int e = C[testa];
  testa=(testa+1)%max;
  nelem--;
  return e;
}
```
## Predicati
```java 
public boolean isEmpty(){
   return nelem==0;
}
```
```java 
public boolean isFull(){
   return nelem==max;
}
```
## Print
```java
public void printCoda() {
   for(int i=0; i<nelem; i++) {
       System.out.println(C[(testa+i)%max]);
   }
}
```
