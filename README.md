# sony-duelist-composer

Lightning-fast duet line generator for human–AI counterpoint.

## What this is

A tiny engine that simulates an 8-bar “duel” between a Human and an AI using 5 musical moves: 
**Consonant, Dissonant, Modulate, Rhythm Shift, Silence.**  
Each bar gets a score from a simple payoff table (tension vs. release).  
Goal: short arcs that feel alive, then resolve.

## Quick start

Requires Python 3.9+ (no other installs needed).

```bash
python duel.py
```

## Sample output

```
Bar 1: Human=Consonant, AI=Dissonant, Score=2
Bar 2: Human=Rhythm Shift, AI=Consonant, Score=2
Bar 3: Human=Silence, AI=Modulate, Score=1
Bar 4: Human=Consonant, AI=Consonant, Score=3  # cadence bonus
Bar 5: Human=Dissonant, AI=Consonant, Score=2
Bar 6: Human=Rhythm Shift, AI=Silence, Score=1
Bar 7: Human=Modulate, AI=Dissonant, Score=1
Bar 8: Human=Consonant, AI=Consonant, Score=3  # cadence bonus
Final Score: 15
```

## How it works (short)

- Picks Human + AI moves each bar.  
- Scores with a tiny payoff matrix.  
- Adds a **cadence bonus** on bars 4 and 8 if both land Consonant.  
- Prints the bar-by-bar story and total score.  

## Examples

A sample run of the Human–AI duel is included in this repo.  
You can view the output here: [examples/duel_output.txt](examples/duel_output.txt)

This file demonstrates how the program plays out bar by bar, showing both the Human and AI moves, along with the score calculation.

Example snippet:

```
Bar 1: Human=Consonant, AI=Dissonant, Score=2
Bar 2: Human=Rhythm Shift, AI=Consonant, Score=2
Bar 3: Human=Silence, AI=Modulate, Score=1
...
Final Score: 15
```

This makes it easy to verify that the system is running correctly and producing results.

## Roadmap

- [x] v0: random duel with payoff + cadence bonus  
- [ ] v1: avoid same move >2x in a row (variety)  
- [ ] v2: basic “learning” (prefer release after tension)  
- [ ] v3: export to MIDI (`music21` or `MIDIUtil`)  
- [ ] v4: multi-agent quartet (piano/violin/percussion AIs)  
