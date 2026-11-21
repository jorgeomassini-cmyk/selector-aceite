<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>LubriFinder Pro - Selector Motor y Transmisión</title>
  <style>
    :root {
      --primary: #1d4ed8;
      --primary-hover: #1e40af;
      --dark: #0f172a;
      --bg: #f1f5f9;
      --card: #ffffff;
      --border: #cbd5e1;
      --accent: #16a34a;
      --warn-bg: #fef3c7;
      --warn-border: #f59e0b;
    }
    * { box-sizing: border-box; font-family: system-ui, -apple-system, sans-serif; margin: 0; padding: 0; }
    body { background: var(--bg); color: var(--dark); line-height: 1.45; padding-bottom: 40px; }
    header {
      background: var(--dark); color: #fff; padding: 14px 16px;
      display: flex; flex-wrap: wrap; justify-content: space-between; align-items: center; gap: 10px;
      position: sticky; top: 0; z-index: 40; box-shadow: 0 2px 6px rgba(0,0,0,0.15);
    }
    .brand { font-weight: 800; font-size: 1.2rem; letter-spacing: -0.5px; }
    .brand span { color: #60a5fa; }
    .nav-btns { display: flex; gap: 6px; flex-wrap: wrap; }
    button { cursor: pointer; border: none; border-radius: 6px; padding: 8px 12px; font-weight: 600; font-size: 0.82rem; transition: 0.15s; }
    button:active { transform: scale(0.98); }
    .btn-dl { background: var(--accent); color: #fff; }
    .btn-sec { background: #334155; color: #fff; }
    .btn-primary { background: var(--primary); color: #fff; width: 100%; padding: 12px; font-size: 0.95rem; margin-top: 10px; }
    .btn-primary:hover { background: var(--primary-hover); }
    .container { max-width: 780px; margin: 18px auto; padding: 0 12px; }
    .card { background: var(--card); border: 1px solid #e2e8f0; border-radius: 10px; padding: 16px; margin-bottom: 16px; box-shadow: 0 1px 3px rgba(0,0,0,0.04); }
    h1 { font-size: 1.25rem; margin-bottom: 4px; }
    h2 { font-size: 1.05rem; margin-bottom: 10px; color: var(--dark); border-bottom: 1px solid #e2e8f0; padding-bottom: 6px; }
    p.sub { color: #475569; font-size: 0.85rem; margin-bottom: 14px; }
    .tabs { display: flex; gap: 6px; margin-bottom: 12px; }
    .tab { flex: 1; background: #e2e8f0; color: #334155; padding: 9px 6px; font-size: 0.85rem; }
    .tab.active { background: var(--primary); color: #fff; }
    input, select, textarea { width: 100%; padding: 10px; border: 1px solid var(--border); border-radius: 8px; font-size: 0.95rem; background: #fff; }
    input.upper { text-transform: uppercase; }
    .chips { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 12px; }
    .chip { background: #eff6ff; color: var(--primary); border: 1px solid #bfdbfe; padding: 5px 10px; font-size: 0.78rem; border-radius: 16px; }
    .plate-badge { display: inline-block; border: 2px solid #000; border-radius: 5px; overflow: hidden; margin-bottom: 10px; background: #fff; }
    .plate-top { background: #1e40af; color: #fff; font-size: 0.6rem; text-align: center; padding: 2px 10px; font-weight: 700; letter-spacing: 1px; }
    .plate-num { font-size: 1.25rem; font-weight: 800; padding: 3px 12px; letter-spacing: 2px; text-align: center; }
    .section-title { font-size: 0.8rem; text-transform: uppercase; letter-spacing: 0.5px; color: var(--primary); font-weight: 800; margin: 14px 0 6px; }
    .grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(155px, 1fr)); gap: 8px; margin-bottom: 10px; }
    .spec-box { background: #f8fafc; border: 1px solid #e2e8f0; padding: 9px 11px; border-radius: 8px; }
    .spec-label { font-size: 0.7rem; color: #64748b; text-transform: uppercase; font-weight: 700; }
    .spec-val { font-size: 0.95rem; font-weight: 700; color: var(--dark); margin-top: 2px; }
    .brands-table { width: 100%; border-collapse: collapse; margin-top: 8px; font-size: 0.85rem; }
    .brands-table th, .brands-table td { border: 1px solid #e2e8f0; padding: 8px; text-align: left; }
    .brands-table th { background: #f1f5f9; font-size: 0.75rem; text-transform: uppercase; color: #475569; }
    .brand-tag { font-weight: 700; color: var(--dark); }
    .alert { background: var(--warn-bg); border-left: 4px solid var(--warn-border); padding: 9px 11px; font-size: 0.83rem; border-radius: 4px; margin: 10px 0; }
    .modal { display: none; position: fixed; inset: 0; background: rgba(15,23,42,0.7); padding: 14px; overflow-y: auto; z-index: 50; }
    .modal.open { display: flex; align-items: flex-start; justify-content: center; padding-top: 30px; }
    .modal-content { background: #fff; width: 100%; max-width: 520px; border-radius: 10px; padding: 18px; }
    .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }
    .form-group { margin-bottom: 9px; }
    .form-group.full { grid-column: 1 / -1; }
    .form-group label { display: block; font-size: 0.75rem; font-weight: 700; margin-bottom: 3px; color: #334155; }
    .hist-item { border-bottom: 1px solid #e2e8f0; padding: 8px 0; display: flex; justify-content: space-between; align-items: center; font-size: 0.85rem; }
    .hidden { display: none; }
  </style>
</head>
<body>

<header>
  <div class="brand">Lubri<span>Finder</span> Pro</div>
  <div class="nav-btns">
    <button class="btn-sec" onclick="openModal('modal-reg')">+ Registrar Auto</button>
    <button class="btn-sec" onclick="openModal('modal-hist')">Historial (<span id="hist-count">0</span>)</button>
    <button class="btn-dl" onclick="downloadBackupHTML()">⬇ Guardar App + Datos</button>
  </div>
</header>

<div class="container">
  <div class="card">
    <h1>Selector Técnico de Lubricantes</h1>
    <p class="sub">Consulta rápida de Motor y Transmisión por Patente, VIN o Vehículo (100% Offline).</p>

    <div class="tabs">
      <button class="tab active" id="tab-pat" onclick="setMode('patente')">Por Patente</button>
      <button class="tab" id="tab-vin" onclick="setMode('vin')">Por VIN (Chasis)</button>
      <button class="tab" id="tab-mod" onclick="setMode('modelo')">Marca / Modelo</button>
    </div>

    <div id="box-text">
      <input type="text" id="search-input" class="upper" placeholder="Ej: AE123CD o AAA123" maxlength="17" onkeyup="if(event.key==='Enter') buscar()">
    </div>

    <div id="box-select" class="hidden">
      <select id="model-select"></select>
    </div>

    <button class="btn-primary" onclick="buscar()">Buscar Ficha Técnica</button>

    <div class="chips">
      <button class="chip" onclick="quickSearch('AE123CD')">AE123CD • VW Polo 1.6 MSI (AT)</button>
      <button class="chip" onclick="quickSearch('AG450RT')">AG450RT • Toyota Hilux 2.8</button>
      <button class="chip" onclick="quickSearch('AF889KL')">AF889KL • VW Amarok V6</button>
      <button class="chip" onclick="quickSearch('AD712MP')">AD712MP • Peugeot 208 1.6</button>
      <button class="chip" onclick="quickSearch('AC305BN')">AC305BN • Ford Ranger 3.2</button>
    </div>
  </div>

  <div id="result-area"></div>
</div>

<div class="modal" id="modal-reg">
  <div class="modal-content">
    <h2>+ Registrar Nuevo Vehículo / Cliente</h2>
    <div class="form-grid">
      <div class="form-group">
        <label>Patente (Opcional)</label>
        <input type="text" id="reg-pat" class="upper" placeholder="AA123BB">
      </div>
      <div class="form-group">
        <label>VIN / Chasis (Opcional)</label>
        <input type="text" id="reg-vin" class="upper" placeholder="17 caracteres">
      </div>
      <div class="form-group full">
        <label>Vehículo (Marca, Modelo, Año, Motor) *</label>
        <input type="text" id="reg-veh" placeholder="Ej: Chevrolet Cruze 1.4 Turbo (2019)">
      </div>
      <div class="form-group">
        <label>Viscosidad Motor *</label>
        <input type="text" id="reg-mvisc" placeholder="Ej: 5W-30">
      </div>
      <div class="form-group">
        <label>Norma Motor *</label>
        <input type="text" id="reg-mnorm" placeholder="Ej: Dexos 1 Gen 2">
      </div>
      <div class="form-group">
        <label>Capacidad Motor (Lts)</label>
        <input type="text" id="reg-mcap" placeholder="Ej: 4.0 L (con filtro)">
      </div>
      <div class="form-group">
        <label>Tipo y Código Caja</label>
        <input type="text" id="reg-tbox" placeholder="Ej: Automática 6T35">
      </div>
      <div class="form-group">
        <label>Fluido / Norma Caja *</label>
        <input type="text" id="reg-tnorm" placeholder="Ej: Dexron VI">
      </div>
      <div class="form-group">
        <label>Capacidad Caja (Lts)</label>
        <input type="text" id="reg-tcap" placeholder="Ej: 8.1 L total / 5 L cambio">
      </div>
      <div class="form-group full">
        <label>Equivalencias en Stock (Nishimoto, Valvoline, Motul, etc.)</label>
        <textarea id="reg-brands" rows="2" placeholder="Ej: Motor: Valvoline Full Synthetic 5W-30 | Caja: Nishimoto ATF VI"></textarea>
      </div>
      <div class="form-group full">
        <label>Notas de Taller</label>
        <input type="text" id="reg-notes" placeholder="Ej: Filtro aceite Mann W712/95 - Tapón 25 Nm">
      </div>
    </div>
    <div style="display:flex; gap:8px; margin-top:12px;">
      <button class="btn-primary" style="margin-top:0;" onclick="guardarVehiculo()">Guardar Ficha</button>
      <button class="btn-sec" onclick="closeModal('modal-reg')">Cancelar</button>
    </div>
  </div>
</div>

<div class="modal" id="modal-hist">
  <div class="modal-content">
    <h2>Historial de Consultas Recientes</h2>
    <div id="hist-list" style="max-height:320px; overflow-y:auto; margin-bottom:12px;"></div>
    <div style="display:flex; gap:8px;">
      <button class="btn-sec" style="background:#dc2626;" onclick="limpiarHistorial()">Borrar Historial</button>
      <button class="btn-primary" style="margin-top:0;" onclick="closeModal('modal-hist')">Cerrar</button>
    </div>
  </div>
</div>

<script id="app-data-script">
const DEFAULT_DB = [
  {
    id: "vw-polo-16-at",
    patente: "AE123CD",
    vinPrefix: "9BW",
    vehiculo: "Volkswagen Polo / Virtus 1.6 16V MSI (2018-2023)",
