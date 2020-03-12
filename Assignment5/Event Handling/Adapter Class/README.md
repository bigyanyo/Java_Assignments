> Question 3

# Adapter Class
	
- Java adapter classes provide the default implementation of listener interfaces.

- If you inherit the adapter class, you will not be forced to provide the implementation of all the methods of listener interfaces. So it saves code.

- The adapter classes are found in java.awt.event, java.awt.dnd and javax.swing.event packages.

---

>java.awt.event Adapter Classes

|Adapter class | Listener interface |
---------------|---------------------
|WindowAdapter	|WindowListener|
|KeyAdapter	|KeyListener|
|MouseAdapter	|MouseListener|
|MouseMotionAdapter|	MouseMotionListener|
|FocusAdapter	|FocusListener|
|ContainerAdapter	|ContainerListener|
|HierarchyBoundsAdapter	|HierarchyBoundsListener|

>javax.swing.event Adapter classes

|Adapter class | Listener interface |
---------------|---------------------
|MouseInputAdapter	|MouseInputListener|
|InternalFrameAdapter	|InternalFrameListener|

>java.awt.dnd Adapter classes

|Adapter class | Listener interface |
---------------|---------------------
|DragSourceAdapter	|DragSourceListener|
|DragTargetAdapter	|DragTargetListener|
