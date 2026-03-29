# Code Convention

## 파일 및 디렉토리 명명 규칙
- **컴포넌트 파일**: PascalCase → `UserProfile.jsx`
- **유틸리티/훅 파일**: camelCase → `useAuth.js`, `formatDate.js`
- **페이지 파일**: PascalCase + Page → `HomePage.jsx`
- **스타일 파일**: 컴포넌트명 동일 → `UserProfile.module.css`

## 디렉토리 구조
```
src/
├── components/      # 재사용 컴포넌트
│   ├── common/      # 공통 컴포넌트 (Button, Modal 등)
│   └── layout/      # 레이아웃 컴포넌트
├── pages/           # 라우트 페이지
├── hooks/           # 커스텀 훅
├── utils/           # 유틸리티 함수
├── assets/          # 이미지, 폰트 등
├── theme.js         # MUI 테마 설정
└── main.jsx         # 앱 진입점
```

## 컴포넌트 작성 규칙

### 함수형 컴포넌트 사용
```jsx
// ✅ 올바른 방식
const UserCard = ({ name, email }) => {
  return (
    <Card>
      <Typography>{name}</Typography>
    </Card>
  );
};

export default UserCard;
```

### Props 구조분해
```jsx
// ✅ 올바른 방식
const Button = ({ label, onClick, disabled = false }) => { ... };

// ❌ 잘못된 방식
const Button = (props) => { const label = props.label; ... };
```

### 이벤트 핸들러 명명
```jsx
// handle + 이벤트명
const handleClick = () => { ... };
const handleSubmit = () => { ... };
const handleChange = (e) => { ... };
```

## import 순서
```jsx
// 1. React
import React, { useState, useEffect } from 'react';

// 2. 외부 라이브러리
import { useNavigate } from 'react-router-dom';
import { Button, Typography } from '@mui/material';

// 3. 내부 컴포넌트/유틸
import UserCard from '../components/UserCard';
import { formatDate } from '../utils/formatDate';

// 4. 스타일
import './styles.css';
```

## MUI sx prop 사용 규칙
```jsx
// ✅ sx prop 사용 (인라인 스타일 금지)
<Box sx={{
  display: 'flex',
  gap: 2,
  p: 3,
  borderRadius: 1
}}>

// ❌ 인라인 스타일 금지
<Box style={{ display: 'flex', gap: '16px' }}>
```

## 상태 관리
```jsx
// useState: 로컬 상태
const [isOpen, setIsOpen] = useState(false);

// 복잡한 상태는 객체로 묶기
const [form, setForm] = useState({ name: '', email: '' });
const handleFormChange = (field) => (e) => {
  setForm(prev => ({ ...prev, [field]: e.target.value }));
};
```

## 주석 규칙
- 코드가 명확하면 주석 불필요
- 복잡한 로직에만 한국어 주석 작성
- TODO/FIXME 형식 사용: `// TODO: API 연동 필요`
