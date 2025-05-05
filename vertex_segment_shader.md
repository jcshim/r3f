물론입니다! 아래는 기존 `meshBasicMaterial`을 \*\*사용자 정의 vertex/fragment shader (`shaderMaterial`)\*\*로 대체한 완전한 예제입니다. 이 코드는 `@react-three/fiber`, `@react-three/drei`, `three` 패키지를 활용하며, 삼각형 꼭짓점에 색을 주고 그것을 보간해서 그라디언트처럼 보여줍니다.

---

### ✅ 설치가 필요한 패키지:

```bash
npm install three @react-three/fiber @react-three/drei
```

---

### 🌈 Rainbow Triangle – 사용자 정의 셰이더 적용 예제

```jsx
// App.jsx

import React from 'react';
import { Canvas, extend } from '@react-three/fiber';
import { shaderMaterial } from '@react-three/drei';
import * as THREE from 'three';

// 사용자 정의 셰이더 정의
const RainbowMaterial = shaderMaterial(
  {},
  ` // vertex shader
    varying vec3 vColor;
    attribute vec3 color;

    void main() {
      vColor = color;
      gl_Position = projectionMatrix * modelViewMatrix * vec4(position, 1.0);
    }
  `,
  ` // fragment shader
    varying vec3 vColor;

    void main() {
      gl_FragColor = vec4(vColor, 1.0);
    }
  `
);

extend({ RainbowMaterial });

function RainbowTriangle() {
  const positions = new Float32Array([
     0,  1, 0,   // 위쪽 꼭지점
    -1, -1, 0,   // 왼쪽 아래
     1, -1, 0    // 오른쪽 아래
  ]);

  const colors = new Float32Array([
    1, 0, 0,  // 빨강
    0, 1, 0,  // 초록
    0, 0, 1   // 파랑
  ]);

  return (
    <mesh>
      <bufferGeometry>
        <bufferAttribute
          attach="attributes-position"
          array={positions}
          count={3}
          itemSize={3}
        />
        <bufferAttribute
          attach="attributes-color"
          array={colors}
          count={3}
          itemSize={3}
        />
      </bufferGeometry>
      <rainbowMaterial />
    </mesh>
  );
}

export default function App() {
  return (
    <Canvas style={{ background: 'black', height: '100vh' }}>
      <RainbowTriangle />
    </Canvas>
  );
}
```

---

이 코드는 각 꼭짓점에 RGB 색을 부여하고, 셰이더에서 그 색을 받아와 픽셀에 그라디언트처럼 보간하여 출력합니다.

셰이더 부분을 바꾸어 다양한 색상 표현이나 애니메이션도 가능하니, 원하시면 그쪽도 도와드릴 수 있어요. 애니메이션도 추가해볼까요?
