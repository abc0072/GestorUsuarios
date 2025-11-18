Wireframe dibujado


(Captura requerida: foto o dibujo de tu wireframe en papel)
👉 Pon aquí tu foto. Yo describo lo que debes mostrar:


































Árbol de contenedores
JFrame (BorderLayout)
 ├─ NORTH: headerPanel (FlowLayout)
 │    └── JLabel “Gestor de Usuarios”
 │
 ├─ WEST: navPanel (GridLayoutManager 5x1)
 │    ├── JButton Dashboard
 │    ├── JButton Usuarios
 │    ├── JButton Informes
 │    ├── JButton Ajustes
 │    └── JButton Ayuda
 │
 ├─ CENTER: formPanel (GridBagLayout)
 │    ├── JLabel + JTextField (Nombre)
 │    ├── JLabel + JTextField (Email)
 │    ├── JLabel + JComboBox (Rol)
 │    ├── JLabel + JCheckBox (Activo)
 │    └── JLabel + JScrollPane + JTextArea (Notas)
 │
 │
 │
 ├─ EAST: previewPanel (BorderLayout)
 │    └── JTabbedPane
 │          ├── Tab “Resumen” (JTextArea readonly)
 │          └── Tab “Logs” (JList)
 │
 └─ SOUTH: buttonBar (FlowLayout RIGHT)
       ├── JButton Cancelar
       ├── JButton Limpiar
       └── JButton Guardar
























Capturas necesarias
Vista general de la ventana

Imagen 1












































Ventana redimensionada

Imagen 2




Pestaña “Resumen” del JTabbedPane

Imagen 3
Pestaña “Logs” del JTabbedPane

Imagen 4






Diálogo modal de confirmación

Imagen 5


Mini tabla con las propiedades clave usadas


Zona/Componente
Layout
Propiedades clave
Root panel
BorderLayout
Distribuye NORTH/WEST/CENTER/EAST/SOUTH
Header
FlowLayout
alignment = CENTER, gap=5
Navegación
GridLayoutManager (5x1)
Same-size-horizontally, botones iguales
Formulario
GridBagLayout
insets=5, anchor=WEST, fill=HORIZONTAL/BOTH, weightx=1 en inputs, weighty=1 en textarea
Panel derecho
BorderLayout
Preferred width ~260 px, JTabbedPane en CENTER
Botonera
FlowLayout RIGHT
Botones alineados a la derecha




