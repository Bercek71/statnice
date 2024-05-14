---
Done: true
---
![[Okruhy#^7396e7]]
## Java

Java je objektově orientovaný programovací jazyk, který je známý pro svou přenositelnost, bezpečnost a robustnost. Jeho syntaxe je podobná jazykům jako C++ a C#, ale Java je kompilována do bajtkódu, který je spouštěn na virtuálním stroji Java (JVM). To znamená, že Java aplikace jsou nezávislé na platformě a mohou být spuštěny na různých zařízeních, které podporují JVM.

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, world!");
    }
}
```


## Typový systém

Java používá statický typový systém, což znamená, že typy proměnných jsou ověřovány při kompilaci programu. Typový systém Java obsahuje základní datové typy jako `int`, `double`, `boolean`, atd., a umožňuje také vytvářet uživatelsky definované třídy a rozhraní.

```java
int number = 10;
double pi = 3.14;
boolean isTrue = true;
String text = "Hello";
```

## Virtuální stroj a kompilace

Java aplikace jsou kompilovány do bajtkódu, který je spouštěn na virtuálním stroji Java (JVM). JVM interpretuje bajtkód a provádí ho na cílovém operačním systému. To umožňuje Java aplikacím běžet na různých platformách bez nutnosti přepisování kódu.

```bash
javac HelloWorld.java
java HelloWorld
```

## Tvorba uživatelského rozhraní

Pro tvorbu uživatelského rozhraní v Javě se obvykle používá knihovna Swing nebo JavaFX. Tyto knihovny poskytují sadu komponent pro vytváření interaktivních uživatelských rozhraní, včetně tlačítek, textových polí, seznamů a dalších prvků.
```java
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class Main extends Application {
    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        primaryStage.setTitle("Hello World");
        Button btn = new Button();
        btn.setText("Say 'Hello World'");
        btn.setOnAction(event -> System.out.println("Hello World!"));
        StackPane root = new StackPane();
        root.getChildren().add(btn);
        primaryStage.setScene(new Scene(root, 300, 250));
        primaryStage.show();
    }
}
```

## Delegáty a události

V Javě se události a jejich obsluha obvykle řeší pomocí rozhraní a anonymních tříd. Například pro zachycení události tlačítka se vytvoří anonymní třída implementující rozhraní `ActionListener`, které obsahuje metodu pro zpracování události.

```java
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import javax.swing.JButton;
import javax.swing.JFrame;

public class Main {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Event Example");
        JButton button = new JButton("Click me");

        button.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                System.out.println("Button clicked");
            }
        });

        frame.add(button);
        frame.setSize(300, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }
}
```

## Přístup k databázím

Pro přístup k databázím v Javě se obvykle používá standardní API pro práci s databázemi (JDBC). JDBC umožňuje Java aplikacím vytvářet spojení s databází, provádět SQL dotazy a zpracovávat výsledky.

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

public class Main {
    public static void main(String[] args) {
        try {
            Connection connection = DriverManager.getConnection("jdbc:mysql://localhost:3306/mydatabase", "username", "password");
            Statement statement = connection.createStatement();
            ResultSet resultSet = statement.executeQuery("SELECT * FROM mytable");

            while (resultSet.next()) {
                System.out.println(resultSet.getString("column1") + " " + resultSet.getString("column2"));
            }

            connection.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

## Práce s textovými daty

Pro práci s textovými daty v Javě se obvykle používá třída `java.io.BufferedReader`, která umožňuje číst textová data ze vstupního proudu. Existují také různé třídy pro práci s textem, jako například `java.lang.String` pro práci s textovými řetězci.

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class Main {
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("input.txt"))) {
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## Asynchronní programování

Asynchronní programování v Javě je obvykle řešeno pomocí vláken a rozhraní `java.util.concurrent.Future`. Vlákna umožňují provádět úlohy paralelně a asynchronně, což zlepšuje výkon aplikace a reaktivitu uživatelského rozhraní.

```java
public class Main {
    public static void main(String[] args) {
        Thread thread = new Thread(() -> {
            System.out.println("Hello from thread!");
        });
        thread.start();

        System.out.println("Hello from main thread!");
    }
}
```

## Serializace

Serializace v Javě je proces převádění objektů na bajtový tok, který může být uložen nebo přenesen přes síť. K serializaci objektu v Javě se obvykle používá rozhraní `java.io.Serializable`.

```java
import java.io.*;

class MyClass implements Serializable {
    int number;
    String text;

    public MyClass(int number, String text) {
        this.number = number;
        this.text = text;
    }
}

public class Main {
    public static void main(String[] args) {
        try {
            // Serializace
            ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("data.txt"));
            MyClass obj = new MyClass(42, "Hello");
            out.writeObject(obj);
            out.close();

            // Deserializace
            ObjectInputStream in = new ObjectInputStream(new FileInputStream("data.txt"));
            MyClass newObj = (MyClass) in.readObject();
            System.out.println(newObj.number);
            System.out.println(newObj.text);
            in.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

## Síťová komunikace

Pro síťovou komunikaci v Javě se obvykle používá balíček `java.net`, který obsahuje třídy pro vytváření a správu síťových spojení. Například třída `java.net.Socket` umožňuje vytvořit klienta pro komunikaci se serverem pomocí TCP/IP.

```java
import java.io.*;
import java.net.*;

public class Server {
    public static void main(String[] args) {
        try {
            ServerSocket serverSocket = new ServerSocket(12345);
            System.out.println("Server started.");

            while (true) {
                Socket clientSocket = serverSocket.accept();
                System.out.println("Client connected: " + clientSocket.getInetAddress());

                PrintWriter out = new PrintWriter(clientSocket.getOutputStream(), true);
                out.println("Hello from server!");
                out.close();

                clientSocket.close();
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```
