# Design System Demo

A comprehensive, scalable design system implementation built with Vue.js and SCSS, following modern CSS architecture principles and inspired by Material Design guidelines and Object-Oriented CSS (OOCSS) concepts.

## 📋 Overview

This project demonstrates a production-ready design system architecture that provides:

- **Scalable CSS Architecture**: Built on the 7-1 SCSS pattern for maintainable and organized stylesheets
- **Material Design Principles**: Elevation system, color palettes, and typography scales inspired by Material Design
- **Object-Oriented CSS**: Reusable, modular components following OOCSS principles
- **Theme Support**: Light and dark theme implementations with CSS custom properties
- **Design Tokens**: Centralized design tokens for colors, typography, spacing, elevation, and more

> **Note**: This project was originally developed in 2022. While some dependencies may be dated, the architecture and design system concepts remain relevant and demonstrate solid CSS organization principles.

## 🏗️ Architecture

### 7-1 SCSS Pattern

The project follows the [7-1 SCSS architecture pattern](https://sass-guidelin.es/#the-7-1-pattern), which organizes stylesheets into logical, maintainable folders:

```
src/assets/style/
├── abstracts/     # Variables, functions, mixins, and placeholders
├── base/          # Reset, typography, and base styles
├── components/    # UI component styles
├── objects/       # Design patterns (OOCSS)
├── tools/         # Global mixins and functions
├── vendors/       # Third-party styles
└── style.scss     # Main entry point
```

### Directory Structure

#### `abstracts/`
Design tokens and foundational variables:
- `_color.scss` - Color palettes (light/dark themes), shades, text colors, backgrounds, borders
- `_typography.scss` - Typography scale with responsive breakpoints
- `_spacing.scss` - Spacing scale
- `_elevation.scss` - Material Design elevation system (24 levels)
- `_breakpoint.scss` - Responsive breakpoints
- `_shape.scss` - Border radius and shape tokens
- `_font.scss` - Font family definitions
- `_z-index.scss` - Z-index scale

#### `base/`
Foundation styles:
- `_reset.scss` - CSS reset/normalize
- `_base.scss` - Base element styles
- `_fonts.scss` - Font face declarations
- `_color.scss` - CSS custom properties for theming

#### `components/`
UI component styles (buttons, cards, inputs, etc.)

#### `objects/`
Reusable design patterns following OOCSS principles:
- `_elevation.scss` - Elevation utility classes

#### `tools/`
Global utilities and helpers:
- `_mixin.scss` - Reusable mixins
- `_spacing.scss` - Spacing utilities
- `_typography.scss` - Typography utilities
- `_elevation.scss` - Elevation mixins

#### `vendors/`
Third-party library styles

## 🎨 Design System Concepts

### Material Design Inspiration

The design system incorporates key Material Design concepts:

1. **Elevation System**: 24-level elevation system using box-shadows (light theme) and overlays (dark theme)
2. **Color System**: Semantic color tokens (primary, secondary, error, success, info, warning) with shade variations
3. **Typography Scale**: Material Design typography scale with responsive variants
4. **Shape System**: Consistent border radius and shape tokens

### Object-Oriented CSS (OOCSS)

The architecture follows OOCSS principles:

- **Separation of Structure and Skin**: Layout styles separated from visual styles
- **Separation of Container and Content**: Components are independent of their containers
- **Reusability**: Styles are modular and can be combined in different ways
- **Scalability**: Easy to extend without modifying existing code

### Theme System

The design system supports light and dark themes using CSS custom properties:

```scss
// Theme is applied via data attribute
<div data-theme="dark">
  <!-- Dark theme styles -->
</div>
```

Color tokens are automatically generated for both themes:
- `--clr-primary`, `--clr-secondary`, etc.
- `--text-primary`, `--text-secondary`, etc.
- `--bg-primary`, `--bg-surface`, etc.
- `--border-primary`, `--border-secondary`, etc.

## 🚀 Getting Started

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd design-system-demo
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run serve
```

4. Build for production:
```bash
npm run build
```

## 📦 Project Structure

```
design-system-demo/
├── public/              # Static assets
├── src/
│   ├── assets/
│   │   ├── fonts/       # Custom font files (IranYekan)
│   │   └── style/       # Design system stylesheets
│   ├── components/      # Vue components
│   ├── App.vue          # Root component
│   └── main.js          # Application entry point
├── package.json
└── README.md
```

## 🎯 Key Features

### 1. Color System
- Semantic color tokens (primary, secondary, error, success, info, warning)
- Color shade variations (100-900)
- Theme-aware color generation
- Text, background, and border color tokens

### 2. Typography
- Material Design typography scale
- Responsive typography (default, small, medium, large)
- Semantic type styles (h1-h6, body1, body2, button, caption, etc.)

### 3. Elevation
- 24-level elevation system
- Material Design-compliant shadows
- Dark theme overlay support

### 4. Spacing System
- Consistent spacing scale
- Utility classes for margins and padding

### 5. Responsive Design
- Breakpoint system
- Mobile-first approach

## 💡 Usage Examples

### Using Design Tokens

```vue
<template>
  <div class="card" data-theme="dark">
    <h1>Card Title</h1>
    <p>Card content</p>
  </div>
</template>

<style lang="scss">
.card {
  background-color: var(--bg-primary);
  color: var(--text-primary);
  border: 1px solid var(--border-primary);
  padding: var(--spacing-md);
}
</style>
```

### Using Elevation

```scss
@use '@/assets/style/tools' as *;

.card {
  @include light-elevation(4);
  // or for dark theme
  @include dark-elevation(4);
}
```

### Using Typography

```scss
@use '@/assets/style/tools' as *;

.heading {
  // Typography utilities available
}
```

## 🔧 Customization

### Adding New Colors

Edit `src/assets/style/abstracts/_color.scss`:

```scss
$palette: (
  light: (
    primary: #your-color,
    // ... other colors
  ),
  // ...
);
```

### Adding New Components

1. Create component styles in `src/assets/style/components/`
2. Import in `src/assets/style/components/_index.scss`
3. Use in your Vue components

## 📚 Design Principles

1. **Consistency**: All design tokens are centralized and reusable
2. **Scalability**: Architecture supports growth without refactoring
3. **Maintainability**: Clear separation of concerns and organized structure
4. **Accessibility**: Semantic color tokens and proper contrast ratios
5. **Performance**: Modular imports allow tree-shaking unused styles

## 🤝 Contributing

This is a demonstration project showcasing design system architecture. Feel free to:

- Fork the repository
- Submit issues
- Propose improvements
- Share your own implementations

## 📝 License

This project is open source and available for educational and demonstration purposes.

## 🙏 Acknowledgments

- [7-1 SCSS Architecture Pattern](https://sass-guidelin.es/#the-7-1-pattern)
- [Material Design Guidelines](https://material.io/design)
- [Object-Oriented CSS (OOCSS)](https://github.com/stubbornella/oocss/wiki)

## 📅 Project Status

This project was originally developed in 2022 as a demonstration of design system architecture. The core concepts and structure remain relevant, though some dependencies may need updating for production use.

---

**Built with ❤️ to demonstrate scalable CSS architecture and design system principles**

