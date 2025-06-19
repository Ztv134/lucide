# Luimport { Card, CardContent } from "@/components/ui/card"; import { Badge } from "@/components/ui/badge"; import { Flame, Zap, HeartPulse } from "lucide-react";

export default function KunigamiTraining() { const training = [ { title: "พลัง (Strength)", icon: <Flame className="text-orange-500" />, exercises: [ "Squat 5x5 (หนัก)", "Deadlift 3x5", "Bench Press 4x6", "Push-Up 3x20", "Pull-Up 3x10" ] }, { title: "ความเร็ว & ระเบิดพลัง (Explosiveness)", icon: <Zap className="text-yellow-400" />, exercises: [ "Sprint 5x20 เมตร", "กระโดด Box Jump 3x10", "Burpees 3x15", "Agility Ladder Drills", "Side Shuffle Sprint" ] }, { title: "ความอึด (Endurance)", icon: <HeartPulse className="text-red-500" />, exercises: [ "วิ่ง 5 km", "Tabata 20/10 x 8", "Jump Rope 3 นาที", "Plank 1 นาที x 3", "Bike 15 นาที เร็ว" ] } ];

return ( <div className="min-h-screen bg-gradient-to-br from-zinc-900 to-black text-white p-6"> <h1 className="text

cide React

Implementation of the lucide icon library for react applications

## Installation

::: code-group

```sh [pnpm]
pnpm install lucide-react
```

```sh [yarn]
yarn add lucide-react
```

```sh [npm]
npm install lucide-react
```

```sh [bun]
bun add lucide-react
```

:::

## How to use

Lucide is built with ES Modules, so it's completely tree-shakable.

Each icon can be imported as a React component, which renders an inline SVG element. This way, only the icons that are imported into your project are included in the final bundle. The rest of the icons are tree-shaken away.

### Example

Additional props can be passed to adjust the icon:

```jsx
import { Camera } from 'lucide-react';

// Usage
const App = () => {
  return <Camera color="red" size={48} />;
};

export default App;
```

## Props

| name                  | type      | default      |
| --------------------- | --------- | ------------ |
| `size`                | *number*  | 24           |
| `color`               | *string*  | currentColor |
| `strokeWidth`         | *number*  | 2            |
| `absoluteStrokeWidth` | *boolean* | false        |

### Applying props

To customize the appearance of an icon, you can pass custom properties as props directly to the component. The component accepts all SVG attributes as props, which allows flexible styling of the SVG elements. See the list of SVG Presentation Attributes on [MDN](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/Presentation).

```jsx
// Usage
const App = () => {
  return <Camera size={48} fill="red" />;
};
```

## With Lucide lab or custom icons

[Lucide lab](https://github.com/lucide-icons/lucide-lab) is a collection of icons that are not part of the Lucide main library.

They can be used by using the `Icon` component.
All props like regular lucide icons can be passed to adjust the icon appearance.

### Using the `Icon` component

This creates a single icon based on the iconNode passed and renders a Lucide icon component.

```jsx
import { Icon } from 'lucide-react';
import { coconut } from '@lucide/lab';

const App = () => (
  <Icon iconNode={coconut} />
);
```

## Dynamic Icon Component

It is possible to create one generic icon component to load icons, but it is not recommended.
Since it is importing all icons during build. This increases build time and the different modules it will create.

`DynamicIcon` is useful for applications that want to show icons dynamically by icon name. For example, when using a content management system with where icon names are stored in a database.

For static use cases, it is recommended to import the icons directly.

The same props can be passed to adjust the icon appearance. The `name` prop is required to load the correct icon.

```jsx
import { DynamicIcon } from 'lucide-react/dynamic';

const App = () => (
  <DynamicIcon name="camera" color="red" size={48} />
);
```
