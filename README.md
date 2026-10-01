# TiendaPro

Sistema de punto de venta (POS) para tiendas pequeñas, hecho en Python, CustomTkinter y SQLite. Permite gestionar ventas, inventario, compras de mercadería y ganancias por producto, con permisos según el rol de cada usuario.

## Instalación

Se requiere Python 3.10 o superior.

```bash
git clone https://github.com/<tu-usuario>/tiendapro.git
cd tiendapro
pip install -r requirements.txt
python TiendaPro.py
```

En Windows, puedes hacer doble clic en `ABRIR.bat` para instalar las dependencias, crear el acceso directo en el escritorio y abrir la aplicación. Para recrear el acceso directo, ejecuta `CREAR_ACCESO_DIRECTO.bat`.

## Usuarios por defecto

| Usuario | Contraseña | Rol |
| --- | --- | --- |
| `admin` | `admin123` | Admin General |
| `duena` | `duena123` | Dueña |
| `trabajador` | `trabaja123` | Trabajador |

**Cambia estas contraseñas en Configuración → Cambiar Contraseña antes de usar el sistema en producción.**

## Permisos por rol

| Función | Admin | Dueña | Trabajador |
| --- | --- | --- | --- |
| Vender | ✅ | ✅ | ✅ |
| Agregar productos | ✅ | ✅ | ✅ |
| Editar / eliminar productos | ✅ | ✅ | ❌ |
| Compras, costos y ganancias | ✅ | ✅ | ❌ |
| Licencia y gestión de usuarios | ✅ | ❌ | ❌ |

## Estructura del proyecto

```text
tiendapro/
├── TiendaPro.py              # Punto de entrada
├── ABRIR.bat                 # Instala, crea acceso directo y ejecuta (Windows)
├── CREAR_ACCESO_DIRECTO.bat
├── requirements.txt
├── assets/                   # Logo (icono.ico / icono.png)
├── src/
│   ├── config.py             # Constantes, roles, colores
│   ├── database.py           # Conexión SQLite y migraciones
│   ├── security.py           # Hash de contraseñas
│   ├── models.py             # Modelos (Producto)
│   ├── utils.py              # Utilidades (parseo de decimales)
│   ├── repositories/         # Acceso a datos (productos, compras, ventas, reportes...)
│   └── ui/                   # Interfaz (ventana principal, diálogos, componentes)
└── tests/                    # Pruebas automáticas
```

## Pruebas

```bash
python -m unittest discover -s tests -v
```

Las pruebas cubren el inicio de sesión y la migración de contraseñas, el costo promedio, el cálculo de ganancias, el control de stock y el parseo de decimales.

## Tecnologías

- Python
- CustomTkinter
- Pillow
- SQLite

## Próximas mejoras

- Anular ventas devolviendo el stock
- Cierre de caja diario
- Registro de mermas (productos vencidos o dañados)
- Copia de seguridad automática de la base de datos
- Bloqueo de la aplicación al vencer la licencia

## Licencia

Este proyecto se distribuye bajo la licencia MIT. Consulta el archivo [LICENSE](LICENSE).
