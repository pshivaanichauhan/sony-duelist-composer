# sony-duelist-composer 🎼  
Lightning-fast duet line generator for human–AI counterpoint.

## What this is
A tiny engine that simulates an 8-bar “duel” between a Human and an AI using 5 musical moves:  

- **Consonant**  
- **Dissonant**  
- **Modulate**  
- **Rhythm Shift**  
- **Silence**  

Each bar gets a score from a simple payoff table (tension vs. release).  
**Goal:** short arcs that feel alive, then resolve.

---

## Quick start
Requires **Python 3.9+** (no other installs needed).

```bash
python duel.py
```

This will print Human + AI moves bar by bar with scores.

---

## Example output
A sample run is included: [examples/duel_output.txt](examples/duel_output.txt)

Snippet:
```
Bar 1: Human=Consonant, AI=Dissonant, Score=2
Bar 2: Human=Rhythm Shift, AI=Consonant, Score=2
Bar 3: Human=Silence, AI=Modulate, Score=1
...
Final Score: 15
```

---

## Run Guide

### 1. Requirements
- Python 3.9 or higher  
- No additional libraries needed for the basic duel  

Optional (for testing/extensions):
```bash
pip install -r requirements.txt
```

### 2. Running the Duel
Run a default 8-bar duel:
```bash
python duel.py
```

### 3. Viewing Example Output
Open the included file:
```
examples/duel_output.txt
```

### 4. Running Tests
Check that scoring works correctly:
```bash
pytest test_scoring.py
```

### 5. Command-Line Interface (CLI)
Run with custom options:
```bash
python cli.py --bars 8 --save examples/output.txt
```

---

## Listen (MIDI Export 🚀)
*Coming soon*  
- Export duels to **MIDI files** (so you can hear the generated music).  
- Planned libraries: `mido` or `MIDIUtil`.  

---

## Roadmap
- [x] v0: random duel with payoff + cadence bonus  
- [ ] v1: avoid same move >2× in a row (variety)  
- [ ] v2: basic *learning* (prefer release after tension)  
- [ ] v3: export to MIDI (`mido` or `MIDIUtil`)  
- [ ] v4: multi-agent quartet (piano/violin/percussion AIs)  

---

## License
MIT License
