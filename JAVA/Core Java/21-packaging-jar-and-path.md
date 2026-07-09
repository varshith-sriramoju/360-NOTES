## Packaging Models

In Java, there are three packaging models:

1. JAR
2. WAR
3. EAR

### 1. JAR (Java Archive)

- For core Java applications, we use JAR.
- A JAR file ends with the `.jar` extension.
- A JAR file contains `.class` files.

### 2. WAR (Web Archive)

- For web applications, we use WAR.
- A WAR file ends with the `.war` extension.
- A WAR file contains `.html`, `.jsp`, `.js`, `.css`, `.jpg`, `.class`, and `.jar` files.

### 3. EAR (Enterprise Archive)

- For enterprise web applications, we use EAR.
- An EAR file ends with the `.ear` extension.
- An EAR file contains several `.war` files.

### Packaging Summary

```text
project (application)
|- multiple classes -> package into single file -> packing models (jar, war, ear)
```

- JAR is a tool (development tool) and it is used to create JAR, WAR, and EAR files.
- In Java, archive means JAR file, WAR file, or EAR file.

## Creating a JAR File

```bash
jar -cvf some-name.jar *.class
```

- `-c` creates a new archive (JAR file).
- `-v` generates verbose output on the console.
- `-f` specifies the archive file name.

### To See the Contents of a JAR File

```bash
jar -tvf some-name.jar
```

- `-t` lists the table of contents of the archive.

### Extracting the Contents of a JAR File

```bash
jar -xvf some-name.jar
```

- `-x` extracts files from the archive.

### Notes

1. A JAR file is also a logical directory location.
2. If the `.class` file is available inside the JAR file, we should set the classpath to the JAR file.

### Example Structure

```text
c:
|- temp
   |- app1.jar (Game.class)

d:
|- work
   |- Test.java (Test class is using Game class)
```

## Path

- Path means location.
- There are two kinds of path:

1. Relative path
2. Absolute path

### Relative Path Example

```text
d:
|- work
   |- abc.txt
   |- Test.java --> abc.txt (relative path)
```

### Absolute Path Example

```text
c:
|- temp
   |- abc.txt

d:
|- work
   |- Test.java

Test.java --> c:\temp\abc.txt (absolute path)

```
