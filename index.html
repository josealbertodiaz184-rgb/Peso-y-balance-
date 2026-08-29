<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Peso y Balance MD-82 (YV664T)</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body { font-family: Arial, sans-serif; background-color: #0f172a; color: #f8fafc; margin: 0; padding: 15px; }
        .container { display: flex; flex-wrap: wrap; gap: 15px; max-width: 1200px; margin: auto; }
        .card { background: #1e293b; padding: 15px; border-radius: 8px; flex: 1; min-width: 300px; box-shadow: 0 4px 6px rgba(0,0,0,0.3); }
        h2 { border-bottom: 2px solid #38bdf8; padding-bottom: 5px; color: #38bdf8; font-size: 1.1rem; margin-top: 0; }
        .input-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 10px; }
        label { font-size: 0.85rem; color: #94a3b8; display: block; margin-bottom: 3px; }
        input { width: 90%; padding: 6px; border-radius: 4px; border: 1px solid #475569; background: #0f172a; color: #fff; text-align: right; }
        .results { font-size: 1rem; margin-top: 10px; padding: 8px; background: #0f172a; border-radius: 4px; }
        .status-ok { color: #4ade80; font-weight: bold; }
        .status-alert { color: #f87171; font-weight: bold; }
    </style>
</head>
<body>

<h2 style="text-align: center; color: #38bdf8; margin-bottom: 15px;">HOJA DE DESPACHO DIGITAL — MD-82 (YV664T)</h2>

<div class="container">
    <!-- Formulario -->
    <div class="card">
        <h2>1. Datos Operativos Básicos</h2>
        <div class="input-grid">
            <div>
                <label>DOW (kg):</label>
                <input type="number" id="dow" value="37223" oninput="calcularWB()">
            </div>
            <div>
                <label>DOI (Índice Seco):</label>
                <input type="number" id="doi" value="48.5" step="0.1" oninput="calcularWB()">
            </div>
        </div>

        <h2>2. Distribución de Pasajeros (PAX)</h2>
        <div class="input-grid">
            <div>
                <label>Cabin A (Filas 1-8):</label>
                <input type="number" id="paxA" value="34" oninput="calcularWB()">
            </div>
            <div>
                <label>Cabin B (Filas 9-21):</label>
                <input type="number" id="paxB" value="50" oninput="calcularWB()">
            </div>
            <div>
                <label>Cabin C (Filas 22-35):</label>
                <input type="number" id="paxC" value="54" oninput="calcularWB()">
            </div>
            <div>
                <label>Peso Promedio PAX (kg):</label>
                <input type="number" id="paxWeight" value="75" oninput="calcularWB()">
            </div>
        </div>

        <h2>3. Carga en Bodegas (kg)</h2>
        <div class="input-grid">
            <div>
                <label>Comp 1 (Max 1626kg):</label>
                <input type="number" id="c1" value="0" oninput="calcularWB()">
            </div>
            <div>
                <label>Comp 2 (Max 1326kg):</label>
                <input type="number" id="c2" value="612" oninput="calcularWB()">
            </div>
            <div>
                <label>Comp 3 (Max 1438kg):</label>
                <input type="number" id="c3" value="1080" oninput="calcularWB()">
            </div>
            <div>
                <label>Comp 4 (Max 1014kg):</label>
                <input type="number" id="c4" value="0" oninput="calcularWB()">
            </div>
        </div>

        <h2>4. Combustible (kg)</h2>
        <div class="input-grid">
            <div>
                <label>Takeoff Fuel (kg):</label>
                <input type="number" id="fuel" value="10000" oninput="calcularWB()">
            </div>
        </div>

        <div class="results">
            <div>ZFW: <strong id="zfw">0</strong> kg (Max: 49,200)</div>
            <div>TOW: <strong id="tow">0</strong> kg (Max: 64,800)</div>
            <div>% MAC TOW: <strong id="mac">0</strong>%</div>
            <div id="statusBox" style="margin-top:5px;">Estado: <span class="status-ok">EN LIMITES</span></div>
        </div>
    </div>

    <!-- Gráfica -->
    <div class="card">
        <h2>5. Envolvente de Vuelo (% MAC vs Peso)</h2>
        <canvas id="cgChart"></canvas>
    </div>
</div>

<script>
// Polígono del Envolvente de CG del MD-82
const cgEnvelope = [
    { x: 14.0, y: 37000 },
    { x: 14.0, y: 54400 },
    { x: 20.0, y: 64800 },
    { x: 33.0, y: 64800 },
    { x: 33.0, y: 37000 },
    { x: 14.0, y: 37000 }
];

let myChart;

function initChart() {
    const ctx = document.getElementById('cgChart').getContext('2d');
    myChart = new Chart(ctx, {
        type: 'scatter',
        data: {
            datasets: [
                {
                    label: 'Envolvente MD-82',
                    data: cgEnvelope,
                    showLine: true,
                    borderColor: '#94a3b8',
                    borderWidth: 2,
                    pointRadius: 0,
                    fill: false
                },
                {
                    label: 'Punto TOW',
                    data: [{ x: 20, y: 50000 }],
                    backgroundColor: '#38bdf8',
                    pointRadius: 7
                }
            ]
        },
        options: {
            scales: {
                x: { title: { display: true, text: '% MAC', color: '#fff' }, min: 10, max: 38 },
                y: { title: { display: true, text: 'Peso Total (kg)', color: '#fff' }, min: 35000, max: 68000 }
            },
            plugins: { legend: { labels: { color: '#fff' } } }
        }
    });
}

function calcularWB() {
    const dow = parseFloat(document.getElementById('dow').value) || 0;
    const doi = parseFloat(document.getElementById('doi').value) || 0;
    
    const paxA = parseFloat(document.getElementById('paxA').value) || 0;
    const paxB = parseFloat(document.getElementById('paxB').value) || 0;
    const paxC = parseFloat(document.getElementById('paxC').value) || 0;
    const pWeight = parseFloat(document.getElementById('paxWeight').value) || 75;

    const c1 = parseFloat(document.getElementById('c1').value) || 0;
    const c2 = parseFloat(document.getElementById('c2').value) || 0;
    const c3 = parseFloat(document.getElementById('c3').value) || 0;
    const c4 = parseFloat(document.getElementById('c4').value) || 0;
    
    const fuel = parseFloat(document.getElementById('fuel').value) || 0;

    // Cálculo de Pesos
    const wPaxA = paxA * pWeight;
    const wPaxB = paxB * pWeight;
    const wPaxC = paxC * pWeight;
    const totalPaxWeight = wPaxA + wPaxB + wPaxC;
    const totalCargoWeight = c1 + c2 + c3 + c4;

    const zfw = dow + totalPaxWeight + totalCargoWeight;
    const tow = zfw + fuel;

    // Deltas de Índice (Efecto de momento por zonas del MD-82)
    const dCabinA = (wPaxA / 100) * -0.8;
    const dCabinB = (wPaxB / 100) * 0.1;
    const dCabinC = (wPaxC / 100) * 0.9;

    const dC1 = (c1 / 100) * -0.9;
    const dC2 = (c2 / 100) * -0.3;
    const dC3 = (c3 / 100) * 0.4;
    const dC4 = (c4 / 100) * 0.8;

    const dFuel = (fuel / 1000) * -0.2;

    const indexTOW = doi + dCabinA + dCabinB + dCabinC + dC1 + dC2 + dC3 + dC4 + dFuel;

    // Conversión de Unidades de Índice a % MAC
    let macTOW = ((indexTOW - 20) * 0.42) + 12;
    macTOW = parseFloat(macTOW.toFixed(1));

    // Actualizar UI
    document.getElementById('zfw').innerText = zfw.toLocaleString();
    document.getElementById('tow').innerText = tow.toLocaleString();
    document.getElementById('mac').innerText = macTOW;

    const statusBox = document.getElementById('statusBox');
    
    // Validaciones de sobrepeso y envolvente
    if (tow > 64800 || zfw > 49200 || macTOW < 14.0 || macTOW > 33.0) {
        statusBox.innerHTML = 'Estado: <span class="status-alert">¡FUERA DE LÍMITES!</span>';
        myChart.data.datasets[1].backgroundColor = '#f87171';
    } else {
        statusBox.innerHTML = 'Estado: <span class="status-ok">DENTRO DE LÍMITES</span>';
        myChart.data.datasets[1].backgroundColor = '#4ade80';
    }

    myChart.data.datasets[1].data = [{ x: macTOW, y: tow }];
    myChart.update();
}

window.onload = function() {
    initChart();
    calcularWB();
};
</script>

</body>
</html>
