## 📱 PhoneWrapper Component 

This `PhoneWrapper` component helps simulate a mobile device screen within your **React Native Web** app.  
It wraps your content inside a styled mobile-like container, useful for visualizing how your UI would look on a real Android device.

![image](https://github.com/user-attachments/assets/bcf31eef-a4b0-4c53-af13-c0e481cd75ba)



### Features
- Mimics a real Android phone screen
- Adjustable size (`393x852` by default)
- Adds border and camera decoration (web only)
- Does not affect native platforms (Android/iOS)

### 💻 Usage
1. First, create the component, 

```tsx
import { useState } from "react";
import { View, Text, Platform, StyleSheet } from "react-native";

export default function PhoneWrapper({
  children,
}: {
  children: React.ReactNode;
}) {
  const [PhoneWrapper, setPhoneWrapper] = useState(true);
  const [StatusBar, setStatusBar] = useState(true);
  const [frontCamera, setFrontCamera] = useState(true);

  return (
    <View style={styles.containerWrapper}>
      <View
        style={{
          width: "100%",
          height: "100%",
          borderRadius: Platform.OS === "web" ? 60 : 0,
          overflow: "hidden",
          borderColor: "#010103",
          borderWidth: Platform.OS === "web" ? 6 : 0,
        }}
      >
        {Platform.OS === "web" && (
          <View style={styles.CameraView}>
            <View style={styles.camera}> </View>
          </View>
        )}

        {children}
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  containerWrapper: {
    width: Platform.OS === "web" ? 393 : "100%",
    height: Platform.OS === "web" ? 852 : "100%",
    borderRadius: Platform.OS === "web" ? 65 : 0,
    borderWidth: Platform.OS === "web" ? 3 : 0,
    borderColor: Platform.OS === "web" ? "#294B4A" : "transparent",
    backgroundColor: Platform.OS === "web" ? "#668789" : "transparent",
    margin: "auto",
    padding: 3,
    zIndex: 10,
  },
  btnOff: {
    position: "absolute",
    top: 200,
    left: -5,
    width: 30,
    height: 60,
    borderRadius: 8,
    borderWidth: Platform.OS === "web" ? 3 : 0,
    borderColor: Platform.OS === "web" ? "#294B4A" : "transparent",
    backgroundColor: Platform.OS === "web" ? "#668789" : "transparent",
    zIndex: -100,
  },
  StatusBar: {
    width: "100%",
    height: 50,
    flexDirection: "row",
    justifyContent: "space-between",
    position: "relative",
  },
  CameraView: {
    width: "100%",
    height: 50,
    backgroundColor: "#F2F2F2",
    justifyContent: "center",
    alignItems: "center",
  },
  camera: {
    width: 130,
    height: 32,
    borderRadius: 50,
    marginTop: 8,
    backgroundColor: "#000",
  },
});

```

2. Use it in your App.tsx or App.js

```tsx
import PhoneWrapper from "./PhoneWrapper";

export default function App() {
  return (
    <PhoneWrapper>
      {/* Your mobile UI or screens go here */}
    </PhoneWrapper>
  );
}
```
