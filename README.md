1. Wireframe dibujado (añadir imagen aquí)

(Captura requerida: foto o dibujo de tu wireframe en papel)
👉 Pon aquí tu foto. Yo describo lo que debes mostrar:

Header con título

Lateral con 5 botones

Zona central con formulario de 2 columnas

Derecha con JTabbedPane

Barra inferior con 3 botones alineados a la derecha

2. Árbol de contenedores (basado en tu .form real)
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
 ├─ EAST: previewPanel (BorderLayout)
 │    └── JTabbedPane
 │          ├── Tab “Resumen” (JTextArea readonly)
 │          └── Tab “Logs” (JList)
 │
 └─ SOUTH: buttonBar (FlowLayout RIGHT)
       ├── JButton Cancelar
       ├── JButton Limpiar
       └── JButton Guardar

3. Capturas necesarias (aún NO insertar, yo solo digo dónde van)
3.1 Vista general de la ventana

👉 Pon aquí screenshot de la ventana principal recién abierta.

3.2 Ventana redimensionada

👉 Screenshot mostrando cómo crece el CENTER y el área de “Notas”.

3.3 Pestaña “Resumen” del JTabbedPane

👉 Screenshot abierta la pestaña Resumen.

3.4 Pestaña “Logs” del JTabbedPane

👉 Screenshot abierta la pestaña Logs.

3.5 Diálogo modal de confirmación

👉 Screenshot del JDialog “¿Guardar cambios?”.

4. Mini tabla de propiedades clave utilizadas
Zona / Componente	Layout	Propiedades clave
Root panel	BorderLayout	Distribuye NORTH/WEST/CENTER/EAST/SOUTH
Header	FlowLayout	alignment = CENTER, gap=5
Navegación	GridLayoutManager (5x1)	Same-size-horizontally, botones iguales
Formulario	GridBagLayout	insets=5, anchor=WEST, fill=HORIZONTAL/BOTH, weightx=1 en inputs, weighty=1 en textarea
Panel derecho	BorderLayout	Preferred width ~260 px, JTabbedPane en CENTER
Botonera	FlowLayout RIGHT	Botones alineados a la derecha
5. Explicación breve (RA1 y RA4)

(Puedes entregar tal cual)

RA1 – Diseño y planificación

BorderLayout en el panel raíz se usa porque permite dividir la interfaz en zonas claras: header, navegación, formulario central, previsualización y botonera.

FlowLayout en el header porque solo contiene un elemento (el título) y permite centrarlo fácilmente.

GridLayout/ GridLayoutManager en la navegación ya que todos los botones deben tener el mismo tamaño y estar apilados verticalmente.

GridBagLayout en el formulario porque es el único layout que permite combinar etiquetas, campos y áreas de texto con alineación precisa en 2 columnas y permitir expansión al redimensionar.

RA4 – Usabilidad y comportamiento

Los weightx y weighty se ajustaron para que los campos de texto se estiren horizontalmente y para que el área de “Notas” crezca verticalmente cuando la ventana aumenta de tamaño.

El panel EAST se mantiene estable gracias a su preferredSize y a que BorderLayout no lo estira más allá de su anchura recomendada.

El JTextArea de “Notas” crece gracias a fill=BOTH y weighty=1 dentro del GridBagLayout.

Durante las pruebas de redimensionado, algunos campos no crecían porque tenían fill=NONE; se solucionó cambiándolos a fill=HORIZONTAL y ajustando los weightx de la columna de los inputs.
