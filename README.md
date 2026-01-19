# Herramientas Internas MCBrokers

Sistema integrado con dos herramientas principales:
1. **Cotizador GNP Salud** - Para cotizar seguros de salud (STRM y BIMBO)
2. **Selector de Campañas de Emisión Autos** - Para identificar códigos de campaña

## 📂 Estructura del Proyecto

```
proyecto/
├── index.html                          # Archivo principal
├── data/
│   ├── campanas.json                   # 40 campañas de autos
│   └── ejemplos-expedientes.json       # Ejemplos de formato por empresa
├── pricing/                            # (Necesitas agregar estos)
│   ├── pricing-bimbo.json
│   ├── pricing-strm.json
│   └── pricing-strm-excesos.json
└── assets/                             # (Necesitas agregar esto)
    └── Logo_Colores_MCB.png
```

## 🚀 Instalación

1. **Descarga todos los archivos** manteniendo la estructura de carpetas
2. **Agrega tus archivos de pricing** en la carpeta `pricing/`
3. **Agrega el logo** en la carpeta `assets/`
4. **Abre `index.html`** en tu navegador

## 📊 Datos Externos (JSON)

### `data/campanas.json`
Contiene las 40 campañas con:
- Empresa
- Aseguradora
- Vía de pago
- Periodicidad
- Nombre de campaña
- Regla de dígitos de expediente

### `data/ejemplos-expedientes.json`
Contiene ejemplos de formato de expediente por empresa:
- STRM (7 dígitos)
- Caja de Ahorro (5 dígitos)
- CTBR (8 dígitos)
- Empleados de STRM (6 dígitos)
- MCB (RFC sin homoclave)
- Tecmarketing (8 dígitos)

## ✏️ Cómo Actualizar Datos

### Agregar/Modificar Campañas
Edita `data/campanas.json`:
```json
{
  "empresa": "Nueva Empresa",
  "aseguradora": "GNP",
  "via_pago": "DxN",
  "periodicidad": "Semanal",
  "campana": "NUEVA_CAMPANA",
  "digitos_expediente": "8 dígitos"
}
```

### Agregar/Modificar Ejemplos
Edita `data/ejemplos-expedientes.json`:
```json
{
  "Nueva Empresa": [
    "12345678",
    "87654321"
  ]
}
```

## 🎯 Características

### Cotizador GNP Salud
- Cotización para STRM y BIMBO
- Cálculo de extra-prima
- Modalidad pago mixto (STRM)
- Cálculo por meses de cobertura

### Selector de Campañas
- Búsqueda rápida por nombre
- Filtros en cascada (Empresa → Aseguradora → Periodicidad)
- Botón copiar código de campaña
- Ejemplos de expediente contextuales
- Contador de resultados

## 📈 Ventajas de la Estructura Optimizada

1. **Mantenimiento fácil**: Actualiza datos sin tocar código
2. **Reutilización**: Otros sistemas pueden consumir los JSON
3. **Versionamiento**: Git trackea mejor los cambios
4. **Performance**: HTML 70% más ligero
5. **Escalabilidad**: Fácil agregar empresas/campañas

## 🔧 Soporte

Para dudas o mejoras, contacta al equipo de desarrollo.

---

**Versión**: 1.1
**Última actualización**: Enero 2026  
**MCBrokers** - Herramientas Internas
