## Lettura
Per la lettura da file utilizziamo lo scanner:
```java
```

## Scrittura
Per la scrittura utilizziamo la redirezione dello stream
```java
// Nome del file su cui scrivere l'output
String nomeFile = "output.txt";

// Crea un nuovo PrintStream che scrive su un file
PrintStream fileOutput = new PrintStream(new FileOutputStream(nomeFile));

// Utilizza Scanner per leggere input dall'utente
Scanner scanner = new Scanner(System.in);
System.out.println("Inserisci delle righe di testo (digita 'fine' per terminare):");

// Redirigi System.out sul nuovo PrintStream
System.setOut(fileOutput);
// Leggi input dall'utente e scrivi su System.out (ovvero sul file)
String linea;
while (!(linea = scanner.nextLine()).equalsIgnoreCase("fine")) {
    System.out.println(linea); // Stampa su file tramite System.out
}

// Chiudi lo scanner e il PrintStream
scanner.close();
fileOutput.close();
```
