A React hook to access data from the [Magnetometer API](https://developer.mozilla.org/en-US/docs/Web/API/Magnetometer).

## Installation

Using `npm`:

```sh
npm install --save react-hook-magnetometer
```

Using `yarn`:

```sh
yarn add react-hook-magnetometer
```

## Usage

```jsx
import React from 'react'
import useMagnetometer from 'react-hook-magnetometer'

const MyComponent = () => {
  const magnetometer = useMagnetometer()

  return !magnetometer.error ? (
    <ul>
      <li>X: {magnetometer.x}</li>
      <li>Y: {magnetometer.y}</li>
      <li>Z: {magnetometer.z}</li>
    </ul>
  ) : (
    <p>No magnetometer, sorry.</p>
  )
}
```

### Using `SensorOptions`

If you want to use this feature, simply provide `useMagnetometer` with a `SensorOptions` object:

```jsx
const magnetometer = useMagnetometer({
  frequency: 60, // cycles per second
})
```

## Notes

Access to data from the Magnetometer API needs user permission.

If permission to access magnetometer was previously granted by the user, magnetometer data will be available. If permission to access was not granted previously, the user will be prompted to give permission when the component mounts.

## Caveats

Magnetometer API is available only in secure contexts (only using HTTPS).

## Credits

Credit to [Bence A. Tóth](https://github.com/bence-toth) for his original hook code for [Geolocation](https://www.npmjs.com/package/react-hook-geolocation).

## License

LGPL-3.0
