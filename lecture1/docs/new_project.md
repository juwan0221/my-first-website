# New Project Guide

## 새 프로젝트 빠른 시작

### 1. 템플릿 복사
```bash
# lecture1 디렉토리에서 실행
cp -r _template_settings [새프로젝트명]
cd [새프로젝트명]
```

### 2. package.json 프로젝트명 변경
```json
{
  "name": "[새프로젝트명]",
  ...
}
```

### 3. 의존성 재설치 (선택)
```bash
# node_modules가 없을 때
npm install
```

### 4. 개발 서버 실행
```bash
npm run dev
# → http://localhost:5173
```

---

## 포함된 패키지 목록

| 패키지 | 버전 | 용도 |
|--------|------|------|
| react | ^19 | UI 라이브러리 |
| react-dom | ^19 | DOM 렌더링 |
| react-router-dom | ^7 | 클라이언트 라우팅 |
| @mui/material | ^7 | UI 컴포넌트 |
| @mui/icons-material | ^7 | 아이콘 |
| @emotion/react | ^11 | CSS-in-JS |
| @emotion/styled | ^11 | 스타일 컴포넌트 |
| @fontsource/roboto | ^5 | Roboto 폰트 |
| vite | ^8 | 빌드 도구 |

---

## 프로젝트 초기 구조 설정

### 기본 디렉토리 생성
```bash
mkdir -p src/components/common
mkdir -p src/components/layout
mkdir -p src/pages
mkdir -p src/hooks
mkdir -p src/utils
```

### 라우터 설정 (main.jsx)
```jsx
import { BrowserRouter } from 'react-router-dom';

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <ThemeProvider theme={theme}>
      <CssBaseline />
      <BrowserRouter>
        <App />
      </BrowserRouter>
    </ThemeProvider>
  </React.StrictMode>
);
```

### App.jsx 라우트 설정
```jsx
import { Routes, Route } from 'react-router-dom';
import HomePage from './pages/HomePage';

function App() {
  return (
    <Routes>
      <Route path="/" element={<HomePage />} />
    </Routes>
  );
}
```

---

## 자주 쓰는 MUI 컴포넌트 임포트

```jsx
import {
  Box, Container, Grid,
  Typography, Button, IconButton,
  TextField, Select, MenuItem,
  Card, CardContent, CardActions,
  AppBar, Toolbar, Drawer,
  Dialog, DialogTitle, DialogContent,
  Snackbar, Alert,
  CircularProgress, LinearProgress,
  Divider, Chip, Avatar,
  List, ListItem, ListItemText
} from '@mui/material';
```

---

## 빌드 및 배포
```bash
# 프로덕션 빌드
npm run build

# 빌드 결과 미리보기
npm run preview

# 빌드 결과물 위치: dist/
```
