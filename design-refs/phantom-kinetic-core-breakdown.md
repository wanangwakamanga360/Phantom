# PHANTOM kinetic core — visual breakdown

Reference: `phantom-kinetic-core-desktop-default.png` (1920 × 1920, standalone close-up).

## Visual goal

A compact floating mechanical energy assembly, not a flat neon orb: dark glass and brushed-metal depth, segmented luminous arcs, a readable dark nucleus, a few orbital paths with bright nodes, and a restrained pedestal/energy beam.

## Layout skeleton

- Square composition with the core centered horizontally around x=960.
- Mechanical ring assembly occupies roughly x=250–1660 and y=120–1430.
- Central nucleus is approximately 36–40% of the assembly width and sits around y=760.
- Pedestal begins around y=1450 and occupies the lower quarter, with a thin vertical cyan energy beam connecting to the core.
- Large negative space remains in the upper corners and around the outer orbit segments.

## Geometry and spacing

- Use 3 primary depth layers: central glass nucleus, dense mid-ring mechanism, sparse outer orbital arcs.
- Inner ring spacing is tight and regular; outer orbit spacing is wider and asymmetric.
- Segments have deliberate gaps. No complete bright continuous cyan circles.
- Orbital paths are thin, smooth curves with 3–5 luminous nodes total.
- Mechanical segments are short rectangular/trapezoidal arc pieces, not filled disks.

## Color and depth

- Background: near-black navy, approximately #020914 to #061525.
- Structural metal: charcoal/navy with cool steel highlights, not saturated cyan fill.
- Primary edge light: electric cyan/blue around #00BFFF–#32D7FF.
- Specular highlights: near-white blue #D9F5FF.
- Optional warm reflection: restrained steel/amber at low opacity on a few metal edges.
- Glow is localized to edges, nodes, beam, and pedestal rings. The nucleus remains dark.

## Center nucleus

- Dark circular/hexagonal glass badge with subtle blue rim.
- Exact readable label: `JARVIS`, thin uppercase lettering with wide tracking.
- Label is white-blue, not grey and not embedded in a bright cyan disc.

## Motion and interaction mapping

- Three orbit groups rotate at independent low speeds in idle.
- Listening increases node brightness and adds audio-reactive inner ticks.
- Thinking increases internal ring speed and adds a subtle scan sweep.
- Executing biases motion in one direction.
- Success produces a brief cyan pulse; error changes only edge accents to restrained red.
- Cursor parallax is limited to a few percent of the assembly size.
- Drag rotates the assembly, clamped to a modest pitch/yaw range.

## Known implementation delta

The reference is a photorealistic concept render. The existing application uses PyQt6 QPainter, so the implementation will reproduce the composition, layering, segmentation, lighting hierarchy, and interactions without introducing a heavy 3D dependency. It must remain responsive and preserve the face fallback and current assistant wiring.
