<!DOCTYPE html>
<html lang="da">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rubiks Terning — Singmaster-notation</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,500;9..144,700&family=IBM+Plex+Mono:wght@400;500;600&family=IBM+Plex+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0f1115;
    --bg-panel: #1a1d24;
    --bg-elevated: #232731;
    --border: #2d313d;
    --text: #e8e6e1;
    --text-muted: #8b8d93;
    --accent: #e8b75f;
    --accent-dim: #8b6f38;
    --danger: #c45454;

    --face-u: #f5f5f0;
    --face-d: #f5c518;
    --face-f: #1fa347;
    --face-b: #1658c2;
    --face-r: #c12e1f;
    --face-l: #e87a1a;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  html, body {
    height: 100%;
    overflow: hidden;
    background: var(--bg);
    color: var(--text);
    font-family: 'IBM Plex Sans', sans-serif;
    font-size: 14px;
  }

  /* Subtle grid background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      radial-gradient(circle at 20% 30%, rgba(232, 183, 95, 0.03) 0%, transparent 40%),
      radial-gradient(circle at 80% 70%, rgba(31, 163, 71, 0.025) 0%, transparent 40%);
    pointer-events: none;
    z-index: 0;
  }

  #app {
    position: relative;
    width: 100vw;
    height: 100vh;
    display: grid;
    grid-template-columns: 300px 1fr 280px;
    gap: 0;
    z-index: 1;
  }

  /* Left panel: moves */
  #left-panel {
    background: var(--bg-panel);
    border-right: 1px solid var(--border);
    padding: 24px 20px;
    overflow-y: auto;
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .panel-header {
    font-family: 'Fraunces', serif;
    font-weight: 500;
    font-size: 22px;
    letter-spacing: -0.01em;
    color: var(--text);
    line-height: 1.1;
  }

  .panel-subtitle {
    font-size: 12px;
    color: var(--text-muted);
    margin-top: 4px;
    font-style: italic;
    font-family: 'Fraunces', serif;
  }

  .section-label {
    font-size: 10px;
    font-weight: 600;
    letter-spacing: 0.12em;
    text-transform: uppercase;
    color: var(--accent);
    margin-bottom: 10px;
    display: block;
  }

  .move-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6px;
  }

  .face-group {
    display: contents;
  }

  .move-btn {
    background: var(--bg-elevated);
    border: 1px solid var(--border);
    color: var(--text);
    font-family: 'IBM Plex Mono', monospace;
    font-weight: 500;
    font-size: 15px;
    padding: 10px 12px;
    border-radius: 4px;
    cursor: pointer;
    transition: all 0.15s ease;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    position: relative;
  }

  .move-btn:hover:not(:disabled) {
    background: var(--border);
    border-color: var(--accent-dim);
    transform: translateY(-1px);
  }

  .move-btn:active:not(:disabled) {
    transform: translateY(0);
  }

  .move-btn:disabled {
    opacity: 0.4;
    cursor: not-allowed;
  }

  .move-btn .face-dot {
    width: 10px;
    height: 10px;
    border-radius: 2px;
    display: inline-block;
  }

  .move-btn[data-face="U"] .face-dot { background: var(--face-u); }
  .move-btn[data-face="D"] .face-dot { background: var(--face-d); }
  .move-btn[data-face="F"] .face-dot { background: var(--face-f); }
  .move-btn[data-face="B"] .face-dot { background: var(--face-b); }
  .move-btn[data-face="R"] .face-dot { background: var(--face-r); }
  .move-btn[data-face="L"] .face-dot { background: var(--face-l); }

  .action-btn {
    background: transparent;
    border: 1px solid var(--border);
    color: var(--text);
    font-family: 'IBM Plex Sans', sans-serif;
    font-size: 13px;
    font-weight: 500;
    padding: 9px 14px;
    border-radius: 4px;
    cursor: pointer;
    transition: all 0.15s ease;
    width: 100%;
    text-align: left;
    margin-bottom: 6px;
  }

  .action-btn:hover:not(:disabled) {
    border-color: var(--accent);
    color: var(--accent);
  }

  .action-btn.primary {
    background: var(--accent);
    color: var(--bg);
    border-color: var(--accent);
  }

  .action-btn.primary:hover:not(:disabled) {
    background: var(--text);
    color: var(--bg);
    border-color: var(--text);
  }

  .action-btn:disabled {
    opacity: 0.4;
    cursor: not-allowed;
  }

  /* Canvas area */
  #canvas-wrap {
    position: relative;
    background: var(--bg);
    overflow: hidden;
  }

  #canvas-wrap canvas {
    display: block;
    cursor: grab;
  }

  #canvas-wrap canvas:active {
    cursor: grabbing;
  }

  #canvas-hint {
    position: absolute;
    bottom: 20px;
    left: 50%;
    transform: translateX(-50%);
    font-size: 11px;
    color: var(--text-muted);
    font-style: italic;
    font-family: 'Fraunces', serif;
    pointer-events: none;
    letter-spacing: 0.02em;
  }

  /* Right panel: info */
  #right-panel {
    background: var(--bg-panel);
    border-left: 1px solid var(--border);
    padding: 24px 20px;
    overflow-y: auto;
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .legend {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 6px 10px;
  }

  .legend-item {
    display: flex;
    align-items: center;
    gap: 8px;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 12px;
    color: var(--text-muted);
  }

  .legend-swatch {
    width: 14px;
    height: 14px;
    border-radius: 2px;
    border: 1px solid rgba(255,255,255,0.1);
  }

  .history-box {
    background: var(--bg-elevated);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 12px;
    min-height: 80px;
    max-height: 200px;
    overflow-y: auto;
    font-family: 'IBM Plex Mono', monospace;
    font-size: 13px;
    line-height: 1.6;
    word-break: break-word;
    color: var(--text);
  }

  .history-box.empty {
    color: var(--text-muted);
    font-style: italic;
    font-family: 'Fraunces', serif;
  }

  .history-move {
    display: inline-block;
    padding: 1px 5px;
    margin: 1px;
    background: var(--bg-panel);
    border-radius: 3px;
  }

  .status-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 12px;
    color: var(--text-muted);
    padding: 6px 0;
  }

  .status-row strong {
    color: var(--text);
    font-family: 'IBM Plex Mono', monospace;
    font-weight: 500;
  }

  .toggles {
    display: flex;
    flex-direction: column;
    gap: 6px;
  }

  .toggle-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 13px;
    cursor: pointer;
    padding: 6px 0;
    user-select: none;
  }

  .toggle-switch {
    width: 32px;
    height: 18px;
    background: var(--border);
    border-radius: 999px;
    position: relative;
    transition: background 0.2s;
  }

  .toggle-switch::after {
    content: '';
    position: absolute;
    top: 2px;
    left: 2px;
    width: 14px;
    height: 14px;
    background: var(--text);
    border-radius: 50%;
    transition: transform 0.2s;
  }

  .toggle-row.active .toggle-switch {
    background: var(--accent);
  }

  .toggle-row.active .toggle-switch::after {
    transform: translateX(14px);
    background: var(--bg);
  }

  .notation-table {
    font-family: 'IBM Plex Mono', monospace;
    font-size: 11px;
    color: var(--text-muted);
    line-height: 1.7;
  }

  .notation-table .mono { color: var(--text); }

  .sequence-input {
    width: 100%;
    background: var(--bg-elevated);
    border: 1px solid var(--border);
    color: var(--text);
    font-family: 'IBM Plex Mono', monospace;
    font-size: 14px;
    padding: 10px 12px;
    border-radius: 4px;
    resize: vertical;
    min-height: 60px;
    margin-bottom: 6px;
    outline: none;
    transition: border-color 0.15s;
  }

  .sequence-input:focus {
    border-color: var(--accent);
  }

  .sequence-input::placeholder {
    color: var(--text-muted);
    font-style: italic;
  }

  .sequence-hint {
    font-size: 11px;
    color: var(--text-muted);
    font-family: 'Fraunces', serif;
    font-style: italic;
    margin-top: 4px;
    line-height: 1.4;
  }

  .sequence-error {
    font-size: 11px;
    color: var(--danger);
    margin-top: 4px;
    font-family: 'IBM Plex Mono', monospace;
  }

  /* Labels rendered as HTML (CSS2D-style, simple overlay approach) */
  #labels-layer {
    position: absolute;
    inset: 0;
    pointer-events: none;
    overflow: hidden;
  }

  .cubie-label {
    position: absolute;
    transform: translate(-50%, -50%);
    font-family: 'IBM Plex Mono', monospace;
    font-size: 10px;
    font-weight: 600;
    color: #1a1a1a;
    background: rgba(255, 255, 255, 0.85);
    padding: 1px 4px;
    border-radius: 2px;
    letter-spacing: 0.03em;
    pointer-events: none;
    white-space: nowrap;
    box-shadow: 0 1px 2px rgba(0,0,0,0.3);
  }

  .cubie-label.cubicle {
    color: var(--accent);
    background: rgba(15, 17, 21, 0.9);
    border: 1px solid var(--accent-dim);
  }

  /* Responsive */
  @media (max-width: 980px) {
    #app {
      grid-template-columns: 1fr;
      grid-template-rows: auto 1fr auto;
    }
    #left-panel, #right-panel {
      border: none;
      border-bottom: 1px solid var(--border);
      max-height: 40vh;
    }
    #right-panel {
      border-top: 1px solid var(--border);
      border-bottom: none;
    }
  }
</style>
</head>
<body>
<div id="app">

  <!-- LEFT PANEL -->
  <aside id="left-panel">
    <div>
      <h1 class="panel-header">Rubiks Terning</h1>
      <div class="panel-subtitle">Singmaster-notation · interaktiv</div>
    </div>

    <div>
      <span class="section-label">Træk — med uret</span>
      <div class="move-grid">
        <button class="move-btn" data-move="U" data-face="U" title="Op med uret"><span class="face-dot"></span>U</button>
        <button class="move-btn" data-move="U'" data-face="U" title="Op mod uret"><span class="face-dot"></span>U′</button>
        <button class="move-btn" data-move="D" data-face="D" title="Ned med uret"><span class="face-dot"></span>D</button>
        <button class="move-btn" data-move="D'" data-face="D" title="Ned mod uret"><span class="face-dot"></span>D′</button>
        <button class="move-btn" data-move="F" data-face="F" title="Front med uret"><span class="face-dot"></span>F</button>
        <button class="move-btn" data-move="F'" data-face="F" title="Front mod uret"><span class="face-dot"></span>F′</button>
        <button class="move-btn" data-move="B" data-face="B" title="Bag med uret"><span class="face-dot"></span>B</button>
        <button class="move-btn" data-move="B'" data-face="B" title="Bag mod uret"><span class="face-dot"></span>B′</button>
        <button class="move-btn" data-move="R" data-face="R" title="Højre med uret"><span class="face-dot"></span>R</button>
        <button class="move-btn" data-move="R'" data-face="R" title="Højre mod uret"><span class="face-dot"></span>R′</button>
        <button class="move-btn" data-move="L" data-face="L" title="Venstre med uret"><span class="face-dot"></span>L</button>
        <button class="move-btn" data-move="L'" data-face="L" title="Venstre mod uret"><span class="face-dot"></span>L′</button>
      </div>
    </div>

    <div>
      <span class="section-label">Handlinger</span>
      <button class="action-btn primary" id="btn-scramble">Bland (20 tilfældige træk)</button>
      <button class="action-btn" id="btn-reset">Nulstil til løst</button>
      <button class="action-btn" id="btn-undo">Fortryd sidste træk</button>
    </div>

    <div>
      <span class="section-label">Visning</span>
      <div class="toggles">
        <div class="toggle-row" id="toggle-cubie">
          <span>Vis cubie-navne</span>
          <div class="toggle-switch"></div>
        </div>
        <div class="toggle-row" id="toggle-cubicle">
          <span>Vis cubicle-navne</span>
          <div class="toggle-switch"></div>
        </div>
      </div>
    </div>
  </aside>

  <!-- CANVAS -->
  <main id="canvas-wrap">
    <div id="labels-layer"></div>
    <div id="canvas-hint">Træk kuben for at rotere en side · træk uden for for at dreje kameraet · scroll for zoom · tastatur: U L R F B D (shift for ′)</div>
  </main>

  <!-- RIGHT PANEL -->
  <aside id="right-panel">
    <div>
      <span class="section-label">Status</span>
      <div class="status-row"><span>Antal træk</span><strong id="move-count">0</strong></div>
      <div class="status-row"><span>Tilstand</span><strong id="solved-status">løst</strong></div>
    </div>

    <div>
      <span class="section-label">Sekvens-editor</span>
      <textarea class="sequence-input" id="sequence-input" rows="2" placeholder="R U R' U'  eller  F2 L B' D"></textarea>
      <button class="action-btn primary" id="btn-run-sequence">Kør sekvens</button>
      <div class="sequence-hint">Understøtter R, R′ (eller R'), R2. Bogstaver, mellemrum og apostrof.</div>
      <div class="sequence-error" id="sequence-error" style="display:none;"></div>
    </div>

    <div>
      <span class="section-label">Træksekvens</span>
      <div class="history-box empty" id="history">— ingen træk endnu —</div>
    </div>

    <div>
      <span class="section-label">Farveskema</span>
      <div class="legend">
        <div class="legend-item"><div class="legend-swatch" style="background:var(--face-u)"></div>u — up</div>
        <div class="legend-item"><div class="legend-swatch" style="background:var(--face-d)"></div>d — down</div>
        <div class="legend-item"><div class="legend-swatch" style="background:var(--face-f)"></div>f — front</div>
        <div class="legend-item"><div class="legend-swatch" style="background:var(--face-b)"></div>b — back</div>
        <div class="legend-item"><div class="legend-swatch" style="background:var(--face-r)"></div>r — right</div>
        <div class="legend-item"><div class="legend-swatch" style="background:var(--face-l)"></div>l — left</div>
      </div>
    </div>

    <div>
      <span class="section-label">Notation</span>
      <div class="notation-table">
        <div><span class="mono">urf, ufl, …</span> — 8 hjørne-cubies</div>
        <div><span class="mono">uf, ur, fr, …</span> — 12 kant-cubies</div>
        <div><span class="mono">u, d, f, …</span> — 6 center-cubies</div>
        <div style="margin-top: 8px;"><span class="mono">X′</span> — rotation mod uret</div>
        <div><span class="mono">X²</span> — halv omdrejning (ikke implementeret direkte)</div>
      </div>
    </div>
  </aside>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
  'use strict';

  // ------------------------------------------------------------------
  // Three.js setup
  // ------------------------------------------------------------------
  const canvasWrap = document.getElementById('canvas-wrap');
  const labelsLayer = document.getElementById('labels-layer');

  const scene = new THREE.Scene();
  scene.background = null; // transparent to show page background

  const camera = new THREE.PerspectiveCamera(
    45,
    canvasWrap.clientWidth / canvasWrap.clientHeight,
    0.1, 100
  );

  const renderer = new THREE.WebGLRenderer({ antialias: true, alpha: true });
  renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
  renderer.setSize(canvasWrap.clientWidth, canvasWrap.clientHeight);
  canvasWrap.appendChild(renderer.domElement);

  // Lighting
  const ambient = new THREE.AmbientLight(0xffffff, 0.65);
  scene.add(ambient);

  const keyLight = new THREE.DirectionalLight(0xffffff, 0.7);
  keyLight.position.set(5, 8, 5);
  scene.add(keyLight);

  const fillLight = new THREE.DirectionalLight(0xaabbdd, 0.3);
  fillLight.position.set(-5, -3, -5);
  scene.add(fillLight);

  // ------------------------------------------------------------------
  // Orbit controls (custom, simple spherical)
  // ------------------------------------------------------------------
  let camTheta = Math.PI * 0.2;   // azimuth (around y)
  let camPhi = Math.PI * 0.28;    // elevation from horizontal
  let camDist = 8.5;

  function updateCamera() {
    const cosPhi = Math.cos(camPhi);
    camera.position.x = camDist * Math.sin(camTheta) * cosPhi;
    camera.position.y = camDist * Math.sin(camPhi);
    camera.position.z = camDist * Math.cos(camTheta) * cosPhi;
    camera.lookAt(0, 0, 0);
  }
  updateCamera();

  // Interaction state machine:
  //   'idle'              — nothing happening
  //   'camera'            — dragging rotates the camera
  //   'face-drag-pending' — clicked a cubie, waiting for drag threshold
  //   'face-drag-done'    — already triggered a face move this drag
  let mouseState = 'idle';
  let dragStartX = 0, dragStartY = 0;
  let faceDrag = null;

  const canvas = renderer.domElement;
  const raycaster = new THREE.Raycaster();
  const ndc = new THREE.Vector2();

  function getNDC(clientX, clientY) {
    const rect = canvas.getBoundingClientRect();
    ndc.x = ((clientX - rect.left) / rect.width) * 2 - 1;
    ndc.y = -(((clientY - rect.top) / rect.height) * 2 - 1);
    return ndc;
  }

  function snapToAxis(vec) {
    // Returns {axis: 'x'|'y'|'z', sign: ±1} for the largest component.
    const ax = Math.abs(vec.x), ay = Math.abs(vec.y), az = Math.abs(vec.z);
    if (ax >= ay && ax >= az) return { axis: 'x', sign: Math.sign(vec.x) || 1 };
    if (ay >= az) return { axis: 'y', sign: Math.sign(vec.y) || 1 };
    return { axis: 'z', sign: Math.sign(vec.z) || 1 };
  }

  function pointerDown(clientX, clientY) {
    if (animating) {
      // If an animation is in progress, just allow camera rotation
      mouseState = 'camera';
      dragStartX = clientX;
      dragStartY = clientY;
      return;
    }

    // Raycast against cubies
    raycaster.setFromCamera(getNDC(clientX, clientY), camera);
    const meshes = cubies.map(c => c.mesh);
    const hits = raycaster.intersectObjects(meshes, false);

    if (hits.length > 0) {
      const hit = hits[0];
      const cubie = cubies.find(c => c.mesh === hit.object);

      // Local face normal → world direction
      const worldNormal = hit.face.normal.clone().transformDirection(hit.object.matrixWorld);
      const snapped = snapToAxis(worldNormal);

      // Only accept clicks on outward-facing stickers (ones at max in that axis).
      // This avoids weird behavior on interior-facing black faces.
      const cubiePos = cubie.mesh.position;
      const faceCoord = Math.round(cubiePos[snapped.axis]);
      if (faceCoord !== snapped.sign) {
        mouseState = 'camera';
        dragStartX = clientX;
        dragStartY = clientY;
        return;
      }

      faceDrag = {
        cubie,
        faceNormalAxis: snapped.axis,
        faceNormalSign: snapped.sign,
        startPoint: hit.point.clone(),
        startX: clientX,
        startY: clientY
      };
      mouseState = 'face-drag-pending';
    } else {
      mouseState = 'camera';
      dragStartX = clientX;
      dragStartY = clientY;
    }
  }

  function pointerMove(clientX, clientY) {
    if (mouseState === 'camera') {
      const dx = clientX - dragStartX;
      const dy = clientY - dragStartY;
      camTheta -= dx * 0.008;
      camPhi += dy * 0.008;
      const lim = Math.PI / 2 - 0.05;
      camPhi = Math.max(-lim, Math.min(lim, camPhi));
      dragStartX = clientX;
      dragStartY = clientY;
      updateCamera();
    } else if (mouseState === 'face-drag-pending' && faceDrag) {
      const dx = clientX - faceDrag.startX;
      const dy = clientY - faceDrag.startY;
      if (dx * dx + dy * dy < 100) return; // ~10 pixels

      // Cast ray onto the face plane, find world-space drag vector
      raycaster.setFromCamera(getNDC(clientX, clientY), camera);
      const normalVec = new THREE.Vector3();
      normalVec[faceDrag.faceNormalAxis] = faceDrag.faceNormalSign;
      const plane = new THREE.Plane().setFromNormalAndCoplanarPoint(normalVec, faceDrag.startPoint);
      const currentPoint = new THREE.Vector3();
      if (!raycaster.ray.intersectPlane(plane, currentPoint)) return;

      const worldDrag = currentPoint.sub(faceDrag.startPoint);
      if (worldDrag.length() < 0.08) return;

      // Snap drag to best axis (excluding the face normal's axis)
      const candidates = ['x', 'y', 'z'].filter(a => a !== faceDrag.faceNormalAxis);
      let bestAxis = null, bestSign = 0, bestDot = -Infinity;
      for (const a of candidates) {
        for (const s of [-1, 1]) {
          const v = new THREE.Vector3();
          v[a] = s;
          const d = v.dot(worldDrag);
          if (d > bestDot) { bestDot = d; bestAxis = a; bestSign = s; }
        }
      }
      if (bestDot < 0.05) return;

      const dragDir = new THREE.Vector3();
      dragDir[bestAxis] = bestSign;

      // Rotation axis is the remaining axis
      const rotAxis = ['x', 'y', 'z'].find(a => a !== faceDrag.faceNormalAxis && a !== bestAxis);
      const pos = faceDrag.cubie.mesh.position;
      const layerValue = Math.round(pos[rotAxis]);

      // Skip middle slices (basic moves only)
      if (layerValue === 0) {
        mouseState = 'face-drag-done';
        return;
      }

      // Determine rotation sign: sign of (A × p) · d
      const A = new THREE.Vector3();
      A[rotAxis] = 1;
      const cross = new THREE.Vector3().crossVectors(A, pos);
      const rotSign = Math.sign(cross.dot(dragDir));

      // Map to face move
      const faceMap = {
        'x:1': 'R', 'x:-1': 'L',
        'y:1': 'U', 'y:-1': 'D',
        'z:1': 'F', 'z:-1': 'B'
      };
      const faceLetter = faceMap[rotAxis + ':' + layerValue];
      if (!faceLetter) { mouseState = 'face-drag-done'; return; }

      const cfg = FACE_CONFIG[faceLetter];
      // Applied rotation is rotSign * π/2 around +rotAxis.
      // The face's "CW" (no-prime) move is cfg.cwSign * π/2.
      const move = faceLetter + (rotSign === cfg.cwSign ? '' : "'");
      enqueueMove(move);
      mouseState = 'face-drag-done';
    }
  }

  function pointerUp() {
    mouseState = 'idle';
    faceDrag = null;
  }

  canvas.addEventListener('mousedown', e => pointerDown(e.clientX, e.clientY));
  window.addEventListener('mousemove', e => pointerMove(e.clientX, e.clientY));
  window.addEventListener('mouseup', pointerUp);

  canvas.addEventListener('touchstart', e => {
    if (e.touches.length === 1) pointerDown(e.touches[0].clientX, e.touches[0].clientY);
  }, { passive: true });
  canvas.addEventListener('touchmove', e => {
    if (e.touches.length === 1) pointerMove(e.touches[0].clientX, e.touches[0].clientY);
  }, { passive: true });
  canvas.addEventListener('touchend', pointerUp);

  canvas.addEventListener('wheel', e => {
    e.preventDefault();
    camDist = Math.max(4, Math.min(20, camDist + e.deltaY * 0.01));
    updateCamera();
  }, { passive: false });

  // ------------------------------------------------------------------
  // Cube construction
  // ------------------------------------------------------------------
  const COLORS = {
    u: 0xf5f5f0,
    d: 0xf5c518,
    f: 0x1fa347,
    b: 0x1658c2,
    r: 0xc12e1f,
    l: 0xe87a1a,
    inside: 0x1a1a1a
  };

  const CUBIE_SIZE = 0.96;
  const CUBIE_SPACING = 1.0; // distance between cubie centers

  // Cubie group (holds all 26 visible cubies)
  const cubeGroup = new THREE.Group();
  scene.add(cubeGroup);

  // Each cubie stores:
  // - mesh (THREE.Mesh)
  // - canonicalName (original cubie name, used as identifier)
  // - type ('corner' | 'edge' | 'center')
  const cubies = [];

  // Map from (x,y,z) position to canonical cubie name
  // Convention for corners: listed u/d first, then clockwise viewed from outside
  function cubieNameFromPos(x, y, z) {
    const ax = Math.abs(x) > 0.5 ? 1 : 0;
    const ay = Math.abs(y) > 0.5 ? 1 : 0;
    const az = Math.abs(z) > 0.5 ? 1 : 0;
    const count = ax + ay + az;
    if (count === 0) return null; // invisible center

    if (count === 1) {
      // Center cubie
      if (y > 0.5) return 'u';
      if (y < -0.5) return 'd';
      if (z > 0.5) return 'f';
      if (z < -0.5) return 'b';
      if (x > 0.5) return 'r';
      return 'l';
    }

    if (count === 2) {
      // Edge cubie: order u/d, f/b, r/l
      let s = '';
      if (y > 0.5) s += 'u'; else if (y < -0.5) s += 'd';
      if (z > 0.5) s += 'f'; else if (z < -0.5) s += 'b';
      if (x > 0.5) s += 'r'; else if (x < -0.5) s += 'l';
      return s;
    }

    // Corner cubie — hardcoded canonical form per position
    const key = `${x},${y},${z}`;
    const corners = {
      '1,1,1': 'urf',   '-1,1,1': 'ufl',  '-1,1,-1': 'ulb',  '1,1,-1': 'ubr',
      '1,-1,1': 'dfr',  '-1,-1,1': 'dlf', '-1,-1,-1': 'dbl', '1,-1,-1': 'drb'
    };
    return corners[key];
  }

  function cubieTypeFromPos(x, y, z) {
    const n = (Math.abs(x) > 0.5 ? 1 : 0) + (Math.abs(y) > 0.5 ? 1 : 0) + (Math.abs(z) > 0.5 ? 1 : 0);
    if (n === 3) return 'corner';
    if (n === 2) return 'edge';
    if (n === 1) return 'center';
    return null;
  }

  function createCubieMesh(x, y, z) {
    const geo = new THREE.BoxGeometry(CUBIE_SIZE, CUBIE_SIZE, CUBIE_SIZE);

    // BoxGeometry material order: [+x, -x, +y, -y, +z, -z]
    const mats = [
      new THREE.MeshStandardMaterial({ color: x > 0.5 ? COLORS.r : COLORS.inside, roughness: 0.45, metalness: 0.05 }),
      new THREE.MeshStandardMaterial({ color: x < -0.5 ? COLORS.l : COLORS.inside, roughness: 0.45, metalness: 0.05 }),
      new THREE.MeshStandardMaterial({ color: y > 0.5 ? COLORS.u : COLORS.inside, roughness: 0.45, metalness: 0.05 }),
      new THREE.MeshStandardMaterial({ color: y < -0.5 ? COLORS.d : COLORS.inside, roughness: 0.45, metalness: 0.05 }),
      new THREE.MeshStandardMaterial({ color: z > 0.5 ? COLORS.f : COLORS.inside, roughness: 0.45, metalness: 0.05 }),
      new THREE.MeshStandardMaterial({ color: z < -0.5 ? COLORS.b : COLORS.inside, roughness: 0.45, metalness: 0.05 })
    ];

    const mesh = new THREE.Mesh(geo, mats);
    mesh.position.set(x * CUBIE_SPACING, y * CUBIE_SPACING, z * CUBIE_SPACING);

    // Rounded-look edge highlight: add slightly smaller black outline via EdgesGeometry
    const edges = new THREE.EdgesGeometry(geo);
    const line = new THREE.LineSegments(
      edges,
      new THREE.LineBasicMaterial({ color: 0x0a0a0a, linewidth: 1 })
    );
    mesh.add(line);

    return mesh;
  }

  // Build 27 cubies (skip the inner 0,0,0)
  for (let x = -1; x <= 1; x++) {
    for (let y = -1; y <= 1; y++) {
      for (let z = -1; z <= 1; z++) {
        if (x === 0 && y === 0 && z === 0) continue;
        const mesh = createCubieMesh(x, y, z);
        cubeGroup.add(mesh);
        cubies.push({
          mesh,
          canonicalName: cubieNameFromPos(x, y, z),
          type: cubieTypeFromPos(x, y, z),
          // Position used for label direction (outward from origin). Will update after moves.
          outwardOffset: new THREE.Vector3(x, y, z).normalize()
        });
      }
    }
  }

  // ------------------------------------------------------------------
  // Move logic
  // ------------------------------------------------------------------
  const FACE_CONFIG = {
    U: { axis: 'y', layer:  1, cwSign: -1 }, // clockwise from +y view = negative rotation around y
    D: { axis: 'y', layer: -1, cwSign:  1 },
    R: { axis: 'x', layer:  1, cwSign: -1 },
    L: { axis: 'x', layer: -1, cwSign:  1 },
    F: { axis: 'z', layer:  1, cwSign: -1 },
    B: { axis: 'z', layer: -1, cwSign:  1 }
  };

  let animating = false;
  const moveQueue = [];
  const history = [];

  function enqueueMove(move) {
    moveQueue.push(move);
    processQueue();
  }

  function processQueue() {
    if (animating || moveQueue.length === 0) return;
    const move = moveQueue.shift();
    performMove(move);
  }

  function performMove(move) {
    // move is e.g. "U" or "U'"
    const face = move[0];
    const prime = move.length > 1 && move[1] === "'";
    const cfg = FACE_CONFIG[face];
    if (!cfg) return;

    animating = true;
    setButtonsDisabled(true);

    // Find cubies on that layer based on current world position
    const affected = cubies.filter(c => {
      const p = c.mesh.position;
      return Math.round(p[cfg.axis]) === cfg.layer;
    });

    const pivot = new THREE.Group();
    scene.add(pivot);
    affected.forEach(c => pivot.attach(c.mesh));

    const targetAngle = cfg.cwSign * (prime ? -1 : 1) * (Math.PI / 2);
    const duration = 280;
    const startTime = performance.now();

    function step(now) {
      const t = Math.min((now - startTime) / duration, 1);
      const e = t < 0.5 ? 2 * t * t : 1 - Math.pow(-2 * t + 2, 2) / 2;
      pivot.rotation[cfg.axis] = targetAngle * e;
      if (t < 1) {
        requestAnimationFrame(step);
      } else {
        pivot.rotation[cfg.axis] = targetAngle;
        pivot.updateMatrixWorld();

        // Reparent cubies back to cubeGroup preserving world transforms
        affected.forEach(c => cubeGroup.attach(c.mesh));

        // Snap positions to integer grid (world)
        affected.forEach(c => {
          c.mesh.position.x = Math.round(c.mesh.position.x);
          c.mesh.position.y = Math.round(c.mesh.position.y);
          c.mesh.position.z = Math.round(c.mesh.position.z);
        });

        scene.remove(pivot);

        // Record history
        history.push(move);
        updateHistoryUI();
        updateSolvedStatus();

        animating = false;
        setButtonsDisabled(false);
        processQueue();
      }
    }
    requestAnimationFrame(step);
  }

  // ------------------------------------------------------------------
  // Buttons + keyboard
  // ------------------------------------------------------------------
  const moveButtons = document.querySelectorAll('.move-btn');
  moveButtons.forEach(btn => {
    btn.addEventListener('click', () => {
      enqueueMove(btn.dataset.move);
    });
  });

  function setButtonsDisabled(d) {
    moveButtons.forEach(b => b.disabled = d);
  }

  window.addEventListener('keydown', e => {
    const k = e.key.toUpperCase();
    if ('ULRFDB'.indexOf(k) === -1) return;
    if (['INPUT', 'TEXTAREA'].includes((e.target.tagName || '').toUpperCase())) return;
    enqueueMove(k + (e.shiftKey ? "'" : ''));
  });

  // Reset
  document.getElementById('btn-reset').addEventListener('click', () => {
    if (animating) return;
    moveQueue.length = 0;
    // Rebuild: remove all cubies and recreate
    cubies.forEach(c => cubeGroup.remove(c.mesh));
    cubies.length = 0;

    for (let x = -1; x <= 1; x++) {
      for (let y = -1; y <= 1; y++) {
        for (let z = -1; z <= 1; z++) {
          if (x === 0 && y === 0 && z === 0) continue;
          const mesh = createCubieMesh(x, y, z);
          cubeGroup.add(mesh);
          cubies.push({
            mesh,
            canonicalName: cubieNameFromPos(x, y, z),
            type: cubieTypeFromPos(x, y, z),
            outwardOffset: new THREE.Vector3(x, y, z).normalize()
          });
        }
      }
    }

    history.length = 0;
    updateHistoryUI();
    updateSolvedStatus();
    rebuildLabels();
  });

  // Undo
  document.getElementById('btn-undo').addEventListener('click', () => {
    if (animating || history.length === 0) return;
    const last = history.pop();
    // Do the inverse
    const inv = last.endsWith("'") ? last[0] : last[0] + "'";
    // But pop again so we don't double-count: performMove will push again.
    // We'll push a special flag: just do move without adding to history
    const face = inv[0];
    const prime = inv.length > 1 && inv[1] === "'";
    const cfg = FACE_CONFIG[face];

    animating = true;
    setButtonsDisabled(true);

    const affected = cubies.filter(c => {
      const p = c.mesh.position;
      return Math.round(p[cfg.axis]) === cfg.layer;
    });

    const pivot = new THREE.Group();
    scene.add(pivot);
    affected.forEach(c => pivot.attach(c.mesh));

    const targetAngle = cfg.cwSign * (prime ? -1 : 1) * (Math.PI / 2);
    const duration = 220;
    const startTime = performance.now();

    function step(now) {
      const t = Math.min((now - startTime) / duration, 1);
      const e = t < 0.5 ? 2 * t * t : 1 - Math.pow(-2 * t + 2, 2) / 2;
      pivot.rotation[cfg.axis] = targetAngle * e;
      if (t < 1) {
        requestAnimationFrame(step);
      } else {
        pivot.rotation[cfg.axis] = targetAngle;
        pivot.updateMatrixWorld();
        affected.forEach(c => cubeGroup.attach(c.mesh));
        affected.forEach(c => {
          c.mesh.position.x = Math.round(c.mesh.position.x);
          c.mesh.position.y = Math.round(c.mesh.position.y);
          c.mesh.position.z = Math.round(c.mesh.position.z);
        });
        scene.remove(pivot);
        updateHistoryUI();
        updateSolvedStatus();
        animating = false;
        setButtonsDisabled(false);
      }
    }
    requestAnimationFrame(step);
  });

  // Scramble
  document.getElementById('btn-scramble').addEventListener('click', () => {
    const faces = ['U','D','F','B','L','R'];
    let last = '';
    for (let i = 0; i < 20; i++) {
      let f;
      do { f = faces[Math.floor(Math.random() * 6)]; } while (f === last);
      last = f;
      const m = f + (Math.random() < 0.5 ? '' : "'");
      enqueueMove(m);
    }
  });

  // ------------------------------------------------------------------
  // Sequence editor
  // ------------------------------------------------------------------
  function parseSequence(text) {
    // Valid tokens: R, R', R′, R2   (case-insensitive)
    const cleaned = text.replace(/\s+/g, ' ').trim();
    if (!cleaned) return { moves: [], error: null };

    const re = /([RLUDFBrludfb])(['′]|2)?/gy;
    const moves = [];
    let pos = 0;
    while (pos < cleaned.length) {
      // Skip whitespace
      if (cleaned[pos] === ' ') { pos++; continue; }
      re.lastIndex = pos;
      const m = re.exec(cleaned);
      if (!m || m.index !== pos) {
        return { moves: [], error: `Kunne ikke tolke ved position ${pos + 1}: "${cleaned.slice(pos, pos + 4)}…"` };
      }
      const face = m[1].toUpperCase();
      const mod = m[2];
      if (mod === '2') {
        moves.push(face);
        moves.push(face);
      } else if (mod === "'" || mod === '′') {
        moves.push(face + "'");
      } else {
        moves.push(face);
      }
      pos = re.lastIndex;
    }
    return { moves, error: null };
  }

  const sequenceInput = document.getElementById('sequence-input');
  const sequenceError = document.getElementById('sequence-error');

  function showSequenceError(msg) {
    if (msg) {
      sequenceError.textContent = msg;
      sequenceError.style.display = '';
    } else {
      sequenceError.style.display = 'none';
    }
  }

  document.getElementById('btn-run-sequence').addEventListener('click', () => {
    const { moves, error } = parseSequence(sequenceInput.value);
    if (error) {
      showSequenceError(error);
      return;
    }
    if (moves.length === 0) {
      showSequenceError('Ingen træk i sekvensen.');
      return;
    }
    showSequenceError(null);
    moves.forEach(enqueueMove);
  });

  // Ctrl/Cmd+Enter runs sequence
  sequenceInput.addEventListener('keydown', e => {
    if (e.key === 'Enter' && (e.ctrlKey || e.metaKey)) {
      e.preventDefault();
      document.getElementById('btn-run-sequence').click();
    }
  });

  // ------------------------------------------------------------------
  // Toggles for labels
  // ------------------------------------------------------------------
  let showCubieNames = false;
  let showCubicleNames = false;

  const toggleCubie = document.getElementById('toggle-cubie');
  const toggleCubicle = document.getElementById('toggle-cubicle');

  toggleCubie.addEventListener('click', () => {
    showCubieNames = !showCubieNames;
    toggleCubie.classList.toggle('active', showCubieNames);
    rebuildLabels();
  });
  toggleCubicle.addEventListener('click', () => {
    showCubicleNames = !showCubicleNames;
    toggleCubicle.classList.toggle('active', showCubicleNames);
    rebuildLabels();
  });

  // Labels: we manage our own DOM elements projected from 3D coords.
  // Two types:
  //  - cubie labels: attached to cubies (move with them), use canonicalName
  //  - cubicle labels: fixed in world space at grid positions, use position-derived name

  const labelObjects = []; // { el, worldPos: function -> Vector3 }

  function rebuildLabels() {
    labelObjects.forEach(l => l.el.remove());
    labelObjects.length = 0;

    if (showCubieNames) {
      cubies.forEach(c => {
        if (!c.canonicalName) return;
        const el = document.createElement('div');
        el.className = 'cubie-label';
        el.textContent = c.canonicalName;
        labelsLayer.appendChild(el);
        labelObjects.push({
          el,
          worldPos: () => {
            // Outward direction from cube center to cubie's CURRENT position
            const pos = c.mesh.position.clone();
            const outward = pos.clone().normalize().multiplyScalar(0.8);
            return pos.add(outward);
          }
        });
      });
    }

    if (showCubicleNames) {
      // Fixed cubicle labels: one per visible position in the 3x3x3 grid
      for (let x = -1; x <= 1; x++) {
        for (let y = -1; y <= 1; y++) {
          for (let z = -1; z <= 1; z++) {
            const name = cubieNameFromPos(x, y, z);
            if (!name) continue;
            const el = document.createElement('div');
            el.className = 'cubie-label cubicle';
            el.textContent = name.toUpperCase();
            labelsLayer.appendChild(el);
            const outward = new THREE.Vector3(x, y, z).normalize().multiplyScalar(1.95);
            labelObjects.push({
              el,
              worldPos: () => outward.clone()
            });
          }
        }
      }
    }
  }

  function updateLabelsPositions() {
    if (labelObjects.length === 0) return;
    const rect = canvasWrap.getBoundingClientRect();
    const w = rect.width, h = rect.height;
    const camDir = camera.position.clone().normalize();
    labelObjects.forEach(l => {
      const p = l.worldPos();
      // Hide labels on the far side of the cube (behind from camera's view)
      const outwardDir = p.clone().normalize();
      const facing = outwardDir.dot(camDir);
      if (facing < 0.05) {
        l.el.style.display = 'none';
        return;
      }
      const proj = p.clone().project(camera);
      if (proj.z > 1 || proj.z < -1) {
        l.el.style.display = 'none';
        return;
      }
      const sx = (proj.x * 0.5 + 0.5) * w;
      const sy = (-proj.y * 0.5 + 0.5) * h;
      l.el.style.display = '';
      l.el.style.opacity = Math.min(1, facing * 3);
      l.el.style.left = sx + 'px';
      l.el.style.top = sy + 'px';
    });
  }

  // ------------------------------------------------------------------
  // Status / history UI
  // ------------------------------------------------------------------
  const historyEl = document.getElementById('history');
  const moveCountEl = document.getElementById('move-count');
  const solvedStatusEl = document.getElementById('solved-status');

  function updateHistoryUI() {
    moveCountEl.textContent = history.length;
    if (history.length === 0) {
      historyEl.classList.add('empty');
      historyEl.textContent = '— ingen træk endnu —';
    } else {
      historyEl.classList.remove('empty');
      historyEl.innerHTML = history
        .map(m => `<span class="history-move">${m.replace("'", '′')}</span>`)
        .join(' ');
      historyEl.scrollTop = historyEl.scrollHeight;
    }
  }

  function isSolved() {
    const canonicalPos = new Map();
    for (let x = -1; x <= 1; x++) {
      for (let y = -1; y <= 1; y++) {
        for (let z = -1; z <= 1; z++) {
          const n = cubieNameFromPos(x, y, z);
          if (n) canonicalPos.set(n, new THREE.Vector3(x, y, z));
        }
      }
    }
    const testX = new THREE.Vector3();
    const testY = new THREE.Vector3();
    for (const c of cubies) {
      const target = canonicalPos.get(c.canonicalName);
      if (!target) continue;
      const p = c.mesh.position;
      if (Math.round(p.x) !== target.x || Math.round(p.y) !== target.y || Math.round(p.z) !== target.z) {
        return false;
      }
      // Check orientation: local +x and +y must still point along world +x and +y
      testX.set(1, 0, 0).applyQuaternion(c.mesh.quaternion);
      testY.set(0, 1, 0).applyQuaternion(c.mesh.quaternion);
      if (Math.abs(testX.x - 1) > 0.02 || Math.abs(testY.y - 1) > 0.02) {
        return false;
      }
    }
    return true;
  }

  function updateSolvedStatus() {
    solvedStatusEl.textContent = isSolved() ? 'løst' : 'blandet';
    solvedStatusEl.style.color = isSolved() ? 'var(--face-f)' : 'var(--accent)';
  }

  // ------------------------------------------------------------------
  // Resize
  // ------------------------------------------------------------------
  function onResize() {
    const w = canvasWrap.clientWidth;
    const h = canvasWrap.clientHeight;
    camera.aspect = w / h;
    camera.updateProjectionMatrix();
    renderer.setSize(w, h);
  }
  window.addEventListener('resize', onResize);

  // ------------------------------------------------------------------
  // Render loop
  // ------------------------------------------------------------------
  function render() {
    renderer.render(scene, camera);
    updateLabelsPositions();
    requestAnimationFrame(render);
  }
  render();

  // Initial UI state
  updateHistoryUI();
  updateSolvedStatus();
  rebuildLabels();
</script>
</body>
</html>
