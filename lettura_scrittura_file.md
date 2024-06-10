## Lettura
Per la lettura da file utilizziamo lo scanner:
```java
String nomeFile;
try {
    Scanner input = new Scanner(Paths.get(nomeFile));
    String nome = scanner.next();
} catch (NoSuchFileException e) {
    System.out.println("File non esistente: " + e.getMessage());
}
```

## Scrittura
Per la scrittura utilizziamo la redirezione dello stream
```java
// Definiamo il nome del file
String fileName = "output.txt";

try {
    // Creiamo un nuovo PrintStream per il file
    PrintStream fileStream = new PrintStream(new FileOutputStream(fileName));
    
    // Salviamo l'attuale System.out in modo da poterlo ripristinare successivamente
    PrintStream consoleStream = System.out;
    
    // Reindirizziamo l'output di System.out su fileStream
    System.setOut(fileStream);
    
    // Ora tutto ciò che viene stampato su System.out verrà scritto direttamente sul file
    
    // Esempio di scrittura
    System.out.println("Questo è un esempio di scrittura su file utilizzando System.out.");
    
    // Ripristiniamo l'output di System.out sulla console
    System.setOut(consoleStream);
    
    System.out.println("Scrittura completata con successo!");
} catch (IOException e) {
    // Gestione delle eccezioni in caso di errori di I/O
    System.out.println("Si è verificato un errore durante la scrittura nel file: " + e.getMessage());
}
```
