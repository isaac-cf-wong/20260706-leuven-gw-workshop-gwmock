## Today: the whole toolbox

<div class="two-col">
  <div>
    <ul>
      <li><strong>Orchestrated</strong> — YAML + CLI: population → signal → noise → frames, hashed and reproducible. The MDC workflow.</li>
      <li><strong>À la carte</strong> — each engine is a Python library:
        <ul>
          <li><code>gwmock-pop</code>: graph-based population models (GWTC-4 preset, swappable priors)</li>
          <li><code>gwmock-signal</code>: waveform → projection → injection, custom models, SGWB</li>
          <li><code>gwmock-noise</code>: ET sensitivity curves, lines, glitches, streaming</li>
        </ul>
      </li>
    </ul>
  </div>
  <div>
    <h3>The habit to take home</h3>
    <p><strong>Anchor what you generate.</strong> Every notebook checks the output against something independent:</p>
    <ul>
      <li>merged strain ASD ↔ the input ET sensitivity curve</li>
      <li>SGWB PSD ↔ $S_h(f) = \frac{3 H_0^2}{10\pi^2}\frac{\Omega_{\rm GW}(f)}{f^3}$</li>
      <li>replayed run ↔ bit-identical to the original</li>
    </ul>
    <p class="takeaway">Simulated data you can defend.</p>
  </div>
</div>

Notes:

- contrast with the June SGWB session: that was one deep dive; today is the
  general, comprehensive tour — SGWB is one stop near the end
- the anchor theme: mock data is only useful if you can show it's right; the
  notebooks bake the checks in
- ~1.5 min
