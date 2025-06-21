# 📱 PhoneWrapper Component (React Native Web)

This `PhoneWrapper` component helps simulate a mobile device screen within your **React Native Web** app.  
It wraps your content inside a styled mobile-like container, useful for visualizing how your UI would look on a real Android device.

---

## Features

- Mimics a real Android phone screen
- Works on **React Native Web**
- Adjustable size (`393x852` by default)
- Adds border and camera decoration (web only)
- Does not affect native platforms (Android/iOS)

---

## 💻 Usage

```tsx
import PhoneWrapper from "./PhoneWrapper";

export default function App() {
  return (
    <PhoneWrapper>
      {/* Your mobile UI or screens go here */}
    </PhoneWrapper>
  );
}
