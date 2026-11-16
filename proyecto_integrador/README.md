# Lab 1 · Copiloto de oferta pyme con facturas (Banco Andino del Pacífico, ficticio)

Notebooks del Proyecto Integrador — Data Scientist Cognitive.

| Notebook | Servicio | Insumos |
|---|---|---|
| `notebooks/01_document_intelligence_oferta_pyme.ipynb` | Document Intelligence (prebuilt-layout, prebuilt-invoice) | `data/Politica_Oferta_Pyme_Facturas_BAP.pdf`, `data/Factura_20999999975_E001-00000412.pdf` |
| `notebooks/02_content_safety_blocklist_oferta_pyme.ipynb` | Content Safety + blocklist | mensajes definidos en el notebook |

Todos los documentos y datos son sintéticos.

## Configuración (Windows / PowerShell)

```powershell
cd lab1
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
python -m ipykernel install --user --name lab1-venv --display-name "Python 3 (lab1 .venv)"

copy .env.example .env      # y completar los endpoints
az login --tenant DSCNTT.onmicrosoft.com
```

En macOS / Linux: `source .venv/bin/activate` y `cp .env.example .env`.

En VS Code: abrir la carpeta `lab1`, abrir el notebook y elegir el kernel **Python 3 (lab1 .venv)**.

## Autenticación

Los notebooks usan `DefaultAzureCredential` (sesión de `az login`), sin API keys. Si un servicio responde 401/403,
el usuario necesita el rol **Cognitive Services User** sobre ese recurso (Control de acceso (IAM)).

Las salidas se escriben en `outputs/` (ignorada por git).
