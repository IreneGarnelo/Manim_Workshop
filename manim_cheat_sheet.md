# Manim Cheat Sheet

---
## **1) Objekte (Mobjects)**

### **1.1) Objekte definieren**
![Mobjects](images/mobjects.png)

| Objekt | Beispielhafte Definition |
|---|---|
| **Dot** | `Dot(point=LEFT*3, radius=0.08, color=RED)` |
| **Line** | `Line(p1, p2, color=YELLOW)` *(p1, p2 sind Dots)* |
| **Circle** | `Circle(radius=0.6, color=GREEN)` |
| **Arc** | `Arc(radius=0.6, start_angle=0, angle=PI/2, color=BLUE)` |
| **Ellipse** | `Ellipse(width=1.2, height=0.6, color=ORANGE)` |
| **Triangle** | `Triangle(radius=0.6, color=YELLOW)` |
| **Square** | `Square(side_length=0.8, color=PINK)` |
| **Rectangle** | `Rectangle(width=1.4, height=0.8, color=MAROON)` |
| **RegularPolygon** | `RegularPolygon(n=5, radius=0.5, color=TEAL)` |
| **Vgroup** | `VGroup(Square(side_length=0.8), Square(side_length=0.8).rotate(PI/4))` |
| **Axes** | `Axes(x_range=[0,5,1], y_range=[0,4,1], x_length=4, y_length=3)` |
| **Matrix** | `Matrix([[1,2],[3,4]], left_bracket="(", right_bracket=")")` |
| **Text** | `Text("Text", font_size=28, color=WHITE)` |
| **Tex** | `Tex(r"$\\int_0^1 x^2 \\, dx = \\frac{1}{3}$", font_size=36, color=BLUE)` |

---
### **1.2) Positionierung eines Objekts `obj`**

#### A) Absolute / relative Position
| Befehl | Bedeutung |
|---|---|
| `obj.move_to([1,2,0])` | Mittelpunkt auf Koordinate setzen |
| `obj.shift(LEFT*2 + UP)` | Relative Verschiebung |
| `obj.set_x(3)` | Nur x-Koordinate ändern |
| `obj.set_y(1)` | Nur y-Koordinate ändern |

#### B) Relativ zu anderen Objekten / zum Frame
| Befehl | Bedeutung |
|---|---|
| `obj.next_to(other_obj, RIGHT, buff=0.3)` | Neben anderes Objekt setzen |
| `obj.to_edge(UP)` | An oberen Rand schieben |
| `obj.to_corner(UR)` | In obere rechte Ecke (Upper Right) schieben |

---
### **1.3) Eigenschaften von `obj` nach der Definition ändern**

| Befehl | Bedeutung |
|---|---|
| `obj.set_color(RED)` | Ändert die Linien-/Textfarbe |
| `obj.set_fill(BLUE, opacity=0.5)` | Füllt das Objekt mit Farbe (inkl. Transparenz) |
| `obj.scale(2)` | Skaliert das Objekt um Faktor 2 |
| `obj.rotate(PI)` | Dreht das Objekt um π |

---
### **1.4) Arbeiten mit Axes (Koordinatensystem)**

| Befehl | Bedeutung |
|---|---|
| `graph = axes.plot(f, color=BLUE)` | Funktion zeichnen |
| `label = axes.get_graph_label(graph, label="x^2")` | Beschriftung erzeugen |
| `p1 = Dot(axes.c2p(x1, y1), color=RED)` | Punkt bei Koordinate setzen, c2p = coordinate to point |

---

&nbsp;

&nbsp;

&nbsp;

## **2) Objekte visualisieren**

### **2.1) Objekte hinzufügen / entfernen**

| Befehl | Bedeutung |
|---|---|
| `self.play(...)` | Mit Animation zeigen/ändern |
| `self.add(obj)` | Sofort sichtbar einfügen |
| `self.remove(obj)` | Sofort entfernen |
| `self.wait(1)` | 1 Sekunde Pause |

---
### **2.2) Einige Animationen**

#### Ein-/Ausblenden
| Animation | Effekt |
|---|---|
| `Create(obj)` | Objekt zeichnen |
| `Write(obj)` | Handschrift-Effekt (Text/Tex) |
| `FadeIn(obj)` | Sanft einblenden |
| `FadeOut(obj)` | Sanft ausblenden |
| `Uncreate(obj)` | Umkehrung von `Create` |

#### Bewegung
| Animation | Effekt |
|---|---|
| `obj.animate.move_to(RIGHT)` | Zielbewegung |
| `obj.animate.shift(UP)` | Relative Bewegung |

#### Transformation
| Animation | Effekt |
|---|---|
| `Transform(obj1, obj2)` | Formübergang |

#### Größe & Rotation
| Animation | Effekt |
|---|---|
| `obj.animate.scale(2)` | Vergrößern/Verkleinern |
| `obj.animate.rotate(PI)` | Drehung um π |


