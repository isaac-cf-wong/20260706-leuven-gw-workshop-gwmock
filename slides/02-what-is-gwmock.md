## What is gwmock?

<div class="two-col">
  <div>
    <ul>
      <li>A Python package that generates <strong>Mock Data Challenge (MDC)</strong> datasets for GW detectors — built for the <strong>Einstein Telescope</strong>, usable beyond it.</li>
      <li>One YAML config → detector <strong>strain</strong>: population + signals + noise, written as standard <strong>GWF / HDF5</strong> frames.</li>
      <li>Every run ships a <strong>metadata sidecar</strong> — versions, seeds, file hashes — so results are <strong>reproducible</strong> and <strong>verifiable</strong>.</li>
      <li>Driven by a small <strong>CLI</strong>; scales from a laptop to a Slurm cluster; publishes to Zenodo.</li>
    </ul>
    <p class="takeaway">Trustworthy, reproducible mock GW data from a single config.</p>
  </div>
  <div>
    <h3>One framework, three engines</h3>
    <div class="engine-list">
      <div><strong>gwmock-pop</strong><br/>source populations (BBH/BNS/NSBH)</div>
      <div><strong>gwmock-signal</strong><br/>waveforms, projection &amp; the SGWB</div>
      <div><strong>gwmock-noise</strong><br/>coloured &amp; correlated noise, lines, glitches</div>
    </div>
    <p class="muted" style="margin-top:0.8em"><code>pip install "gwmock[sgwb]"</code> · Python 3.12–3.14 · GPL-3.0 · <a href="https://leuven-gravity-institute.github.io/gwmock">docs</a></p>
    <p class="benchmark-note">Share performance results: <a href="https://github.com/Leuven-Gravity-Institute/gwmock-benchmark">gwmock-benchmark</a></p>
  </div>
</div>

Notes:

- one-line orientation: config in, detector strain + provenance out
- unlike the SGWB session in June, today we tour the WHOLE toolbox — each engine
  is also a standalone Python library, and we'll use all three directly
- emphasise reproducibility + verification; that's the MDC value
- briefly advertise gwmock-benchmark for community runtime/hardware results
- ~1.5 min
