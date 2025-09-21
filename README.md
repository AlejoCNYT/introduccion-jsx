
# Laboratorio / Lab — Introducción a JSX · Intro to JSX

> **ES/EN International README** — instrucciones multiplataforma (Windows / macOS / Linux).  
> **Objetivo / Goal:** editar una app React existente para renderizar `Hello world, my name is <tu nombre>` usando JSX y pasar las pruebas automáticas de Ada.

---

## ✅ Requisitos / Requirements
- Node.js 18+ y npm (recomendado LTS).  
- Git.  
- Navegador moderno.  
- **Ada Client** binario apropiado para tu sistema (proporcionado por tu cohorte).

Verifica versiones / Check versions:
```bash
node -v
npm -v
git --version
```

---

## 1) Clonar el repositorio / Clone the repository
```bash
# Windows (Git Bash) / macOS / Linux
git clone https://github.com/ada-school/assignments-micro-course-JSX
cd assignments-micro-course-JSX
```

## 2) Cambiar a la rama `intro` / Checkout the `intro` branch
```bash
git fetch --all
git checkout intro
# si falla / if it fails:
# git checkout -b intro origin/intro
```

## 3) Instalar dependencias / Install dependencies
```bash
npm install
```

## 4) Ejecutar en modo desarrollo / Run dev server
```bash
npm run dev
```
- Abre la URL que imprime la consola (p. ej. `http://localhost:5173/`).  
- Open the URL shown in terminal.

---

## 5) Iniciar la asignación en Ada / Start assignment in Ada
> **Importante:** este paso **inyecta/descarga las pruebas** del lab. Úsalo en **otra terminal** situada en la **raíz del proyecto**.

### Windows (PowerShell)
```powershell
.\ada-client.exe start https://eci.learn.ada-school.org/cohorts/<YOUR_COHORT_ID>
```

### macOS
```bash
./ada-client start https://eci.learn.ada-school.org/cohorts/<YOUR_COHORT_ID>
```

### Linux
```bash
./ada-client-linux start https://eci.learn.ada-school.org/cohorts/<YOUR_COHORT_ID>
```

- Se abrirá el navegador para login. Espera a que la terminal indique **connected**.  
- Browser login will open. Wait until terminal shows **connected**.

---

## 6) Correr pruebas locales / Run local tests

<img width="786" height="233" alt="imagen" src="https://github.com/user-attachments/assets/0a45e8e1-bcff-4d46-bc33-a9c1ee40d90d" />

```bash
npm run ada-test
```
Si dice **“No test files found”**, significa que **no has iniciado** el lab con `ada-client` (paso 5).

---

## 7) Tarea de código / Coding task
Abre `src/App.jsx` (o el archivo indicado por tu cohorte) y:

**ES**
1. Declara la constante con tu nombre completo:  
   ```js
   export const myName = "Tu Nombre Completo";
   ```
2. Renderiza con JSX:  
   ```jsx
   export function App() {
     return <div>Hello world, my name is {myName}</div>
   }
   ```

**EN**
1. Set the constant with your full name.  
2. Render the sentence using JSX expression braces `{}`.

Vuelve a correr / Re-run:
```bash
npm run ada-test
```

---

## 8) Enviar la asignación / Submit your assignment
Cuando todas las pruebas pasen / When all tests pass:

### Windows (PowerShell)
```powershell
.\ada-client.exe submit https://eci.learn.ada-school.org/cohorts/<YOUR_COHORT_ID>
```

### macOS
```bash
./ada-client submit https://eci.learn.ada-school.org/cohorts/<YOUR_COHORT_ID>
```

### Linux
```bash
./ada-client-linux submit https://eci.learn.ada-school.org/cohorts/<YOUR_COHORT_ID>
```

---

## Estructura típica / Typical structure
```
assignments-micro-course-JSX/
  src/
    App.jsx
    main.jsx
  package.json
  vite.config.*
  # (Las pruebas se descargan al iniciar con ada-client)
```

---

## Solución de problemas / Troubleshooting

**“No test files found”**  
- Corre el paso 5 (start con ada-client) desde la raíz del proyecto.  
- Verifica rama `intro`: `git rev-parse --abbrev-ref HEAD` → debe decir `intro`.  
- Reinstala deps: `rm -rf node_modules package-lock.json && npm install` (en Windows PowerShell: `Remove-Item node_modules -Recurse -Force; Remove-Item package-lock.json -Force; npm install`).

**El dev server no abre**  
- Cierra procesos previos y vuelve a `npm run dev`.  
- Cambia el puerto si choca: `npm run dev -- --port=5174`.

**Problemas con permisos del binario Ada**  
- macOS/Linux: `chmod +x ./ada-client*` y ejecuta de nuevo.  
- Windows: usa **PowerShell** (no Git Bash) para `ada-client.exe`.

**Tests siguen fallando**  
- Asegúrate de que el texto renderizado sea exactamente:  
  `Hello world, my name is <tu nombre>` (sin puntos finales/extra espacios).

---

## Consejos / Tips
- Usa VS Code con la extensión de ESLint/Prettier si tu cohorte la recomienda.  
- Commits pequeños y descriptivos ayudan a depurar.

¡Éxitos! / Good luck!

