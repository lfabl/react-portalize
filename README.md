# Portalize

The simplest way to render anything on top of the rest FOR WEB.

## Installation

```bash
yarn add react-portalize
```

## Usage

```tsx
import React from 'react';
import { Host, Portal } from 'react-portalize';

export const MyApp = () => (
  <Host>
    <div>
      <span>Some copy here and there...</span>

      <Portal>
        <span>A portal on top of the rest</span>
      </Portal>
    </div>
  </Host>
);
```

**Example with `react-modalize` and `react-navigation`**

```tsx
import React from 'react';
import { NavigationContainer } from '@react-navigation/native';
import { createBottomTabNavigator } from '@react-navigation/bottom-tabs';
import { Host, Portal } from 'react-portalize';

const Tab = createBottomTabNavigator();

const ExamplesScreen = () => {
  return (
    <>
      <div onPress={onOpen}>
        <span>Open the modal</span>
      </div>

      <Portal>
        <div>...your modal content</div>
      </Portal>
    </>
  );
};

const SettingsScreen = () => (
  <div style={{ display: 'flex', flexDirection: 'column', justifyContent: 'center', alignItems: 'center' }}>
    <span>Settings screen</span>
  </div>
);

export const App = () => (
  <NavigationContainer>
    <Host>
      <Tab.Navigator>
        <Tab.Screen name="Examples" component={ExamplesScreen} />
        <Tab.Screen name="Settings" component={SettingsScreen} />
      </Tab.Navigator>
    </Host>
  </NavigationContainer>
);
```

## Props

### Host

- `children`

A React node that will be most likely wrapping your whole app.

| Type | Required |
| ---- | -------- |
| node | Yes      |

- `style`

Optional props to define the style of the Host component.

| Type  | Required |
| ----- | -------- |
| style | No       |

### Portal

- `children`

The React node you want to display on top of the rest.

| Type | Required |
| ---- | -------- |
| node | Yes      |
