# PHANTOM

## Interactive kinetic core

PHANTOM now defaults to the interactive kinetic core in the existing PyQt6 HUD. The renderer remains inside `Mark-LVI-main/Mark-LVI-main/ui.py` and uses the existing `HudCanvas` surface, so no new Python package or graphics framework is required.

The core provides:

- Three projected orbital planes with independent motion rates.
- Moving luminous nodes labelled `VOICE`, `TOOLS`, and `MEMORY`.
- A compact geometric nucleus with restrained cyan depth cues.
- Smooth cursor parallax and clamped drag rotation.
- Hover rings and labels for orbit nodes.
- Double-click routing to the existing command, tools, and memory surfaces.
- State-aware motion for `IDLE`, `LISTENING`, `THINKING`, `EXECUTING`, `SPEAKING`, `SUCCESS`, and `ERROR`.
- Audio-level response through the existing `set_audio_level()` path.
- `set_interaction_enabled()` for disabling pointer interaction without stopping the animation.
- Monotonic elapsed-time animation and visibility-aware repaint throttling.

The previous animated face remains available through the existing HUD-style setting. New installations default to `core`; an existing saved `hud_style: "face"` preference is preserved.

## Run

From the nested application directory:

```bash
cd Mark-LVI-main/Mark-LVI-main
python3 main.py
```

Install the declared project dependencies first when setting up a fresh environment:

```bash
python3 -m pip install -r requirements.txt
```

## Validate

Run syntax and whitespace checks from the repository root:

```bash
python3 -m py_compile \
  Mark-LVI-main/Mark-LVI-main/ui.py \
  Mark-LVI-main/Mark-LVI-main/main.py \
  Mark-LVI-main/Mark-LVI-main/memory/config_manager.py

git diff --check
```

The kinetic core does not require PyOpenGL or another new dependency. If a future hardware-accelerated surface is added, it should remain optional; the current QPainter renderer is the safe reduced-effects path for systems where GPU initialization is unavailable.
