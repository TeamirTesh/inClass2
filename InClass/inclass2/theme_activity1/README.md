# Theme Demo — In-Class Assignment

A single-screen Flutter app that toggles between light and dark themes, with animated UI and a switch control.

## What Was Covered

### 1. Theming (Light & Dark)
- **`MaterialApp`** uses `theme` (light) and `darkTheme` (dark) so the app has two distinct looks.
- **`themeMode`** is set from state (`_themeMode`) so the active theme can change at runtime (e.g. `ThemeMode.light`, `ThemeMode.dark`, or `ThemeMode.system`).

### 2. Using Theme Data (No Hardcoded Colors)
- Colors and text styles come from the **current theme** via `Theme.of(context)`.
- Examples: `Theme.of(context).brightness`, `Theme.of(context).colorScheme.primary`, `Theme.of(context).textTheme.bodyLarge`.
- This keeps the UI consistent with the active theme and supports light/dark switching.

### 3. State for Theme Toggling
- A **state variable** (`_themeMode`) holds the current theme mode.
- A **method** (`changeTheme`) updates it with `setState()` so the app rebuilds and applies the new theme.
- The Switch (or any control) calls this method to switch between light and dark.

### 4. AnimatedContainer
- The main content area uses **`AnimatedContainer`** instead of `Container`.
- When properties (e.g. color) change with the theme, the change **animates** over a set **duration** (here, 500 ms).
- Demonstrates smooth transitions when theme-dependent properties update.

### 5. Switch Widget for Theme Selection
- A single **`Switch`** replaces separate buttons.
- **Value:** `_themeMode == ThemeMode.dark` (true when dark mode is on).
- **onChanged:** Receives a boolean and calls `changeTheme(isDark ? ThemeMode.dark : ThemeMode.light)`.

### 6. Dynamic Icons
- An **`Icon`** changes with the theme: **sun** (`Icons.wb_sunny`) in light mode, **moon** (`Icons.nightlight_round`) in dark mode.
- The choice is based on `Theme.of(context).brightness`.

## How to Run

From the `theme_activity1` directory:

```bash
flutter run
```

Use the **Dark mode** switch to toggle themes; the container color and icon animate/update accordingly.
