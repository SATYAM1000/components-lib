# @satyamx55/components-lib

A comprehensive React component library built with Tailwind CSS and Radix UI primitives.

## Installation

```bash
npm install @satyamx55/components-lib
```

## Setup

### 1. Install Required Dependencies

Your project needs these peer dependencies:

```bash
npm install react react-dom
```

### 2. Configure Tailwind CSS

Add this to your `tailwind.config.js`:

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,ts,jsx,tsx}",
    "./node_modules/@satyamx55/components-lib/dist/**/*.js"
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

### 3. Add Global Styles

Import the required CSS in your main CSS file or `index.css`:

```css
@import "tailwindcss/base";
@import "tailwindcss/components";
@import "tailwindcss/utilities";
```

## Usage

### Basic Example

```tsx
import React from 'react';
import { Button, Card, CardContent, CardHeader, CardTitle } from '@satyamx55/components-lib';

function App() {
  return (
    <div className="p-8">
      <Card className="max-w-md mx-auto">
        <CardHeader>
          <CardTitle>Welcome to Components Lib</CardTitle>
        </CardHeader>
        <CardContent>
          <p className="mb-4">This is a sample card component.</p>
          <Button onClick={() => alert('Button clicked!')}>
            Click Me
          </Button>
        </CardContent>
      </Card>
    </div>
  );
}

export default App;
```

### Available Components

#### Form Components
- `Button` - Customizable button with variants
- `Input` - Text input with validation support
- `Textarea` - Multi-line text input
- `Checkbox` - Checkbox input
- `Switch` - Toggle switch
- `RadioGroup` - Radio button group
- `Select` - Dropdown select component
- `Label` - Form labels
- `Form` - Form components with validation

#### Layout Components
- `Card` - Card container with header, content, and footer
- `Separator` - Visual separator line
- `AspectRatio` - Maintain aspect ratios
- `Sidebar` - Collapsible sidebar navigation
- `Resizable` - Resizable panel layout

#### Navigation Components
- `Breadcrumb` - Navigation breadcrumbs
- `Pagination` - Page navigation
- `NavigationMenu` - Primary navigation menu
- `Menubar` - Menu bar component
- `Tabs` - Tab navigation

#### Data Display
- `Avatar` - User avatar with fallback
- `Badge` - Status badges and labels
- `Table` - Data table components
- `Calendar` - Date picker calendar
- `Chart` - Chart components
- `Carousel` - Image/content carousel
- `Accordion` - Collapsible content sections

#### Feedback Components
- `Alert` - Alert messages
- `AlertDialog` - Modal alert dialogs
- `Dialog` - Modal dialogs
- `Drawer` - Slide-out drawer
- `Popover` - Floating popover content
- `Tooltip` - Contextual tooltips
- `Progress` - Progress indicators
- `Skeleton` - Loading placeholders

#### Utilities
- `ScrollArea` - Custom scrollable area
- `Collapsible` - Collapsible content
- `HoverCard` - Hover-triggered card
- `Sheet` - Side panel component
- `Slider` - Range slider input
- `Toggle` - Toggle button
- `ToggleGroup` - Group of toggle buttons
- `Command` - Command palette
- `ContextMenu` - Right-click context menu
- `DropdownMenu` - Dropdown menu

### Using the `cn` Utility

The library exports a `cn` utility function for merging Tailwind classes:

```tsx
import { cn } from '@satyamx55/components-lib';

const MyComponent = ({ className, ...props }) => (
  <div className={cn("default-classes", className)} {...props} />
);
```

### Theming

Components are built with CSS variables for easy theming. You can customize colors by setting CSS variables in your global styles:

```css
:root {
  --background: 0 0% 100%;
  --foreground: 222.2 84% 4.9%;
  --primary: 222.2 47.4% 11.2%;
  --primary-foreground: 210 40% 98%;
  /* Add more theme variables as needed */
}
```

## TypeScript Support

This library is built with TypeScript and includes full type definitions. All components are fully typed for the best development experience.

## Contributing

Issues and pull requests are welcome! Please visit the [GitHub repository](https://github.com/satyamx55/components-lib) to contribute.

## License

MIT License - see LICENSE file for details.
