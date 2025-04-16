# Java Modifier

A GUI application that allows embedding hidden content into `.class` or `.jar` files and optionally signing the modified `.jar` using a digital certificate.

## Project Structure

- SecretViewer.java - A class to read and display the embedded secret.
- GeneratorApp.java - GUI application for embedding secret and .jar signature.

## Features

- Injection of secret data into Java binary files (`.class` or `.jar`)
- Automatic backup creation before modification
- Optional digital signing of `.jar` files with a user-provided certificate and key
- Signature agreement dialog before signing

## Dependencies

- **Java Development Kit:** I used openjdk 21.0.1 2023-10-17
- **jarsigner utility** (included in the standard JDK)
- **JavaFX** (for GUI support)

## Building And Running

1. `javac SecretViewer.java`
2. `javac GeneratorApp.java`
3. `jar cfe SecretViewer.jar SecretViewer SecretViewer.class`: сreating an executable .jar file
4. `java GeneratorApp`: run GeneratorApp to select .class or .jar, embed the secret and sign it (jar only)
5. `jarsigner -verify -verbose SecretViewer.jar`: This signature verification is performed through the console.<br>
   One of the expected output lines: `jar verified`.
6. `java SecretViewer`: run SecretViewer to check the secret output from the .class file
7. `java -jar SecretViewer.jar`: run SecretViewer.jar to check the secret output from the .jar file

## Made by

- Makar Kireenko, Chair of Programming Technologies, Group 12, Year 3
