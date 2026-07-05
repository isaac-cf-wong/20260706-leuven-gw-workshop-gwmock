## gwmock at a glance

<div class="two-col">
  <div>
    <h3>A config is two blocks</h3>

```yaml
globals: # rate, duration, start, seed, paths
orchestration:
    population: # the event catalogue
    signal: # detectors, waveform / SGWB
    noise: # the noise model
```

  </div>
  <div>
    <h3>The commands you'll use</h3>

```bash
gwmock config --list          # browse examples
gwmock config --interactive   # TUI config editor
gwmock simulate config.yaml   # generate data
gwmock validate  …            # check hashes
gwmock merge     …            # signal + noise
```

  </div>
</div>

<p class="takeaway">That's the whole mental model — we'll fill it in live in the notebooks.</p>

Notes:

- this is orientation, not a tutorial — just so the notebooks aren't a cold
  start
- any section of orchestration can be omitted: noise-only, signal-only, or both
- optional live demo: `gwmock config --interactive` in a terminal — build the
  notebook-01 config with `/template noise` + `/noise psd …` + `/save`; 60 s,
  lands well; notebook 01 §6 has the command table for attendees
- don't read it out; point at the shape and move on (~40 s, +1 min with demo)
