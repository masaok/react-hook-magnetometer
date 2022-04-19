# react-hook-accelerometer

A React hook to access data from the [Accelerometer API](https://developer.mozilla.org/en-US/docs/Web/API/Accelerometer).

## Installation

Using `npm`:

```sh
npm install --save react-hook-accelerometer
```

Using `yarn`:

```sh
yarn add react-hook-accelerometer
```

## Usage

```jsx
import React from 'react'
import useAccelerometer from 'react-hook-accelerometer'

const ComponentWithAccelerometer = () => {
  const accelerometer = useAccelerometer()

  return !accelerometer.error ? (
    <ul>
      <li>X: {accelerometer.x}</li>
      <li>Y: {accelerometer.y}</li>
      <li>Z: {accelerometer.z}</li>
    </ul>
  ) : (
    <p>No accelerometer, sorry.</p>
  )
}
```

### Using `SensorOptions`

If you want to use this feature, simply provide `useAccelerometer` with a `SensorOptions` object:

```jsx
const accelerometer = useAccelerometer({
  frequency: 60, // cycles per second
})
```

## Notes

Access to data from the Accelerometer API needs user permission.

If permission to access accelerometer was previously granted by the user, accelerometer data will be available. If permission to access was not granted previously, the user will be prompted to give permission when the component mounts.

## Caveats

Accelerometer API is available only in secure contexts (only using HTTPS).

## Credits

Credit to [Bence A. Tóth](https://github.com/bence-toth) for his original hook code for [Geolocation](https://www.npmjs.com/package/react-hook-geolocation).

## License

LGPL-3.0
