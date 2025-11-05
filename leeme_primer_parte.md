# UIII-act2-3-tablas-mascotas-sofia-granados
    lenguaje: Python.
    Framework: Django.
    Editor: VS code.

    # 1. carpeta del Proyecto: UIII_mascotas_0237
         abrir vs code sobre la carpeta UIII_mascotas_0237
         
    # 2. abrir terminal en vs code
         crear carpeta entorno virtual “.venv” desde terminal de vs code
    # 3. activar el entorno virtual.
    
    # 4. activar intérprete de python.
         instalar Django
         proyecto backend_mascotas sin duplicar carpeta.
         
    # 5. procedimiento para ejecutar servidor en el puerto 8037
         copiar y pegar el link en el navegador.
         
    # 6. crear aplicacion app_mascotas
    
    # 7. Aqui el modelo models.py

         from django.db import models

# MODELO: ANIMALES
La tabla central que es referenciada por Clientes y Empleados

    class Animal(models.Model):
     id_animales = models.AutoField(primary_key=True)
    nombre = models.CharField(max_length=100)
    edad = models.CharField(max_length=20, blank=True, null=True) 
    peso = models.DecimalField(max_digits=6, decimal_places=2)
    cuidados = models.TextField(blank=True, null=True)
    enfermedades = models.TextField(blank=True, null=True)
    especie = models.CharField(max_length=50)
    alimentacion = models.TextField(blank=True, null=True) 
    def __str__(self):
        return f"{self.nombre} ({self.especie}) - ID: {self.id_animales}"

# ==========================================
# MODELO: CLIENTES
# Relacion 1 a muchos: Un Cliente puede tener muchos Animales.

    class Cliente(models.Model):
    # Clave primaria
    id_cliente = models.AutoField(primary_key=True)
     apepaterno = models.CharField(max_length=100)
    apematerno = models.CharField(max_length=100)
    nombre = models.CharField(max_length=100)
    domicilio = models.CharField(max_length=255, blank=True, null=True)
    correo = models.CharField(max_length=100, unique=True)
    telefono = models.CharField(max_length=20)
    alergias = models.TextField(blank=True, null=True)    
    def __str__(self):
        return f"{self.nombre} {self.apepaterno}"
    Animal.add_to_class('dueno', models.ForeignKey(
    Cliente, 
    on_delete=models.CASCADE, 
    related_name="animales_poseidos",
    blank=True, 
    null=True))

# ==========================================
# MODELO: EMPLEADOS # 
# ========================================== 
Relación Muchos a Muchos: Un Empleado atiende muchos Animales,  y un Animal puede ser atendido por muchos Empleados. 
# ========================================== 
    class Empleado(models.Model):
    # Clave primaria id_empleado = models.AutoField(primary_key=True) 
      Atributos personales apepaterno = models.CharField(max_length=100) 
      apematerno = models.CharField(max_length=100) 
      nombre = models.CharField(max_length=100)
      telefono = models.CharField(max_length=20)
      domicilio = models.TextField(blank=True, null=True) 
      ocupacion = models.CharField(max_length=100) 
      alergias = models.TextField(blank=True, null=True) 
      animales_a_cargo = models.ManyToManyField( 'Animal', related_name="empleados_responsables", blank=True ) 
      def __str__(self): return f"Empleado: {self.nombre} {self.apepaterno} ({self.ocupacion})"



# 8.  Procedimiento para realizar las migraciones(makemigrations y migrate.
 
# 9.  primero trabajamos con el MODELO: animales
    En view de app_mascotas crear las funciones con sus códigos correspondientes (inicio_mascotas, agregar_mascota,
    actualizar_mascota, realizar_actualizacion_mascota, borrar_mascota)

# 10.  Crear la carpeta “templates” dentro de “app_mascotas”.
            En la carpeta templates crear los archivos html (base.html,
            header.html, navbar.html, footer.html, inicio.html).
 
# 11. En el archivo base.html agregar bootstrap para css y js.
 
 # 12. En el archivo navbar.html incluir las opciones ( “Sistema de Administración mascotas”, “Inicio”, “mascotas”,en submenu de
           mascotas(Aregar mascotas,ver mascotas, actualizar mascotas, borrar mascota), “clientes” en submenú de clientes(Agregar clientes,ver
           clientes, actualizar clientes, borrar clientes) “empleados” en sub menu de empleados(Agregar empleados,ver empleados,
           actualizar empleados, borrar empleados), incluir iconos a las opciones principales, no en los submenús.
 
 # 14. En el archivo footer.html incluir derechos de autor,fecha del sistema y “Creado por Sofia Granados Sanchez, Cbtis 128” y mantenerla fija al final de la página.
           En el archivo inicio.html se usa para colocar información del sistema más una imagen tomada desde la red sobre cinepolis.
 
 # 15. Crear la subcarpeta carpeta mascotas dentro de app_mascotas\templates.
           crear los archivos html con su codigo correspondientes de (agregar_mascotas.html, ver_mascotas.html mostrar en tabla con
           los botones ver, editar y borrar, actualizar_mascotas.html, borrar_mascotas.html) dentro de app_mascotas\templates\mascotas.
 
# 16.  No utilizar forms.py.
 
 # 17.  procedimiento para crear el archivo urls.py en app_mascotas con el código correspondiente para acceder a las funciones de views.py
            para operaciones de crud en mascotas.
            procedimiento para agregar app_mascotas en settings.py de backend_mascotas
           realizar las configuraciones correspondiente a urls.py de backend_mascotas para enlazar con app_mascotas
 
# 18. procedimiento para registrar los modelos en admin.py y volver a realizar las migraciones.
 
# 19. por lo pronto solo trabajar con “mascotas” dejar pendiente # MODELO: clientes y # MODELO: empleados
 
# 20. Utilizar colores suaves, atractivos y modernos, el código de las páginas web sencillas.
 
 # 21. No validar entrada de datos.
     
# 22. Al inicio crear la estructura completa de carpetas y archivos.

# 23. proyecto totalmente funcional.
 
# 24. finalmente ejecutar servidor en el puerto puerto 8037.
