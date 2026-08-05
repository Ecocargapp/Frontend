# Graph Report - .  (2026-08-05)

## Corpus Check
- cluster-only mode — file stats not available

## Summary
- 42 nodes · 52 edges · 10 communities
- Extraction: 96% EXTRACTED · 4% INFERRED · 0% AMBIGUOUS · INFERRED: 2 edges (avg confidence: 0.82)
- Token cost: 556 input · 95 output

## Graph Freshness
- Built from commit: `8e18b98c`
- Run `git rev-parse HEAD` and compare to check if the graph is stale.
- Run `graphify update .` after code changes (no API cost).

## Community Hubs (Navigation)
- Fattening Management API
- Feed Consumption Backend
- User Auth and Login
- Reports API Wrappers
- Excel Export Utilities
- Farm Modules Overview
- Sow Census Dashboard
- PDF Export Utilities
- Task Calendar Management

## God Nodes (most connected - your core abstractions)
1. `api() — Fetch wrapper (ceba.html)` - 7 edges
2. `AgroSoft Backend REST API` - 7 edges
3. `agrosoft_token (sessionStorage)` - 7 edges
4. `api() — Fetch wrapper (informes.html)` - 6 edges
5. `Granja de Cría` - 5 edges
6. `api() — Fetch wrapper (cria.html)` - 5 edges
7. `api() — Fetch wrapper (tareas.html)` - 5 edges
8. `Informes de Cría` - 4 edges
9. `api() — Fetch wrapper (index.html)` - 4 edges
10. `api() — Fetch wrapper (consumo.html)` - 4 edges

## Surprising Connections (you probably didn't know these)
- `Granja de Cría` --references--> `Ceba (Engorde)`  [EXTRACTED]
  cria.html → ceba.html
- `Index / Login / Panel de Control` --references--> `Granja de Cría`  [EXTRACTED]
  index.html → cria.html
- `Granja de Cría` --references--> `Consumo Diario de Alimento`  [EXTRACTED]
  cria.html → consumo.html
- `Granja de Cría` --references--> `Tareas y Vacunación`  [EXTRACTED]
  cria.html → tareas.html
- `Consumo Diario de Alimento` --shares_data_with--> `Informes de Cría`  [INFERRED]
  consumo.html → informes.html

## Import Cycles
- None detected.

## Hyperedges (group relationships)
- **Cría module: census, ficha, tablero all feed from cria api into reproductive management** — cria_cargar_censo, cria_abrir_ficha, cria_cargar_tablero, cria_api [EXTRACTED 0.95]
- **informes and tareas share export capability via xlsx and jspdf** — informes_exportar_excel, informes_exportar_pdf, tareas_exportar_excel, tareas_exportar_pdf, ext_xlsx, ext_jspdf [EXTRACTED 1.00]

## Communities (10 total, 0 thin omitted)

### Community 0 - "Fattening Management API"
Cohesion: 0.47
Nodes (6): api() — Fetch wrapper (ceba.html), cargarConsumo() — Load feed consumption (ceba), cargarGranjas() — Load farms list, cargarInventario() — Load fattening inventory, cargarMovimientos() — Load movements, liquidar() — Compute fattening settlement

### Community 1 - "Feed Consumption Backend"
Cohesion: 0.40
Nodes (5): AgroSoft Backend REST API, api() — Fetch wrapper (consumo.html), cargarBandas() — Load bands for costing, cargarDiario() — Load daily feed records, AgroSoft Frontend README

### Community 2 - "User Auth and Login"
Cohesion: 0.60
Nodes (5): api() — Fetch wrapper (index.html), cargarUsuarios() — Load users table, entrarApp() — Show main app, login() — Authenticate user, agrosoft_token (sessionStorage)

### Community 3 - "Reports API Wrappers"
Cohesion: 0.40
Nodes (5): api() — Fetch wrapper (informes.html), cargarBandas() — Load band report, cargarCostos() — Load cost report, cargarDescarte() — Load cull candidates, cargarRepro() — Load reproductive report

### Community 4 - "Excel Export Utilities"
Cohesion: 0.50
Nodes (4): Ceba (Engorde), SheetJS / xlsx library, exportarExcel() — Export to Excel (informes), exportarExcel() — Export to Excel (tareas)

### Community 5 - "Farm Modules Overview"
Cohesion: 0.67
Nodes (4): Consumo Diario de Alimento, Granja de Cría, Index / Login / Panel de Control, Informes de Cría

### Community 6 - "Sow Census Dashboard"
Cohesion: 0.50
Nodes (4): abrirFicha() — Open sow detail, api() — Fetch wrapper (cria.html), cargarCenso() — Load sow census, cargarTablero() — Load dashboard

### Community 7 - "PDF Export Utilities"
Cohesion: 0.50
Nodes (4): jsPDF library, exportarPDF() — Export to PDF (informes), Tareas y Vacunación, exportarPDF() — Export to PDF (tareas)

### Community 8 - "Task Calendar Management"
Cohesion: 0.50
Nodes (4): api() — Fetch wrapper (tareas.html), cargarCatalogo() — Load task catalogue, generar() — Generate task calendar, marcarHecha() — Mark task done

## Knowledge Gaps
- **20 isolated node(s):** `AgroSoft Frontend README`, `Index / Login / Panel de Control`, `abrirFicha() — Open sow detail`, `cargarCenso() — Load sow census`, `cargarTablero() — Load dashboard` (+15 more)
  These have ≤1 connection - possible missing edges or undocumented components.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `agrosoft_token (sessionStorage)` connect `User Auth and Login` to `Fattening Management API`, `Feed Consumption Backend`, `Reports API Wrappers`, `Sow Census Dashboard`, `Task Calendar Management`?**
  _High betweenness centrality (0.197) - this node is a cross-community bridge._
- **Why does `AgroSoft Backend REST API` connect `Feed Consumption Backend` to `Fattening Management API`, `User Auth and Login`, `Reports API Wrappers`, `Sow Census Dashboard`, `Task Calendar Management`?**
  _High betweenness centrality (0.176) - this node is a cross-community bridge._
- **Why does `api() — Fetch wrapper (ceba.html)` connect `Fattening Management API` to `Feed Consumption Backend`, `User Auth and Login`?**
  _High betweenness centrality (0.150) - this node is a cross-community bridge._
- **What connects `AgroSoft Frontend README`, `Index / Login / Panel de Control`, `abrirFicha() — Open sow detail` to the rest of the system?**
  _20 weakly-connected nodes found - possible documentation gaps or missing edges._