# Design System

## 기술 스택
- **UI 라이브러리**: MUI (Material-UI) v7
- **스타일 엔진**: Emotion (@emotion/react, @emotion/styled)
- **폰트**: Roboto (@fontsource/roboto)

## 컬러 팔레트
| 역할 | 색상 | 코드 |
|------|------|------|
| Primary | Blue | `#1976d2` |
| Secondary | Pink | `#dc004e` |
| Background | White | `#ffffff` |
| Surface | Light Gray | `#f5f5f5` |
| Error | Red | `#d32f2f` |

## 타이포그래피
```js
typography: {
  fontFamily: '"Roboto", "Helvetica", "Arial", sans-serif',
  h1: { fontSize: '2.125rem', fontWeight: 500 },
  h2: { fontSize: '1.5rem', fontWeight: 500 },
  h3: { fontSize: '1.25rem', fontWeight: 500 },
  body1: { fontSize: '1rem' },
  body2: { fontSize: '0.875rem' },
}
```

## 간격 시스템
- 기본 단위: `8px` (theme.spacing(1) = 8px)
- 사용 예: `sx={{ p: 2 }}` → 16px padding

## 컴포넌트 가이드

### 버튼
```jsx
// 주요 액션
<Button variant="contained" color="primary">확인</Button>

// 보조 액션
<Button variant="outlined" color="secondary">취소</Button>

// 텍스트 버튼
<Button variant="text">더보기</Button>
```

### 레이아웃
```jsx
// 컨테이너
<Container maxWidth="lg">

// 그리드
<Grid container spacing={2}>
  <Grid item xs={12} md={6}>
```

### 카드
```jsx
<Card sx={{ borderRadius: 2, boxShadow: 2 }}>
  <CardContent>
    <Typography variant="h5">제목</Typography>
  </CardContent>
</Card>
```

## 반응형 브레이크포인트
| 이름 | 크기 |
|------|------|
| xs | 0px~ |
| sm | 600px~ |
| md | 900px~ |
| lg | 1200px~ |
| xl | 1536px~ |
