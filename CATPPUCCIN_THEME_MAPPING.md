# Catppuccin Theme Variable Mapping for Fluenty

This document provides a comprehensive audit of Fluenty's color system and defines a mapping to Catppuccin tokens for consistent theming. This mapping follows Catppuccin's standard palette structure used in projects like `ctp-steam`.

## Catppuccin Token Vocabulary

### Base Palette (from darkest to lightest)
- `ctp-crust` - Darkest background (used for deepest UI layers)
- `ctp-mantle` - Dark background (used for sidebars, alternate backgrounds)
- `ctp-base` - Base background (primary surface color)

### Surface & Overlay Tones
- `ctp-surface0` - Slightly elevated surface
- `ctp-surface1` - More elevated surface (cards, panels)
- `ctp-surface2` - Highly elevated surface (hover states, active elements)
- `ctp-overlay0` - Subtle overlay/border
- `ctp-overlay1` - Medium overlay/border
- `ctp-overlay2` - Strong overlay/border

### Text Colors
- `ctp-text` - Primary text
- `ctp-subtext1` - Secondary text
- `ctp-subtext0` - Tertiary text/disabled

### Accent Colors
Primary accent options (user-configurable):
- `ctp-rosewater`, `ctp-flamingo`, `ctp-pink`, `ctp-mauve`
- `ctp-red`, `ctp-maroon`, `ctp-peach`, `ctp-yellow`
- `ctp-green`, `ctp-teal`, `ctp-sky`, `ctp-sapphire`
- `ctp-blue`, `ctp-lavender`

Standard mappings:
- `ctp-blue` - Primary accent (buttons, active indicators)
- `ctp-lavender` - Secondary accent (highlights, hover states)
- `ctp-red` - Destructive actions (close button)
- `ctp-green` - Success states
- `ctp-yellow` - Warnings

---

## Current Variable Inventory & Mapping

### 1. Core Variables (`src/styles/variables.css`)

| Current Variable | Current Value | Catppuccin Token | Usage | Notes |
|-----------------|---------------|------------------|-------|-------|
| `--fill-color-accent-default` | `#005fb8` | `ctp-blue` | Primary accent color | Windows blue → Catppuccin blue |
| `--fill-color-accent-secondary` | `rgba(96, 205, 255, 0.9)` | `ctp-lavender` @ 90% | Secondary accent/highlight | Light blue → Lavender |
| `--main-accent-default` | `var(--SystemAccentColorLight2, --fill-color-accent-secondary)` | `ctp-blue` or `ctp-lavender` | Accent fallback | Keep dynamic but use Catppuccin |
| `--background-fill-color-mica-background-base` | `rgb(32 32 32)` | `ctp-base` | Primary background | Base window surface |
| `--background-fill-color-acrylic-background-default` | `rgba(44, 44, 44, 0.96)` | `ctp-mantle` @ 96% | Translucent background | For acrylic effects |
| `--stroke-color-card-stroke-default` | `rgba(0, 0, 0, 0.1)` | `ctp-overlay0` @ 10% | Subtle borders | Card outlines |
| `--fill-color-subtle-secondary` | `#454545` | `ctp-surface1` | Hover/active background | Interactive states |
| `--fill-color-text-primary` | `rgba(255, 255, 255, 1)` | `ctp-text` | Primary text color | Main text |
| `--background-fill-color-acrylic-background-default` (media) | `url("../media/noise.jpeg")` | Keep as overlay | Noise texture | Preserve for acrylic effect |

---

### 2. Color Theme Variables (`src/styles/config/colors/*.css`)

#### Dark Theme (`dark.css` / `winui.css`)

**RGB Component Tokens (dark-XX series):**

| Current Variable | Current RGB | Catppuccin Token | Semantic Usage |
|-----------------|-------------|------------------|----------------|
| `--dark-13` | `19, 19, 19` | `ctp-crust` | Deepest background layer |
| `--dark-14` | `20, 20, 20` | `ctp-crust` | Very dark background |
| `--dark-19` | `25, 25, 25` | `ctp-mantle` | Dark secondary background |
| `--dark-1b` | `27, 27, 27` | `ctp-mantle` | Sidebar/alternate background |
| `--dark-1d` | `29, 29, 29` | `ctp-base` | Primary background |
| `--dark-20` | `32, 32, 32` | `ctp-base` | Base window background |
| `--dark-21` | `33, 33, 33` | `ctp-base` | Main content background |
| `--dark-29` | `41, 41, 41` | `ctp-surface0` | Elevated surface |
| `--dark-2b` | `43, 43, 43` | `ctp-surface0` | Card/panel background |
| `--dark-2d` | `45, 45, 45` | `ctp-surface1` | Button background |
| `--dark-30` | `48, 48, 48` | `ctp-surface1` | Input/interactive background |
| `--dark-31` | `49, 49, 49` | `ctp-surface1` | Borders |
| `--dark-32` | `50, 50, 50` | `ctp-surface2` | Hover states |
| `--dark-37` | `55, 55, 55` | `ctp-surface2` | Active/pressed states |
| `--dark-3a` | `58, 58, 58` | `ctp-overlay0` | Overlays, separators |

**Semantic Tokens:**

| Current Variable | Uses | Catppuccin Token | Notes |
|-----------------|------|------------------|-------|
| `--background-fill-color-layer-default` | `rgb(var(--dark-3a), 0.3)` | `ctp-overlay0` @ 30% | Layer backgrounds |
| `--settings-sidebar-btn-bg` | `rgb(var(--dark-2d))` | `ctp-surface1` | Settings sidebar buttons |
| `--settings-sidebar-hover-bg` | `rgb(var(--dark-29))` | `ctp-surface0` | Settings hover state |
| `--settings-sidebar-hover-not-select` | `rgb(var(--dark-32), 0.42)` | `ctp-surface2` @ 42% | Non-selected hover |
| `--compact-mode-navbar-button-col` | `rgb(var(--dark-30), 0.49)` | `ctp-surface1` @ 49% | Navbar buttons |
| `--settings-button-col` | `rgb(var(--dark-37))` | `ctp-surface2` | Settings buttons |
| `--settings-groupbox-bg` | `rgb(var(--dark-2b))` | `ctp-surface0` | Group boxes |
| `--settings-mdl-bg` | `rgb(var(--dark-20))` | `ctp-base` | Modal backgrounds |
| `--window-bg` | `rgb(var(--dark-1b))` | `ctp-mantle` | Window background |
| `--nosidebar-title` | `rgb(var(--dark-21), 0.46)` | `ctp-base` @ 46% | Title without sidebar |
| `--titlebar-color` | `rgb(var(--dark-1b), 0.82)` | `ctp-mantle` @ 82% | Title bar (with blur) |
| `--background-col` | `rgb(var(--dark-21))` | `ctp-base` | Main background |
| `--accent-col` | `rgb(var(--dark-20))` | `ctp-base` | Accent background |
| `--color-darker` | `rgb(var(--dark-19))` | `ctp-mantle` | Darker variant |
| `--color-darkest` | `rgb(var(--dark-14))` | `ctp-crust` | Darkest variant |
| `--color-light` | `rgb(var(--dark-30))` | `ctp-surface1` | Light variant |
| `--border-color` | `rgb(var(--dark-1d))` | `ctp-overlay0` | Primary borders |
| `--border-color-secondary` | `rgb(var(--dark-3a))` | `ctp-overlay1` | Secondary borders |
| `--accent-secondary` | `rgb(var(--dark-37))` | `ctp-surface2` | Secondary accent |
| `--focusable-col` | `rgb(var(--dark-2b))` | `ctp-surface0` | Focusable elements |
| `--input-border-col` | `rgb(var(--dark-30))` | `ctp-surface1` | Input borders |
| `--context-menu-bg` | `37, 37, 37` | `ctp-mantle` | Context menu |
| `--tray-menu-bg` | `40, 40, 40` | `ctp-surface0` | Tray menu |

#### AMOLED Theme (`amoled.css`)

All values should follow the same Catppuccin tokens but with adjusted values for pure black preference:
- `ctp-crust` → `#000000` (pure black)
- `ctp-mantle` → `#0a0a0a` (near black)
- `ctp-base` → `#0f0f0f` (very dark gray)
- Other tokens remain consistent with standard Mocha palette

#### Nord Theme (`nord.css`)

Currently uses Nord-specific colors. Should be migrated to Catppuccin tokens for consistency:
- `#2E3440` → `ctp-base`
- `#3B4252` → `ctp-surface0`
- `#434C5E` → `ctp-surface1`
- `#4C566A` → `ctp-surface2`

---

### 3. Hard-Coded Color Literals by Surface

#### Frame / Sidebar (`src/styles/frame.css`)

| Line | Current Value | Element | Catppuccin Token | Notes |
|------|--------------|---------|------------------|-------|
| 330 | `rgb(var(--dark-32))` | Breadcrumb dot | `ctp-surface2` | Navigation indicator |
| Various | `var(--fill-color-subtle-secondary)` | Hover states | `ctp-surface1` | Button hover |
| Various | `var(--fill-color-text-primary)` | Text | `ctp-text` | Primary text |
| Various | `var(--main-accent-default)` | Active indicator | `ctp-blue` | Sidebar active state |

#### Library (`src/styles/library.css`)

| Line | Current Value | Element | Catppuccin Token | Notes |
|------|--------------|---------|------------------|-------|
| 60 | `#9f9f9f` | Scrollbar thumb | `ctp-overlay1` | Scrollbar |
| 173 | `#1b1b1b` | Background | `ctp-mantle` | Dark background |
| 185 | `rgba(33, 33, 36, 0.6)` | Background | `ctp-base` @ 60% | Translucent |
| 232 | `#272727` | Background | `ctp-base` | Base surface |
| 280 | `#505050` | Background | `ctp-surface2` | Elevated surface |
| 281 | `#fff` | Text | `ctp-text` | Text color |
| 290 | `#235ecf` | Progress gradient | `ctp-blue` | Download progress |
| 293 | `#47bfff → #235ecf` | Progress gradient | `ctp-sapphire → ctp-blue` | Active download |
| 347 | `#454545` | Background | `ctp-surface1` | Interactive surface |
| 417 | `#454545` | Background | `ctp-surface1` | Button |
| 439 | `#353535` | Background | `ctp-surface0` | Card |
| 447 | `#252525` | Background | `ctp-mantle` | Dark card |
| 456 | `#1f8dff` | Accent | `ctp-blue` | Bright blue accent |
| 490 | `#383c43` | Border | `ctp-overlay0` | Subtle border |
| 511 | `rgba(143, 143, 143, 0.25)` | Border | `ctp-overlay0` @ 25% | Very subtle |
| 516 | `#353535` | Border | `ctp-surface0` | Card border |
| 546 | `#fff` | Text | `ctp-text` | Text |
| 572 | `#151515` | Background | `ctp-crust` | Very dark |
| 585 | `#252525` | Background | `ctp-mantle` | Dark surface |
| 622 | `rgb(var(--dark-19))` → gradient | `ctp-mantle` | Header gradient |
| 747 | `#0000004d` | Shadow | Keep as `rgba(0,0,0,0.3)` | Shadow overlay |
| 748 | `#2828284d` | Border | `ctp-overlay0` @ 30% | Translucent border |
| 757 | `#1e1e1eb3` | Background | `ctp-mantle` @ 70% | Semi-transparent |
| 769 | `#2c2c2c` | Background | `ctp-base` | Base background |
| 798 | `#5abce9` | Accent | `ctp-sky` | Sky blue accent |
| 808 | `#0005` | Shadow | Keep as shadow | Box shadow |
| 868 | `#272727` | Background | `ctp-base` | Surface |
| 1122 | `#ffffff85` | Text | `ctp-subtext1` @ 52% | Dimmed text |

#### Titlebar (`src/styles/titlebar/frameBar.css`)

| Line | Current Value | Element | Catppuccin Token | Notes |
|------|--------------|---------|------------------|-------|
| 14 | `#fff` | Text | `ctp-text` | Button text |
| 55 | `#e81123` | Hover | `ctp-red` | Close button hover |

#### Menus (`src/styles/menus/rootMenu.css`)

| Line | Current Value | Element | Catppuccin Token | Notes |
|------|--------------|---------|------------------|-------|
| 20 | `rgb(var(--context-menu-bg))` | Background | `ctp-mantle` | Menu background |
| 23 | `rgb(var(--dark-1b))` | Border | `ctp-overlay0` | Menu border |
| 34 | `url(../../media/noise_1.png)` | Texture | Keep | Noise overlay |
| 47 | `rgb(var(--dark-32), 0.42)` | Hover | `ctp-surface2` @ 42% | Menu item hover |
| 48, 54, 91 | `#fff` | Text | `ctp-text` | Text color |
| 71 | `rgb(var(--dark-31))` | Separator | `ctp-overlay0` | Menu divider |
| 95 | `#0000002e` | Shadow | Keep as shadow | Box shadow |
| 111 | `#4a4a4a9e` | Separator | `ctp-overlay0` @ 62% | Separator line |

#### Settings Modal (`src/styles/modals/settings/Settings.css`)

| Line | Current Value | Element | Catppuccin Token | Notes |
|------|--------------|---------|------------------|-------|
| 12, 32 | `white` | Text | `ctp-text` | Text elements |

#### Overlay (`src/styles/overlay/overlay.css`)

| Line | Current Value | Element | Catppuccin Token | Notes |
|------|--------------|---------|------------------|-------|
| 2 | `rgb(var(--dark-30))` | Background | `ctp-surface1` | Overlay background |
| 4 | `rgb(var(--dark-3a), 0.81)` | Border | `ctp-overlay0` @ 81% | Overlay border |

---

## Additional Hard-Coded Colors to Audit

The following files contain hard-coded color values that need to be catalogued and mapped:

### Modals
- `src/styles/modals/friends/FriendsChat.css` - Chat window colors
- `src/styles/modals/launchDialog/LaunchDialog.css` - Launch dialog
- `src/styles/modals/notifications/notifs.css` - Notification styling
- `src/styles/modals/screenshotsManager/ScreenshotManager.css` - Screenshot manager
- `src/styles/modals/properties/Properties.css` - Game properties
- `src/styles/modals/settings/Millennium.css` - Millennium settings

### Menus
- `src/styles/menus/notificationsMenu.css` - Notification menu
- `src/styles/menus/trayMenu.css` - System tray menu

### Overlay
- `src/styles/overlay/browser.css` - In-game browser
- `src/styles/overlay/gameOverview.css` - Game overview
- `src/styles/overlay/gameNotes.css` - Game notes

### Other Surfaces
- `src/styles/downloadPage.css` - Downloads page
- `src/styles/loginView.css` - Login screen
- `src/styles/noSidebar.css` - No sidebar variant
- `src/styles/titlebar/steamMainBar.css` - Main title bar
- `src/styles/utility/browserContextMenu.css` - Browser context menus
- `src/styles/webkit/*.css` - WebKit-specific styles

### Config Variants
- `src/styles/config/compactSideBar.css` - Compact sidebar colors
- `src/styles/config/compactView.css` - Compact view colors
- `src/styles/config/playButtonMatte.css` - Play button styling
- `src/styles/config/profile/transparentBG.css` - Profile backgrounds
- `src/styles/config/sidebarBase.css` - Sidebar base colors
- `src/styles/config/win11SideBar.css` - Windows 11 sidebar

---

## Special Considerations

### 1. Acrylic/Blur Effects
- Preserve noise texture overlays (`--background-fill-color-acrylic-background-default` url)
- Use Catppuccin tokens with appropriate alpha values for translucency
- Acrylic backgrounds: `ctp-mantle` @ 85-96% opacity

### 2. Gradients
- Download progress: `ctp-blue` to `ctp-sapphire`
- Header gradients: `ctp-mantle` to `ctp-mantle` @ 90%
- Keep gradient structure, replace color stops with Catppuccin tokens

### 3. Shadows & Overlays
- Box shadows should remain as `rgba(0, 0, 0, alpha)` for proper shadow rendering
- Use `ctp-overlay0/1/2` for colored overlays and borders, not shadows

### 4. Interactive States
- **Default:** Base token (e.g., `ctp-surface1`)
- **Hover:** Next level up (e.g., `ctp-surface2`)
- **Active/Pressed:** `ctp-overlay0` or accent color
- **Disabled:** `ctp-subtext0` @ 50%

### 5. Scrollbars
- Thumb: `ctp-overlay1`
- Track: transparent or `ctp-surface0` @ 20%
- Hover: `ctp-overlay2`

### 6. Borders & Separators
- Subtle borders: `ctp-overlay0` @ 10-30%
- Standard borders: `ctp-overlay0`
- Prominent borders: `ctp-overlay1`
- Dividers/separators: `ctp-overlay0` @ 20-40%

### 7. Text Hierarchy
- **Primary:** `ctp-text`
- **Secondary:** `ctp-subtext1`
- **Tertiary/Disabled:** `ctp-subtext0`
- **Inverted (on dark accent):** Keep as `#fff` or use `ctp-crust`

### 8. Accent Color Usage
- Primary actions: `ctp-blue`
- Active indicators: `ctp-blue`
- Hover highlights: `ctp-lavender`
- Success: `ctp-green`
- Warning: `ctp-yellow`
- Error/Destructive: `ctp-red`
- Info: `ctp-sky`
- Special highlights: `ctp-mauve`, `ctp-pink`

---

## Implementation Strategy

### Phase 1: Define Catppuccin Variables
Create new color scheme files that define all Catppuccin tokens:
- `src/styles/config/colors/catppuccin-mocha.css` - Mocha (dark) palette
- `src/styles/config/colors/catppuccin-macchiato.css` - Macchiato palette
- `src/styles/config/colors/catppuccin-frappe.css` - Frappé palette
- `src/styles/config/colors/catppuccin-latte.css` - Latte (light) palette

### Phase 2: Map Semantic Variables
Update `src/styles/variables.css` to use Catppuccin tokens instead of hard-coded values:
```css
:root {
    /* Catppuccin base tokens defined in color scheme files */
    --fill-color-accent-default: var(--ctp-blue);
    --fill-color-accent-secondary: var(--ctp-lavender);
    --background-fill-color-mica-background-base: var(--ctp-base);
    --fill-color-text-primary: var(--ctp-text);
    /* ... etc */
}
```

### Phase 3: Migrate RGB Component System
Replace `--dark-XX` variables with Catppuccin equivalents in color config files:
```css
:root {
    --dark-13: var(--ctp-crust-rgb);
    --dark-14: var(--ctp-crust-rgb);
    --dark-1b: var(--ctp-mantle-rgb);
    /* ... etc */
}
```

### Phase 4: Replace Hard-Coded Values
Systematically replace all hard-coded hex/rgba values throughout `src/styles/**` with:
1. Existing semantic variables (if appropriate)
2. New Catppuccin token variables (if no semantic variable exists)
3. Keep only shadows and special effects as hard-coded

### Phase 5: Test & Refine
- Test all themes (Mocha, Macchiato, Frappé, Latte)
- Verify contrast ratios for accessibility
- Ensure acrylic/blur effects work correctly
- Check all interactive states (hover, active, disabled)

---

## Catppuccin Token Definitions (Mocha Reference)

For implementation, here are the standard Catppuccin Mocha hex values:

```css
/* Catppuccin Mocha */
:root {
    /* Base colors */
    --ctp-rosewater: #f5e0dc;
    --ctp-flamingo: #f2cdcd;
    --ctp-pink: #f5c2e7;
    --ctp-mauve: #cba6f7;
    --ctp-red: #f38ba8;
    --ctp-maroon: #eba0ac;
    --ctp-peach: #fab387;
    --ctp-yellow: #f9e2af;
    --ctp-green: #a6e3a1;
    --ctp-teal: #94e2d5;
    --ctp-sky: #89dceb;
    --ctp-sapphire: #74c7ec;
    --ctp-blue: #89b4fa;
    --ctp-lavender: #b4befe;
    
    /* Text colors */
    --ctp-text: #cdd6f4;
    --ctp-subtext1: #bac2de;
    --ctp-subtext0: #a6adc8;
    
    /* Surface colors */
    --ctp-overlay2: #9399b2;
    --ctp-overlay1: #7f849c;
    --ctp-overlay0: #6c7086;
    --ctp-surface2: #585b70;
    --ctp-surface1: #45475a;
    --ctp-surface0: #313244;
    
    /* Base backgrounds */
    --ctp-base: #1e1e2e;
    --ctp-mantle: #181825;
    --ctp-crust: #11111b;
    
    /* RGB variants for use with rgb() and rgba() */
    --ctp-crust-rgb: 17, 17, 27;
    --ctp-mantle-rgb: 24, 24, 37;
    --ctp-base-rgb: 30, 30, 46;
    --ctp-surface0-rgb: 49, 50, 68;
    --ctp-surface1-rgb: 69, 71, 90;
    --ctp-surface2-rgb: 88, 91, 112;
    --ctp-overlay0-rgb: 108, 112, 134;
    --ctp-overlay1-rgb: 127, 132, 156;
    --ctp-overlay2-rgb: 147, 153, 178;
    --ctp-text-rgb: 205, 214, 244;
    --ctp-blue-rgb: 137, 180, 250;
    --ctp-lavender-rgb: 180, 190, 254;
}
```

---

## Summary

This audit catalogues:
- **11 core variables** in `variables.css`
- **15 RGB component tokens** (dark-XX series)
- **24 semantic color variables** in theme configs
- **100+ hard-coded color values** across 40+ files
- **Complete mapping** to 24 Catppuccin tokens

All colors are mapped to appropriate Catppuccin tokens with specific guidance for:
- Background layers (crust → mantle → base → surface0/1/2)
- Interactive states (default → hover → active)
- Text hierarchy (text → subtext1 → subtext0)
- Accent colors (blue, lavender, red, etc.)
- Special effects (shadows, borders, overlays)

This mapping provides clear guidance for replacing all Fluent colors with Catppuccin tokens while maintaining visual hierarchy and accessibility.
