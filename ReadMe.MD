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

The final command center follows the supplied PHANTOM concept across the whole shell: the icon navigation rail, monitor/current-task/quick-action cards, activity log, upcoming schedule, files/media cards, and floating listening dock are all built into `MainWindow` while preserving the existing callbacks. The core surface uses `Mark-LVI-main/Mark-LVI-main/assets/phantom_kinetic_core.png` for the reference-matched glass/metal finish, with live state, audio, parallax, hover, drag, and orbit-node overlays drawn by `HudCanvas`. Listening adds green orbital response, speaking adds an audio-reactive amber waveform/radial response, and hover changes parallax/focus lighting. If the asset is unavailable, the procedural QPainter kinetic core remains the safe reduced-effects fallback. No new Python dependency or GPU runtime is required.

The visual specification and audit trail are stored in `design-refs/phantom-kinetic-core-desktop-default.png` and `design-refs/phantom-kinetic-core-breakdown.md`.
