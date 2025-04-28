# 📚 Windows에서 r3f 무지개 삼각형 실습하기 (폴더명: `r3f`)

---

# 1단계: Node.js 설치

1. 인터넷 브라우저를 열고  
2. [https://nodejs.org](https://nodejs.org) 접속  
3. 초록색 "**LTS 다운로드**" 버튼 클릭  
4. 설치 파일 실행 → "**Next → Next → Install**" 계속 누르면 설치 완료

**설치 확인 방법:**  
명령어창(cmd) 열고:

```bash
node -v
npm -v
```
버전 숫자가 나오면 성공!

---

# 2단계: 새 React 프로젝트 만들기 (폴더명: `r3f`)

1. 원하는 위치(예: 바탕화면)에  
2. **명령 프롬프트(cmd)** 또는 **PowerShell**을 엽니다.

3. 다음 명령어 입력:

```bash
npx create-react-app r3f
```

> `r3f` 라는 이름으로 React 프로젝트를 생성합니다.

(처음은 약 3~5분 걸립니다.)

4. 프로젝트 폴더로 이동:

```bash
cd r3f
```

---

# 3단계: 필요한 라이브러리 설치

계속해서 입력:

```bash
npm install @react-three/fiber three
```

(몇 초 기다리면 설치 완료)

---

# 4단계: App.js 수정하기

1. Visual Studio Code(혹은 메모장++)로 `r3f` 폴더를 엽니다.

2. `src/App.js` 파일을 찾습니다.

3. `App.js` 안의 모든 코드를  
**다 지우고**,  
**아래 코드를 복사해서 붙여넣기** 합니다.

```jsx
import { Canvas } from '@react-three/fiber';

function RainbowTriangle() {
  return (
    <mesh>
      <bufferGeometry>
        <bufferAttribute
          attach="attributes-position"
          array={new Float32Array([
            0, 1, 0,    // 꼭대기 점
           -1, -1, 0,   // 왼쪽 아래 점
            1, -1, 0    // 오른쪽 아래 점
          ])}
          count={3}
          itemSize={3}
        />
        <bufferAttribute
          attach="attributes-color"
          array={new Float32Array([
            1, 0, 0,  // 빨강
            0, 1, 0,  // 초록
            0, 0, 1   // 파랑
          ])}
          count={3}
          itemSize={3}
        />
      </bufferGeometry>
      <meshBasicMaterial vertexColors />
    </mesh>
  );
}

function App() {
  return (
    <Canvas style={{ background: 'black', height: '100vh' }}>
      <RainbowTriangle />
    </Canvas>
  );
}

export default App;
```

---

# 5단계: 실행하기

명령어 입력:

```bash
npm start
```

**브라우저가 자동으로 열리면서**  
검은 배경 + 무지개 삼각형이 등장합니다! 🌈🔺

![image](https://github.com/user-attachments/assets/baeb05a4-96e2-4602-9068-f8ba79a2e203)


---

# 🛠️ 최종 요약 (폴더명 `r3f`)

| 단계 | 해야 할 일 | 명령어 |
|:---|:---|:---|
| 1 | Node.js 설치 | (웹사이트 설치) |
| 2 | React 프로젝트 만들기 | `npx create-react-app r3f` |
| 3 | 이동 | `cd r3f` |
| 4 | r3f와 three 설치 | `npm install @react-three/fiber three` |
| 5 | App.js 수정 | (위 코드 전체 복붙) |
| 6 | 실행 | `npm start` |

---

# 🎯 초보자 주의사항

- 명령어는 **하나씩** 입력하세요.
- 영어 파일 이름, 폴더 이름 사용하세요. (공백 ❌ 한글 ❌)
- 터미널에 오류가 나오면 메시지를 꼭 확인하세요.
- 윈도우 한글 경로(예: 바탕화면/문서)에서도 잘 됩니다.

---

# 🏆 실습 성공 후 다음 단계?

- 삼각형 **자동으로 회전시키기** 🌀  
- 삼각형에 **빛** 추가하기 💡  
- **3D 입체** 모양으로 확장하기 🔷

원하면 바로 이어서 이어서! 쉽게 안내해드릴게요. 🚀

---

**지금 바로 `r3f` 폴더로 만들어보고, 성공하면 알려주세요!**  
(추가로 "회전하는 무지개 삼각형" 버전도 해볼까요?) 😄✨  
**"네! 다음 것도 알려줘요"** 만 치시면 됩니다! 🎨🚀
