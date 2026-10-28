# Todo Tutorial

[Claude Code Playbook](https://docs.claude-hunt.com) 강의의 실습용 저장소입니다. Next.js 와 shadcn/ui 로 시작하는 작은 Todo 앱을 단계별로 발전시키며 Claude Code 사용법을 익힙니다.

## 프로젝트 소개

브라우저에서 바로 쓰는 단일 페이지 할일(Todo) 앱입니다. 별도 백엔드 없이 할일을 브라우저 `localStorage` 에 저장하므로, 새로고침하거나 다시 방문해도 목록이 유지됩니다.

### 주요 기능

- 할일 추가 · 수정 · 삭제 · 완료 토글
- 우선순위(높음 / 보통 / 낮음), 마감일, 카테고리(업무 / 개인 / 쇼핑) 지정
- 상태 필터(전체 / 진행중 / 완료)와 카테고리 필터
- 텍스트 검색
- 정렬(생성일순 / 이름순 / 마감일순)
- 다크 모드 (`d` 키로 전환)

## 관련 링크

- 강의 본문: https://docs.claude-hunt.com
- 수강생 결과물 공유: https://claude-hunt.com

## 기술 스택

- Next.js 16 (App Router, Turbopack)
- React 19
- Tailwind CSS v4
- shadcn/ui (radix-maia 스타일, taupe 베이스)
- TypeScript / ESLint / Prettier
- 패키지 매니저: bun 1.3.6

## 시작하기

### 사전 준비

- [bun](https://bun.sh) 1.3 이상
- Node.js 20.9 이상 (Next.js 16 요구 사항)

### 실행 방법

```bash
git clone https://github.com/imfact79/todo-tutorial.git
cd todo-tutorial
bun install
bun dev
```

개발 서버는 기본적으로 [http://localhost:3000](http://localhost:3000) 에서 열립니다.

프로덕션 모드로 실행하려면 빌드 후 시작합니다.

```bash
bun run build
bun run start
```

### 자주 쓰는 스크립트

```bash
bun dev            # 개발 서버 실행
bun run build      # 프로덕션 빌드
bun run start      # 빌드 결과 실행
bun run test       # Vitest 테스트 1회 실행
bun run test:watch # Vitest 감시 모드
bun run lint       # ESLint
bun run typecheck  # tsc --noEmit
bun run format     # Prettier 포맷팅
```

> `bun test` 는 bun 내장 테스트 러너를 실행하므로, Vitest 테스트는 반드시 `bun run test` 로 실행하세요.

### 디렉토리 구조

```
app/          # App Router 페이지와 레이아웃
components/   # Todo 컴포넌트 (components/ui 는 shadcn/ui)
hooks/        # useTodos 등 클라이언트 상태 훅
lib/          # 타입 정의와 정렬·검색 유틸
```

## 챕터별 시작 브랜치

각 레슨은 시작 시점의 코드 상태를 브랜치로 제공합니다. 레슨 본문에서 안내하는 브랜치로 전환한 뒤 따라가시면 됩니다.

```shell
git checkout ch02-03
```

## 컴포넌트 추가

shadcn/ui 컴포넌트는 다음과 같이 추가합니다.

```bash
bunx --bun shadcn@latest add button
```

`components/ui` 디렉토리에 컴포넌트가 추가됩니다.

## 컴포넌트 사용

```tsx
import { Button } from "@/components/ui/button";
```

## Contributors

- 토이크레인 - Frontend Developer
