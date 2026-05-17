
# Basics of JavaFX & Event-Driven Programming

### Basic Structure of a JavaFX Program

- A JavaFX program extends `Application`.
    
- You override the `start(Stage primaryStage)` method.
    
- You create a `Scene` and add UI elements (nodes) to it.
    
- Show the `Stage` (main window).


```java
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.stage.Stage;

public class SimpleJavaFX extends Application {
    @Override
    public void start(Stage stage) {
        Button btn = new Button("Click me");
        Scene scene = new Scene(btn, 200, 100);
        stage.setScene(scene);
        stage.setTitle("My JavaFX App");
        stage.show();
    }
    public static void main(String[] args) {
        launch(args);
    }
}

```

### What are Panes?

- **Panes** are special containers used to organize and arrange UI controls (buttons, labels, text fields, etc.) in a JavaFX application.
    
- They help you decide **how elements are placed and sized** on the screen.
    
- Think of panes as "layouts" or "boxes" that hold your controls and arrange them in a certain way.
    

---

### Common Types of Panes:

|Pane Type|Description|Example Use|
|---|---|---|
|**HBox**|Arranges children horizontally in a row.|Place buttons side by side.|
|**VBox**|Arranges children vertically in a column.|Stack labels or inputs vertically.|
|**StackPane**|Places children on top of each other (stack).|Overlay text on an image.|
|**BorderPane**|Divides the area into top, bottom, left, right, and center regions.|Create complex UI with header, footer, sidebar, etc.|
|**GridPane**|Arranges children in a flexible grid of rows and columns.|Create forms with labels and inputs aligned.|
## UI Controls in JavaFX

**UI Controls** are the interactive elements you see in an application, like buttons, text fields, checkboxes, etc. These allow users to interact with your program.

### Common UI Controls:

- **Button:** Clickable button.
    
- **Label:** Displays text.
    
- **TextField:** Single-line input box.
    
- **TextArea:** Multi-line input box.
    
- **CheckBox:** A box that can be checked or unchecked.
    
- **RadioButton:** Choose one option from a group.
    
- **ComboBox:** Drop-down list to select one item.
    
- **ListView:** Displays a list of items.



## Shapes in JavaFX

**Shapes** are graphical elements used to draw simple graphics like circles, rectangles, lines, etc.

### Common Shapes:

- **Circle**
    
- **Rectangle**
    
- **Line**
    
- **Ellipse**
    
- **Polygon**


```java
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Circle;
import javafx.scene.shape.Rectangle;
import javafx.stage.Stage;

public class ShapesExample extends Application {
    @Override
    public void start(Stage stage) {
        Circle circle = new Circle(100, 100, 50); // centerX, centerY, radius
        circle.setFill(Color.BLUE);               // fill color

        Rectangle rect = new Rectangle(50, 200, 150, 100); // x, y, width, height
        rect.setFill(Color.RED);

        Pane pane = new Pane(circle, rect);
        Scene scene = new Scene(pane, 300, 350);

        stage.setScene(scene);
        stage.setTitle("Shapes Example");
        stage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}

```

## What is Property Binding?

- **Property Binding** connects two properties so that when one property changes, the other updates automatically.
    
- It’s like linking UI components or variables together so you don’t have to manually update them.
    
- Makes your UI reactive and easier to maintain
## Other types of bindings:

- **One-way binding:** One property depends on another (like above).
    
- **Bidirectional binding:** Both properties update each other.
    
- **Binding with expressions:** Bind a property to a calculated expression (e.g., sum, concatenate).
## Color Class

- The **Color** class in JavaFX is used to set colors for UI elements like shapes, text, backgrounds, etc.
    
- It supports many ways to define colors: predefined constants, RGB values, hex codes, opacity, etc.
    

### Common ways to create a Color:

- Using predefined constants like `Color.RED`, `Color.BLUE`, etc.
    
- Using RGB values: `Color.rgb(red, green, blue)`
    
- Using hex string: `Color.web("#FF5733")`
    
- With opacity: `Color.color(red, green, blue, opacity)`
## Font Class

- The **Font** class is used to specify the font style, size, and family for text in JavaFX.
    
- You can choose font family (like Arial, Times New Roman), size, weight (bold), and posture (italic).
    

---

### Common ways to create Font:

- `Font.font("Arial", 20)` — font family Arial, size 20
    
- `Font.font("Arial", FontWeight.BOLD, 20)` — bold Arial size 20
    
- `Font.font("Times New Roman", FontPosture.ITALIC, 18)` — italic Times New Roman size 18

## Image Class

- The **Image** class is used to load and represent images (like PNG, JPEG) in JavaFX.
    
- You can load images from files, URLs, or resources inside your project.
    
- It holds the image data but doesn’t display it directly.
    

---

## ImageView Class

- The **ImageView** class is a Node (UI component) that displays an Image on the screen.
    
- You can control the size, position, and effects of the image via ImageView.
    
- It is like a container for showing an Image.
    

---

## How to use Image and ImageView together?

1. Load an image using **Image**.
    
2. Show it by putting that Image inside an **ImageView**.
    
3. Add the ImageView to your scene graph.

## Events in JavaFX

- **Events** are actions or occurrences that happen in the system you can respond to.
    
- Common events include user actions like clicking a button, moving the mouse, typing on the keyboard, or window resizing.
    
- JavaFX uses an event-driven programming model, meaning the program reacts to events when they occur.
    

---

## Event Sources

- An **Event Source** is the UI element (or object) that generates an event.
    
- For example, when you click a Button, the Button is the event source.
    
- Other sources can be a TextField, a Scene, or even the Stage (window).
    

---

## How Events Work in JavaFX?

1. The user interacts with an event source (e.g., clicks a button).
    
2. The event source generates an **event**.
    
3. The event is handled by an **event handler** — a method you write to respond to that event.
### Events kya re miya?

Event ka matlab samajh — jaise tu biryani khaate khaate **button dabaya**, toh woh bolta **“Arey miya, dab gaya main!”** 😲

Toh koi bhi harkat jo user karta — mouse hilana, key dabana, screen ko chhuna — **sabko bolte event re bhai!**

---

### 💥 Event Source kaun miya?

Event source matlab **jahan se hungama shuru hota**. Jaise agar **button pe click** kiya toh button hi **event ka baap re!**  
Usi ne chillaya “Oye miya, kuch ho gaya!”


### Registering Handlers — Matlab kya re miya?

**Handler** matlab **ek banda (function)** jo **wait kar raha** hai ke kab koi **event ho** jaaye, phir woh **kaam pe lag jaata**.  
Jaise koi dost bola: **"Miya jab biryani aayegi, mujhe bula dena!"** — yeh registration hua!

➡️ Tu button ko bolta:

> "Abe sun, jab tujhe dabaye koi, toh yeh kaam kar dena!"

**Registering handler** = bata raha hoon ki event hone pe kya kaam karein.  
**Handling event** = wohi kaam karna jab event sach mein ho jaaye.



### 1. **Labeled and Label**

- **Label** is a UI element that just shows some text or image.
    
- It’s not clickable, just displays information.
    

Example:

java

CopyEdit

`Label label = new Label("Hello, JavaFX!");`

---

### 2. **Button**

- A clickable UI element that performs an action when pressed.
    

Example:

java

CopyEdit

`Button button = new Button("Click Me"); button.setOnAction(e -> System.out.println("Button clicked!"));`

---

### 3. **Checkbox**

- A box you can check or uncheck.
    
- Useful for multiple selections.
    

Example:

java

CopyEdit

`CheckBox cb = new CheckBox("Subscribe"); cb.setSelected(true); // checked by default`

---

### 4. **RadioButton**

- A small round button.
    
- Used for selecting only one option among a group.
    
- RadioButtons are grouped using a **ToggleGroup**.
    

Example:

java

CopyEdit

`RadioButton rb1 = new RadioButton("Male"); RadioButton rb2 = new RadioButton("Female"); ToggleGroup group = new ToggleGroup(); rb1.setToggleGroup(group); rb2.setToggleGroup(group);`

---

### 5. **TextField**

- A single-line input box where user types text.
    

Example:

java

CopyEdit

`TextField tf = new TextField(); tf.setPromptText("Enter your name");`

---

### 6. **TextArea**

- A multi-line text input box.
    

Example:

java

CopyEdit

`TextArea ta = new TextArea(); ta.setPromptText("Write your message here...");`

---

### 7. **ComboBox**

- A dropdown list for selecting one item.
    

Example:

java

CopyEdit

`ComboBox<String> combo = new ComboBox<>(); combo.getItems().addAll("Apple", "Banana", "Orange"); combo.setValue("Apple");  // default selected`

---

### 8. **ListView**

- Shows a scrollable list of items.
    
- User can select one or more items.
    

Example:

java

CopyEdit

`ListView<String> listView = new ListView<>(); listView.getItems().addAll("Red", "Green", "Blue");`

---

### 9. **Scrollbar**

- A control to scroll through content vertically or horizontally.
    

Example:

java

CopyEdit

`Scrollbar scrollbar = new Scrollbar(); scrollbar.setOrientation(Orientation.VERTICAL); scrollbar.setMin(0); scrollbar.setMax(100);`

---

### 10. **Slider**

- Lets user select a numeric value by sliding a knob.
    

Example:

java

CopyEdit

`Slider slider = new Slider(0, 100, 50); // min=0, max=100, initial=50`

---

### 11. **Video and Audio**

- JavaFX supports multimedia with **Media** and **MediaPlayer** classes.
    
- You can play video or audio files inside your app.
    

Example (Playing audio):

java

CopyEdit

`Media sound = new Media("file:///C:/music/song.mp3"); MediaPlayer mediaPlayer = new MediaPlayer(sound); mediaPlayer.play();`

Example (Playing video):

java

CopyEdit

`Media video = new Media("file:///C:/videos/movie.mp4"); MediaPlayer mediaPlayer = new MediaPlayer(video); MediaView mediaView = new MediaView(mediaPlayer);`