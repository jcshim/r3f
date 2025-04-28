## r3f란?
**r3f**는 **React Three Fiber**의 줄임말입니다.  
- **React**를 쓰듯이 **Three.js** 3D 그래픽스를 다루게 해주는 **React 전용 라이브러리**입니다.  
- 풀네임: **React Three Fiber**.

---

## r3f를 한 줄로 요약하면
> "Three.js를 React 방식으로 사용하게 해주는 라이브러리."

---

## Three.js와 r3f의 차이
| 항목 | Three.js | r3f (React Three Fiber) |
|:---|:---|:---|
| 스타일 | **전통적인 JavaScript 코드**로 작성 | **React 컴포넌트**처럼 작성 |
| 접근 방식 | 명령형 (imperative) → "이것을 하고, 저것을 하고" | 선언형 (declarative) → "이런 장면을 만들어줘" |
| 코드 예시 | `const mesh = new THREE.Mesh(geometry, material); scene.add(mesh);` | `<mesh geometry={...} material={...} />` |
| 사용 대상 | 순수 Three.js만 쓰는 프로젝트 | React 기반 웹 프로젝트에 3D 그래픽을 통합하고 싶을 때 |

---

## 비유로 설명하면
- **Three.js**: 직접 요리하는 것 (프라이팬 들고 재료 볶고, 물 끓이고... 전부 명령)
- **r3f**: 레시피를 써놓고 "요리해줘" 하는 것 (컴포넌트로 선언)

---

## 요약
- **Three.js**는 순수 JavaScript 3D 엔진.
- **r3f**는 **Three.js를 React 컴포넌트처럼 다루게 해주는 라이브러리**.
- 둘 다 3D를 만든다는 목표는 같지만, **코딩 스타일과 사용법이 다르다**.
