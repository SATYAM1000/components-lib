# Usage Example: Using @satyamx55/react-ui in a New Project

This guide shows how to integrate and use your published component library in a new React project.

## Step 1: Create a New React Project

```bash
npx create-react-app my-app --template typescript
cd my-app
```

Or with Vite:

```bash
npm create vite@latest my-app -- --template react-ts
cd my-app
npm install
```

## Step 2: Install the Component Library

```bash
npm install @satyamx55/react-ui
```

## Step 3: Install and Configure Tailwind CSS

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

Update your `tailwind.config.js`:

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

## Step 4: Import the Component Library CSS

**⚠️ IMPORTANT**: You must import the CSS file for the components to work properly.

In your `src/main.tsx` (Vite) or `src/index.tsx` (Create React App):

```tsx
import '@satyamx55/react-ui/styles.css';
```

## Step 5: Add Tailwind CSS to Your Styles

In your `src/index.css` or `src/App.css`:

```css
@import '@satyamx55/react-ui/styles.css';
@import "tailwindcss/base";
@import "tailwindcss/components";
@import "tailwindcss/utilities";
```

## Step 6: Use the Components

### Basic Example (src/App.tsx)

```tsx
import React, { useState } from 'react';
import {
  Button,
  Card,
  CardContent,
  CardHeader,
  CardTitle,
  Input,
  Label,
  Checkbox,
  Badge,
  Alert,
  AlertTitle,
  AlertDescription,
  Avatar,
  AvatarFallback,
  AvatarImage,
  Separator,
  Tabs,
  TabsContent,
  TabsList,
  TabsTrigger,
} from '@satyamx55/react-ui';

function App() {
  const [inputValue, setInputValue] = useState('');
  const [isChecked, setIsChecked] = useState(false);

  return (
    <div className="min-h-screen bg-gray-50 p-8">
      <div className="max-w-4xl mx-auto space-y-8">
        {/* Header */}
        <div className="text-center">
          <h1 className="text-4xl font-bold text-gray-900 mb-2">
            Component Library Demo
          </h1>
          <p className="text-gray-600">
            Showcasing components from @satyamx55/react-ui
          </p>
        </div>

        {/* Alert */}
        <Alert>
          <AlertTitle>Welcome!</AlertTitle>
          <AlertDescription>
            This is a demo of the component library. Try interacting with the components below.
          </AlertDescription>
        </Alert>

        {/* Tabs */}
        <Tabs defaultValue="components" className="w-full">
          <TabsList className="grid w-full grid-cols-3">
            <TabsTrigger value="components">Components</TabsTrigger>
            <TabsTrigger value="forms">Forms</TabsTrigger>
            <TabsTrigger value="data">Data Display</TabsTrigger>
          </TabsList>

          <TabsContent value="components" className="space-y-4">
            <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
              {/* Button Examples */}
              <Card>
                <CardHeader>
                  <CardTitle>Buttons</CardTitle>
                </CardHeader>
                <CardContent className="space-y-4">
                  <div className="flex gap-2">
                    <Button>Default</Button>
                    <Button variant="destructive">Destructive</Button>
                    <Button variant="outline">Outline</Button>
                    <Button variant="ghost">Ghost</Button>
                  </div>
                  <div className="flex gap-2">
                    <Button size="sm">Small</Button>
                    <Button size="lg">Large</Button>
                  </div>
                </CardContent>
              </Card>

              {/* Avatar Examples */}
              <Card>
                <CardHeader>
                  <CardTitle>Avatars</CardTitle>
                </CardHeader>
                <CardContent className="space-y-4">
                  <div className="flex gap-4">
                    <Avatar>
                      <AvatarImage src="https://github.com/shadcn.png" alt="Avatar" />
                      <AvatarFallback>CN</AvatarFallback>
                    </Avatar>
                    <Avatar>
                      <AvatarFallback>JD</AvatarFallback>
                    </Avatar>
                    <Avatar>
                      <AvatarFallback>AB</AvatarFallback>
                    </Avatar>
                  </div>
                </CardContent>
              </Card>

              {/* Badge Examples */}
              <Card>
                <CardHeader>
                  <CardTitle>Badges</CardTitle>
                </CardHeader>
                <CardContent className="space-y-4">
                  <div className="flex gap-2">
                    <Badge>Default</Badge>
                    <Badge variant="secondary">Secondary</Badge>
                    <Badge variant="destructive">Destructive</Badge>
                    <Badge variant="outline">Outline</Badge>
                  </div>
                </CardContent>
              </Card>
            </div>
          </TabsContent>

          <TabsContent value="forms" className="space-y-4">
            <Card>
              <CardHeader>
                <CardTitle>Form Components</CardTitle>
              </CardHeader>
              <CardContent className="space-y-4">
                <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
                  <div className="space-y-2">
                    <Label htmlFor="email">Email</Label>
                    <Input 
                      id="email"
                      type="email" 
                      placeholder="Enter your email" 
                      value={inputValue}
                      onChange={(e) => setInputValue(e.target.value)}
                    />
                  </div>
                  <div className="space-y-2">
                    <Label htmlFor="password">Password</Label>
                    <Input id="password" type="password" placeholder="Enter password" />
                  </div>
                </div>
                
                <Separator />
                
                <div className="flex items-center space-x-2">
                  <Checkbox 
                    id="terms"
                    checked={isChecked}
                    onCheckedChange={setIsChecked}
                  />
                  <Label htmlFor="terms">Accept terms and conditions</Label>
                </div>
                
                <Button disabled={!isChecked} className="w-full">
                  Submit Form
                </Button>
              </CardContent>
            </Card>
          </TabsContent>

          <TabsContent value="data" className="space-y-4">
            <Card>
              <CardHeader>
                <CardTitle>Data Display</CardTitle>
              </CardHeader>
              <CardContent className="space-y-4">
                <div className="space-y-2">
                  <h3 className="font-semibold">User Profile</h3>
                  <div className="flex items-center space-x-4">
                    <Avatar>
                      <AvatarFallback>JD</AvatarFallback>
                    </Avatar>
                    <div>
                      <p className="font-medium">John Doe</p>
                      <p className="text-sm text-gray-600">john.doe@example.com</p>
                    </div>
                    <Badge>Active</Badge>
                  </div>
                </div>
                
                <Separator />
                
                <div className="space-y-2">
                  <h3 className="font-semibold">Current Input Value:</h3>
                  <p className="text-sm text-gray-600">
                    {inputValue || 'No input entered yet'}
                  </p>
                </div>
              </CardContent>
            </Card>
          </TabsContent>
        </Tabs>
      </div>
    </div>
  );
}

export default App;
```

## Step 7: Run Your Application

```bash
npm start
```

Your application should now be running with your component library integrated!

## Advanced Usage

### Custom Styling

You can customize components by passing additional classes:

```tsx
<Button className="bg-purple-600 hover:bg-purple-700">
  Custom Purple Button
</Button>
```

### Using the cn Utility

```tsx
import { cn } from '@satyamx55/react-ui';

const MyComponent = ({ className, variant = 'default' }) => (
  <div 
    className={cn(
      'base-styles',
      variant === 'highlighted' && 'bg-yellow-200',
      className
    )}
  >
    Content
  </div>
);
```

### TypeScript Support

All components are fully typed:

```tsx
import { ButtonProps } from '@satyamx55/react-ui';

const CustomButton: React.FC<ButtonProps> = ({ children, ...props }) => (
  <Button {...props}>
    {children}
  </Button>
);
```

## Next Steps

1. Explore more components in the library
2. Check out the documentation for each component
3. Customize the theme using CSS variables
4. Build your application with confidence!

## Package Information

- **Package Name**: `@satyamx55/react-ui`
- **Version**: 1.1.2
- **Registry**: https://www.npmjs.com/package/@satyamx55/react-ui 