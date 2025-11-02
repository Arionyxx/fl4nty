# Fluenty

> A modern Steam skin featuring Catppuccin theming with Windows 11 Fluent-inspired design

Fluenty transforms the Steam client with a spacious, polished aesthetic inspired by Microsoft's Fluent Design System and powered by the beautiful [Catppuccin](https://github.com/catppuccin/catppuccin) color palette.

## ✨ Features

- 🎨 **Four Catppuccin Flavors**: Mocha, Macchiato, Frappé, and Latte
- 🪟 **Fluent Design**: Windows 11-inspired UI with acrylic effects
- 🎯 **Highly Customizable**: Multiple sidebar layouts, scrollbar options, and more
- 🌈 **Consistent Theming**: Unified color system across all Steam surfaces
- ⚡ **Quality of Life**: Enhanced download monitoring, navigation sync, and more

## 🖼️ Catppuccin Flavors

Fluenty uses the official [Catppuccin](https://github.com/catppuccin/catppuccin) color palette, offering four distinct flavors:

### 🌙 Mocha (Default - Dark)
The most popular Catppuccin dark theme featuring warm, cozy tones with excellent contrast.
- **Base Color**: `#1e1e2e`
- **Best For**: Default dark theme users

### ☕ Macchiato (Dark)
A warm, alternative dark theme with slightly lighter backgrounds than Mocha.
- **Base Color**: `#24273a`
- **Best For**: Users who prefer warmer tones with more depth

### 🧊 Frappé (Dark)
A cool-toned dark theme with a refreshing, crisp appearance.
- **Base Color**: `#303446`
- **Best For**: Users who prefer cooler, blue-leaning color temperatures

### ☀️ Latte (Light)
A carefully crafted light theme maintaining readability while staying true to Catppuccin's aesthetic.
- **Base Color**: `#eff1f5`
- **Best For**: Light theme enthusiasts

## 📥 Installation

1. **Install Millennium**: This skin requires [Millennium](https://steambrew.app/) to be installed on your Steam client
2. **Download Fluenty**: Get the latest release from the Millennium themes repository
3. **Apply the Skin**: Enable Fluenty through Millennium's skin manager
4. **Choose Your Flavor**: Navigate to Settings → Millennium → Fluenty → Color Preferences → Color Scheme

## ⚙️ Customization

### Switching Color Flavors

1. Open Steam Settings
2. Navigate to **Millennium** section
3. Select **Fluenty** skin settings
4. Under **Color Preferences** tab, find **Color Scheme**
5. Choose your preferred Catppuccin flavor:
   - **Mocha** - Dark theme (default)
   - **Macchiato** - Dark theme (warm variant)
   - **Frappé** - Dark theme (cool variant)
   - **Latte** - Light theme

### Other Customization Options

Fluenty offers extensive customization through Millennium's settings panel:

**Window Preferences:**
- Sidebar View: Windows 11, Compact, or No Sidebar
- Scroll Bar Width: 2px, 4px, or 6px
- Title Bar Auto Hide: Show or Hide

**Library Preferences:**
- Library List: Full, Compact, or Hidden
- Play Button Alignment: Center or Left Spanning
- Play Button Color: System accent or matte
- Game Header Width: Full or Original
- What's New Section: Show or Hide
- Add Shelf Section: Show or Hide

**Miscellaneous:**
- Main Profile Settings: Default or Transparent
- Store Page Live Broadcast: Show or Hide

## 🎨 For Theme Developers & Contributors

### Catppuccin Token System

Fluenty uses a comprehensive token-based color system. Each flavor file defines:

#### Core Catppuccin Tokens (24 total)

**Accent Colors (14):**
```css
--ctp-rosewater, --ctp-flamingo, --ctp-pink, --ctp-mauve
--ctp-red, --ctp-maroon, --ctp-peach, --ctp-yellow
--ctp-green, --ctp-teal, --ctp-sky, --ctp-sapphire
--ctp-blue, --ctp-lavender
```

**Text Hierarchy (3):**
```css
--ctp-text      /* Primary text */
--ctp-subtext1  /* Secondary text */
--ctp-subtext0  /* Tertiary/disabled text */
```

**Surface Layers (6):**
```css
--ctp-surface0, --ctp-surface1, --ctp-surface2
--ctp-overlay0, --ctp-overlay1, --ctp-overlay2
```

**Base Backgrounds (3):**
```css
--ctp-base      /* Primary surface */
--ctp-mantle    /* Alternate background */
--ctp-crust     /* Deepest layer */
```

#### RGB Variants

All tokens include RGB variants for use with `rgba()` functions:
```css
--ctp-blue: #89b4fa;
--ctp-blue-rgb: 137, 180, 250;

/* Usage */
color: var(--ctp-blue);
background: rgba(var(--ctp-blue-rgb), 0.5);
```

### Architecture

**Color System Structure:**
```
src/styles/config/colors/catppuccin/
├── mocha.css      # Dark theme (default)
├── macchiato.css  # Dark theme (warm)
├── frappe.css     # Dark theme (cool)
└── latte.css      # Light theme
```

Each flavor file contains:
1. **Catppuccin Native Tokens** (`--ctp-*`) - Official color values
2. **RGB Variants** (`--ctp-*-rgb`) - For opacity control
3. **Legacy Compatibility** (`--dark-XX`) - Mapped to Catppuccin tokens
4. **Semantic Variables** - High-level design tokens using Catppuccin colors

### Theme Configuration

Color flavors are configured in `skin.json` under the `Conditions` section:

```json
{
  "Color Scheme": {
    "tab": "Color Preferences",
    "default": "Mocha",
    "values": {
      "Mocha": { "TargetCss": { "src": "src/styles/config/colors/catppuccin/mocha.css" }},
      "Macchiato": { ... },
      "Frappé": { ... },
      "Latte": { ... }
    }
  }
}
```

### Technical Documentation

For detailed technical information, see:

- **[CATPPUCCIN_IMPLEMENTATION.md](./CATPPUCCIN_IMPLEMENTATION.md)** - Complete implementation summary
- **[CATPPUCCIN_THEME_MAPPING.md](./CATPPUCCIN_THEME_MAPPING.md)** - Detailed token mappings and migration guide
- **[CATPPUCCIN_AUDIT_SUMMARY.md](./CATPPUCCIN_AUDIT_SUMMARY.md)** - Audit findings and color inventory

### Contributing

When contributing to Fluenty's color system:

1. **Use Catppuccin Tokens**: Reference `var(--ctp-*)` instead of hard-coded colors
2. **Maintain Hierarchy**: Follow the surface elevation pattern (crust → mantle → base → surface0/1/2)
3. **Test All Flavors**: Ensure changes work across all four Catppuccin flavors
4. **Preserve Accessibility**: Maintain sufficient contrast ratios for text readability
5. **Document Changes**: Update technical docs if modifying the token system

### Adding New Components

When styling new Steam UI elements:

1. Use semantic variables from flavor files where available
2. Reference Catppuccin tokens directly for new use cases
3. Follow the established patterns:
   - Backgrounds: `ctp-base`, `ctp-mantle`, `ctp-surface*`
   - Borders: `ctp-overlay0` @ 10-30% opacity
   - Text: `ctp-text`, `ctp-subtext1`, `ctp-subtext0`
   - Accents: `ctp-blue` (primary), `ctp-lavender` (hover)
   - States: `ctp-green` (success), `ctp-red` (error), `ctp-yellow` (warning)

## 🔍 Verification & Testing

To verify the Catppuccin theme system is working correctly:

1. **Switch Between Flavors**: 
   - Navigate to Settings → Millennium → Fluenty → Color Preferences
   - Select each flavor (Mocha, Macchiato, Frappé, Latte)
   - Verify color changes are applied immediately

2. **Test Key Surfaces**:
   - ✅ Frame and sidebar navigation
   - ✅ Library view (grid/list)
   - ✅ Game detail pages
   - ✅ Context menus and dropdowns
   - ✅ Modal dialogs (Settings, Properties)
   - ✅ Titlebar and window controls
   - ✅ In-game overlay

3. **Verify Interactive States**:
   - ✅ Hover effects on buttons
   - ✅ Active indicators in sidebar
   - ✅ Focus states on inputs
   - ✅ Download progress bars

4. **Check Text Readability**:
   - ✅ Primary text contrast
   - ✅ Secondary text visibility
   - ✅ Disabled state appearance
   - ✅ Light theme (Latte) contrast ratios

## 🐛 Known Limitations

- **Legacy Hard-coded Colors**: Some Steam UI elements still contain hard-coded color values. These will be gradually migrated to use Catppuccin tokens. See [CATPPUCCIN_THEME_MAPPING.md](./CATPPUCCIN_THEME_MAPPING.md) for details.
- **Steam Client Updates**: Steam client updates may introduce new UI elements that haven't been styled yet.
- **Acrylic Effects**: Some acrylic/blur effects depend on Steam's rendering capabilities and may vary by platform.

## 🔮 Future Enhancements

- [ ] Complete migration of all hard-coded color values to Catppuccin tokens
- [ ] Customizable accent color selection (choose primary accent while keeping flavor base)
- [ ] Additional Catppuccin-inspired color variants
- [ ] Enhanced animation and transition effects
- [ ] Community-contributed component styles

## 📚 Resources

- **Catppuccin Project**: [github.com/catppuccin/catppuccin](https://github.com/catppuccin/catppuccin)
- **Catppuccin Palette Showcase**: [catppuccin.com/palette](https://catppuccin.com/palette)
- **Millennium (Steam Patcher)**: [steambrew.app](https://steambrew.app/)
- **Steam Skin Documentation**: [Millennium Docs](https://steambrew.app/docs)

## 👥 Authors

- **ShadowMonster** - Original Fluenty design
- **Clawdius** - Co-developer
- **Catppuccin Team** - Color palette ([catppuccin.com](https://catppuccin.com))

## 📜 License

Fluenty is licensed under a proprietary license. See [LICENSE](./LICENSE) for full terms.

The Catppuccin color palette is licensed under the MIT License. See [Catppuccin License](https://github.com/catppuccin/catppuccin/blob/main/LICENSE) for details.

## 🙏 Acknowledgments

- The [Catppuccin](https://github.com/catppuccin) team for creating the beautiful color palette
- The [Millennium](https://steambrew.app/) team for making Steam skinning possible
- The Steam community for feedback and support

---

**Version**: 1.10.0  
**Last Updated**: November 2024  
**Status**: Active Development
