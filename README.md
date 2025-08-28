# sony-duelist-composer 🎼

Lightning-fast duet line generator for human–AI counterpoint.  
Simulates an 8-bar “duel” between a Human and an AI using 5 musical moves.

---

## What this is
A tiny engine that creates duets bar-by-bar using the following moves:

- **Consonant**
- **Dissonant**
- **Modulate**
- **Rhythm Shift**
- **Silence**

Each bar gets a score from a simple payoff table (tension vs. release).  
Goal: short arcs that feel alive, then resolve.

---

## Quick start

Requires **Python 3.9+** (no extra installs needed).

```bash
python duel.py
```

---

## Sample output

```
Bar 1: Human=Consonant, AI=Dissonant, Score=2
Bar 2: Human=Rhythm Shift, AI=Consonant, Score=2
Bar 3: Human=Silence, AI=Modulate, Score=1
Bar 4: Human=Consonant, AI=Consonant, Score=3   # cadence bonus
Bar 5: Human=Dissonant, AI=Consonant, Score=2
Bar 6: Human=Rhythm Shift, AI=Silence, Score=1
Bar 7: Human=Modulate, AI=Dissonant, Score=1
Bar 8: Human=Consonant, AI=Consonant, Score=3   # cadence bonus
Final Score: 15
```

---

## How it works (short)

- Picks Human + AI moves each bar.  
- Scores with a tiny payoff matrix.  
- Adds a **cadence bonus** on bars 4 and 8 if both land Consonant.  
- Prints the bar-by-bar story and total score.  

---

## Examples

A sample run of the Human–AI duel is included:  
👉 [`examples/duel_output.txt`](examples/duel_output.txt)

This file shows both the Human and AI moves, along with the score calculation.  

Example snippet:

```
Bar 1: Human=Consonant, AI=Dissonant, Score=2
Bar 2: Human=Rhythm Shift, AI=Consonant, Score=2
Bar 3: Human=Silence, AI=Modulate, Score=1
...
Final Score: 15
```

---

## Listen (MIDI Export)

Coming soon:  
- Export duels to **MIDI files** (so you can actually hear the generated music).  
- Planned libraries: `mido` or `MIDIUtil`.  

---

## Run Guide

To run tests:

```bash
pytest test_scoring.py
```

To use the command-line interface (CLI):

```bash
python cli.py --bars 8 --save examples/output.txt
```

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
