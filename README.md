# MonyMonty UI - Design Tokens

Monorepo centralizado de **Design Tokens** para el ecosistema de aplicaciones **MonyMonty**, gestionado con **NPM Workspaces**, orquestado con **Turborepo** y compilado con **Style Dictionary**.

---

## 📁 Arquitectura del Repositorio

```plaintext
monymonty-ui/
├── packages/
│   └── tokens/
│       ├── build/
│       │   ├── mobile/
│       │   │   └── MonyMontyStyle.dart     # Tokens tipados para Flutter (Color(0xFF...))
│       │   └── web/
│       │       └── MonyMontyStyle.css      # Variables CSS nativas (:root)
│       ├── src/                            # Archivos JSON de tokens por taxonomía
│       │   ├── F02-color.json
│       │   ├── F03-tipografia.json
│       │   ├── F04-espacio-forma-layout.json
│       │   ├── F05-movimiento.json
│       │   ├── F06-iconografia-logo.json
│       │   ├── F07-componentes-movil.json
│       │   ├── F08-componentes-web.json
│       │   ├── F09-sombras-elevacion.json
│       │   ├── F10-estados.json
│       │   └── F11-visualizacion-datos.json
│       ├── config.json                     # Configuración de compilación Style Dictionary
│       └── package.json                    # @ougmontiel/monymonty-tokens
├── package.json                            # Orquestador raíz (NPM Workspaces)
├── turbo.json                              # Pipeline y caché con Turborepo
└── README.md                               # Guía de inicio y comandos
```

---

## 🚀 Requisitos Previos

- **Node.js**: `>= 18.0.0` (recomendado `>= 20.0.0`)
- **NPM**: `>= 9.0.0` (o compatible con Workspaces)

---

## 🛠️ Guía de Ejecución Paso a Paso

### 1. Inicializar e Instalar Dependencias

Desde la raíz del proyecto (`monymonty-ui/`), ejecuta la instalación. NPM resolverá las dependencias de la raíz y enlazará automáticamente los paquetes de `packages/*`:

```bash
npm install
```

### 2. Ejecutar la Compilación de Tokens

Compila todos los paquetes usando el pipeline optimizado de Turborepo:

```bash
npm run build
```

Turborepo ejecutará la tarea `build` del paquete `@ougmontiel/monymonty-tokens`, generando los artefactos en:
- **Web**: `packages/tokens/build/web/MonyMontyStyle.css`
- **Flutter**: `packages/tokens/build/mobile/MonyMontyStyle.dart`

---

## 📦 Comandos Adicionales

### Compilar solo el paquete de Tokens (sin Turborepo)
```bash
npm run build --workspace=@ougmontiel/monymonty-tokens
```

### Modo Limpieza
```bash
npm run clean
```
