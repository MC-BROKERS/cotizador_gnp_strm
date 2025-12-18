# Cotizador GNP Salud - MCBrokers

Sistema de cotización interno para pólizas de Gastos Médicos Mayores de los clientes **BIMBO** y **STRM**.

## 📋 Descripción

Aplicación web que permite calcular primas de seguros de salud basadas en:
- **Género** (Hombre/Mujer)
- **Edad** (0-120 años)
- **Cliente** (BIMBO o STRM)
- **Producto** (solo STRM: Línea Azul o Excesos)
- **Plan** (solo STRM: Tarifa Plan 600 o Tarifa Otros Planes)

## 🚀 Características

### Cálculos disponibles:
- **Prima Total Anual**
- **Prima Mensual** (anual/12)
- **Prima Semanal** (anual/48)
- **Prima Catorcenal** (anual/24) - *solo BIMBO*
- **Proyección por meses de cobertura** (1-12 meses)

### Funcionalidades:
- ✅ Interfaz responsive (móvil y desktop)
- ✅ Diseño con colores corporativos MCBrokers
- ✅ Carga dinámica de tarifas desde JSON
- ✅ Validación de datos y manejo de errores
- ✅ Formato de moneda en pesos mexicanos (MXN)

## 📁 Estructura del proyecto

```
/
├── index.html                    # Aplicación principal
├── pricing-bimbo.json            # Tarifas BIMBO
├── pricing-strm.json             # Tarifas STRM - Línea Azul
├── pricing-strm-excesos.json     # Tarifas STRM - Excesos
└── Logo_Colores_MCB.png          # Logo corporativo (opcional)
```

## 🛠️ Instalación

1. **Clonar o descargar** todos los archivos en la misma carpeta
2. **Abrir** `index.html` en un navegador web moderno
3. **No requiere servidor** - funciona localmente

> ⚠️ **Nota**: Si el navegador bloquea la carga de archivos JSON locales, usa un servidor local simple:
> ```bash
> python -m http.server 8000
> # Acceder a: http://localhost:8000
> ```

## 📊 Estructura de tarifas (JSON)

### Formato general:
```json
{
  "version": "2025.XX.XX-cliente-v1",
  "last_updated": "2025-XX-XX",
  "moneda": "MXN",
  "cliente": "NOMBRE_CLIENTE",
  "reglas": {
    "iva": 0.16,
    "redondeo": 2
  },
  "tarifas": [
    {
      "rango": "00-04",
      "H": 6790,
      "M": 6190
    }
  ]
}
```

### STRM con múltiples planes:
```json
{
  "planes": {
    "Plan600": [ /* tarifas */ ],
    "OtrosPlanes": [ /* tarifas */ ]
  }
}
```

### Rangos de edad soportados:
- `00-04` (0-4 años)
- `05-14` (5-14 años) - *rango especial unificado*
- `15-19`, `20-24`, `25-29`, ... `75-79` (bloques de 5 años)
- `80-mas` (80+ años) - *rango abierto*

## 🎨 Personalización

### Colores corporativos (CSS):
```css
--mcb-blue: #0057A4;    /* Color primario */
--mcb-green: #2FA24A;   /* Color acento */
--mcb-lime: #9CCB3B;    /* Badge */
```

### Modificar tarifas:
1. Editar el archivo JSON correspondiente
2. Mantener estructura y formato de rangos
3. Recargar la página

## 📝 Uso

1. **Seleccionar empresa**: BIMBO o STRM
2. **Si es STRM**: Elegir Producto (Línea Azul/Excesos) y Plan
3. **Ingresar datos**: Género y Edad
4. **Consultar**: Ver resultados detallados
5. **Opcional**: Calcular primas por meses de cobertura

## 🔧 Tecnologías

- **HTML5** - Estructura
- **Tailwind CSS** (CDN) - Estilos
- **JavaScript Vanilla** - Lógica de negocio
- **JSON** - Base de datos de tarifas

## 📌 Requisitos

- Navegador moderno (Chrome, Firefox, Safari, Edge)
- JavaScript habilitado
- Archivos JSON en la misma carpeta que `index.html`

## 🐛 Solución de problemas

### Error: "No se pudo cargar tarifas"
- Verificar que los archivos JSON están en la misma carpeta
- Revisar permisos de lectura de archivos
- Usar servidor local si el navegador bloquea fetch local

### Tarifa no encontrada
- Validar que la edad ingresada tiene un rango correspondiente
- Revisar que el JSON contenga todos los rangos (00-04 hasta 80-mas)

### Resultados incorrectos
- Verificar decimales en JSON (usar `.` no `,`)
- Confirmar que género coincide con columnas H/M en JSON

## 📄 Versionado

- **v1.0** (2025-09-23): BIMBO y STRM Línea Azul
- **v1.1** (2025-12-18): Agregado STRM Excesos con selector de producto

## 👥 Contacto

**MCBrokers**  
Sistema de cotización interna

---

**Última actualización**: Diciembre 2025
