# Multi-Select Component Demos

## Project Overview

This is an interactive design prototyping environment for exploring and testing multi-select UI component patterns. It provides a live, configurable playground where designers and developers can experiment with different interaction models, visual styles, and behaviors for multi-select dropdowns.

## Purpose & Goals

- **Rapid Prototyping**: Test different multi-select patterns without building production code
- **Design Exploration**: Compare various UI approaches side-by-side with real interactions
- **Usability Testing**: Evaluate keyboard navigation, search, and selection behaviors
- **Component Documentation**: Demonstrate patterns that can be implemented in production systems

## Tech Stack

- **Pure HTML/CSS/JavaScript**: No frameworks or dependencies
- **Single-file architecture**: Everything contained in [components/multi-select.html](components/multi-select.html)
- **Vanilla JS**: Approximately 1,800 lines of interactive component logic
- **CSS Grid & Flexbox**: Modern responsive layout techniques

## Features

### Multi-Select Variants

1. **Checkbox Mode**: Standard checkboxes for multi-selection
2. **Checkbox with Tips**: Includes supporting text below each option
3. **Tree Selection**: Hierarchical checkbox structure with parent/child relationships
4. **Default Mode**: Icon-based list with check indicators

### Interactive Capabilities

- **Search & Filter**: Real-time filtering of options as you type
- **Tag Display**: Selected items shown as removable tags
- **See All/Less**: Collapses tag display when 6+ items are selected (shows first 5)
- **Keyboard Navigation**:
  - Arrow keys: Navigate through options
  - Tab/Shift+Tab: Move between focusable elements
  - Enter/Space: Select/deselect items
  - Escape: Close dropdown
  - Backspace: Remove tags when input is empty
  - Home/End: Jump to first/last item

### Smart UI Behaviors

- **Dynamic Dropdown Positioning**: Automatically flips dropdown above input when space is limited
- **Loading States**: Optional skeleton loading (2.5s simulation)
- **Select All/Clear All**: Bulk selection controls
- **Indeterminate States**: Parent checkboxes show partial selection in tree mode
- **Focus Management**: Maintains input focus during interactions
- **Click-outside**: Closes dropdown when clicking outside component

### Control Panel

Real-time configuration options:

- Data source selection (Languages/Names)
- Number of items to display
- Submenu type selector
- Loading behavior toggle
- Initial selected items count
- Container width adjustment
- Display options (label, hint text, error messages)

## Sample Data

- **Languages Dataset**: 29 international language variants with locale codes
  - English (Australia, Austria, Canada, UK, US)
  - French (International, Belgium, Canada, France)
  - German (Germany, Austria, Switzerland)
  - And more...

- **Names Dataset**: 10 common names for simpler testing scenarios

## Tree Structure

The tree mode demonstrates hierarchical selection with:
- **English category**: 5 child language variants
- **French category**: 4 child language variants

Parent checkboxes show:
- ✓ Checked when all children are selected
- - Indeterminate when some children are selected
- ☐ Unchecked when no children are selected

## Component Architecture

### State Management

The component maintains a central state object tracking:
- Selected items (Set of indices)
- Dropdown open/closed state
- Search query
- Loading states
- Focused elements (for keyboard navigation)
- UI preferences (show label, hints, errors)

### Render Cycle

1. User interaction triggers state change
2. `renderComponent()` regenerates HTML
3. Event listeners reattach
4. Focus restored to appropriate element
5. Dropdown position recalculated if needed

## Accessibility Features

- ARIA roles (`combobox`, `listbox`, `option`)
- ARIA attributes (`aria-expanded`, `aria-selected`, `aria-activedescendant`)
- Keyboard navigation support
- Focus indicators (yellow ring on focused elements)
- Semantic HTML structure

## Use Cases

This prototype is ideal for:

- Design system documentation
- UX research and usability studies
- Client presentations and stakeholder reviews
- Developer implementation reference
- A/B testing different interaction patterns
- Training and onboarding materials

## Recent Updates

Based on commit history:

- Added "see all/see less" toggle for managing large selections
- Implemented tree selection with category grouping
- Enhanced category label display for parent items
- Various UI refinements and bug fixes

## Getting Started

1. Open [components/multi-select.html](components/multi-select.html) in a web browser
2. Use the left control panel to configure component settings
3. Interact with the multi-select component in the preview area
4. Resize the preview container to test responsive behavior
5. Experiment with different submenu types and data sources

## File Structure

```
design-docs-component-demos/
├── claude.md                    # This file
├── components/
│   └── multi-select.html       # Complete interactive prototype
└── .git/                       # Git repository
```

## Future Enhancements

Potential additions to explore:

- Virtual scrolling for large datasets
- Custom tag rendering with icons/avatars
- Grouping/categorization in non-tree modes
- Multi-column layouts
- Async data loading simulation
- Mobile touch interactions
- Theme variations (dark mode, color schemes)
- Export to production code snippets

---

**Note**: This is a design prototype, not production-ready code. Use it as a reference for implementing similar patterns in your production systems with proper frameworks, state management, and testing.
