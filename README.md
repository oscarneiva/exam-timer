# Exam Timer

A minimalistic web-based timer for IB and IGCSE exams. Single-page HTML/CSS/JS application with no dependencies.

## Features

- **IB exams**: 5-minute reading time, 30-minute warning, 5-minute warning
- **IGCSE exams**: 5-minute warning
- **Up to 6 simultaneous timers** in a responsive grid
- Live countdown with current time display
- Editable start time per card for handling delays
- Save/load all timer configurations as JSON
- Remove individual timers with the x button
- Color-coded cards: blue (IB), red (IGCSE)
- High-contrast black text on white background; inverted white text on highlighted warnings
- Large, readable fonts — milestone rows sized close to the countdown for visibility at a distance

## Usage

1. Open `index.html` in a browser
2. Select exam board (IB or IGCSE)
3. Enter exam name, duration, and start time
4. Click **Add Timer**
5. Click the **+** card to add more timers (up to 6)

### Editing start time

Click **Edit** next to the start time on the timer card to adjust for delays. All warning times recalculate automatically.

### Save / Load

- **Download Timers** (bottom-right) saves all timer configurations as `timer.json`
- **Load saved timers** on the setup screen imports a previously saved `timer.json`

## Timer milestones

| Milestone    | IB  | IGCSE |
|-------------|-----|-------|
| Reading     | Start - 5 min | -- |
| Start       | User-defined | User-defined |
| 30 min left | End - 30 min | -- |
| 5 min left  | End - 5 min | End - 5 min |
| End         | Start + duration | Start + duration |

Milestones highlight (blue for IB, red for IGCSE) once the current time passes them.

## File structure

```
exam-timer/
  index.html    # Full application (HTML + CSS + JS)
  README.md     # This file
```

## Configuration file format

`timer.json` schema (array of timers):

```json
[
  {
    "board": "IB",
    "name": "English B Paper 1 HL",
    "durationMin": 90,
    "startMin": 540
  },
  {
    "board": "IGCSE",
    "name": "Biology Paper 4",
    "durationMin": 75,
    "startMin": 540
  }
]
```

Loading also accepts a single object (legacy format).

| Field         | Type   | Description                            |
|--------------|--------|----------------------------------------|
| `board`      | string | `"IB"` or `"IGCSE"`                   |
| `name`       | string | Exam name                              |
| `durationMin`| number | Exam duration in minutes               |
| `startMin`   | number | Start time as minutes from midnight (e.g. 540 = 09:00) |

## Browser support

Any modern browser (Chrome, Firefox, Safari, Edge). No build step or server required.

## License

<!-- TODO: choose a license -->
