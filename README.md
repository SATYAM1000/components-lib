# @satyamx55/react-ui

A comprehensive React component library built with Tailwind CSS and Radix UI primitives.

## Installation

```bash
npm install @satyamx55/react-ui
```

## Setup

### 1. Install Required Dependencies

Your project needs these peer dependencies:

```bash
npm install react react-dom tailwindcss
```

### 2. Import CSS Styles

**⚠️ IMPORTANT: You MUST import the CSS file for components to work properly.**

Choose one of these methods:

**Option A: Import in your main entry file (Recommended)**
```javascript
// src/main.tsx or src/index.tsx
import '@satyamx55/react-ui/styles.css';
```

**Option B: Import in your main CSS file**
```css
/* src/index.css or src/App.css */
@import '@satyamx55/react-ui/styles.css';
```

### 3. Configure Tailwind CSS

Create or update your `tailwind.config.js`:

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,ts,jsx,tsx}",
    "./node_modules/@satyamx55/react-ui/dist/**/*.js"
  ],
  theme: {
    extend: {
      colors: {
        border: "hsl(var(--border))",
        input: "hsl(var(--input))",
        ring: "hsl(var(--ring))",
        background: "hsl(var(--background))",
        foreground: "hsl(var(--foreground))",
        primary: {
          DEFAULT: "hsl(var(--primary))",
          foreground: "hsl(var(--primary-foreground))",
        },
        secondary: {
          DEFAULT: "hsl(var(--secondary))",
          foreground: "hsl(var(--secondary-foreground))",
        },
        destructive: {
          DEFAULT: "hsl(var(--destructive))",
          foreground: "hsl(var(--destructive-foreground))",
        },
        muted: {
          DEFAULT: "hsl(var(--muted))",
          foreground: "hsl(var(--muted-foreground))",
        },
        accent: {
          DEFAULT: "hsl(var(--accent))",
          foreground: "hsl(var(--accent-foreground))",
        },
        popover: {
          DEFAULT: "hsl(var(--popover))",
          foreground: "hsl(var(--popover-foreground))",
        },
        card: {
          DEFAULT: "hsl(var(--card))",
          foreground: "hsl(var(--card-foreground))",
        },
      },
      borderRadius: {
        lg: "var(--radius)",
        md: "calc(var(--radius) - 2px)",
        sm: "calc(var(--radius) - 4px)",
      },
    },
  },
  plugins: [],
}
```

### 4. Add Base Styles (Optional but Recommended)

Add these base styles to your main CSS file:

```css
/* src/index.css or src/App.css */
@import '@satyamx55/react-ui/styles.css';

/* Your custom styles can go here */
```

### 5. Dark Mode Support (Optional)

If you want dark mode support, add the `dark` class to your HTML:

```html
<html class="dark">
<!-- or -->
<html class="light">
```

Or use a theme provider like `next-themes`:

```bash
npm install next-themes
```

```jsx
// App.jsx
import { ThemeProvider } from 'next-themes'

function App() {
  return (
    <ThemeProvider attribute="class" defaultTheme="system" enableSystem>
      {/* Your app content */}
    </ThemeProvider>
  )
}
```

## Usage

### Basic Example

```tsx
import React from 'react';
import { Button, Card, CardContent, CardHeader, CardTitle } from '@satyamx55/react-ui';

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

## Troubleshooting

### Styles Not Applied?

1. **Check CSS Import**: Make sure you've imported `@satyamx55/react-ui/styles.css` in your main entry file.

2. **Tailwind Content Configuration**: Ensure your `tailwind.config.js` includes the library path:
   ```javascript
   content: [
     "./src/**/*.{js,ts,jsx,tsx}",
     "./node_modules/@satyamx55/react-ui/dist/**/*.js"
   ]
   ```

3. **CSS Variables**: The library uses CSS variables. Make sure you're not overriding them accidentally.

4. **Build Process**: If using Vite, make sure your build process includes CSS processing.

### Common Issues

**Components appear unstyled:**
- Import the CSS file: `import '@satyamx55/react-ui/styles.css';`
- Check that Tailwind is configured correctly

**Dark mode not working:**
- Add `class="dark"` to your HTML element
- Or use a theme provider

**TypeScript errors:**
- Make sure you have `@types/react` and `@types/react-dom` installed
- Check that your TypeScript version is compatible

## Available Components

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
import { cn } from '@satyamx55/react-ui';

const MyComponent = ({ className, ...props }) => (
  <div className={cn("default-classes", className)} {...props} />
);
```

### Custom Theming

You can customize the theme by overriding CSS variables:

```css
:root {
  --background: 0 0% 100%;
  --foreground: 222.2 84% 4.9%;
  --primary: 222.2 47.4% 11.2%;
  --primary-foreground: 210 40% 98%;
  /* Add more theme variables as needed */
}

.dark {
  --background: 222.2 84% 4.9%;
  --foreground: 210 40% 98%;
  --primary: 210 40% 98%;
  --primary-foreground: 222.2 47.4% 11.2%;
  /* Add more dark theme variables */
}
```

## TypeScript Support

This library is built with TypeScript and includes full type definitions. All components are fully typed for the best development experience.

## Contributing

Issues and pull requests are welcome! Please visit the [GitHub repository](https://github.com/satyamx55/components-lib) to contribute.

## License

MIT License - see LICENSE file for details.
