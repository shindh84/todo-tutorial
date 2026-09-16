# Todo Tutorial

[Claude Code Playbook](https://docs.claude-hunt.com) 강의의 실습용 저장소입니다. Next.js 와 shadcn/ui 로 시작하는 작은 Todo 앱을 단계별로 발전시키며 Claude Code 사용법을 익힙니다.

## 프로젝트 소개

할 일을 추가·완료 토글·수정·삭제할 수 있는 Todo 앱입니다. Server Components 중심으로 구성하고 클라이언트 상태는 최소화하는 방식으로 구현되어 있으며, 다음 기능을 제공합니다.

- 우선순위(높음/보통/낮음), 마감일, 카테고리(업무/개인/쇼핑) 지정
- 제목 검색, 카테고리·완료 상태별 필터링
- 생성일순 / 이름순 / 마감일순 정렬
- 항목 더블 클릭으로 바로 수정
- `d` 키로 다크 모드 전환
- 브라우저 `localStorage`에 목록 자동 저장

## 관련 링크

- 강의 본문: https://docs.claude-hunt.com
- 수강생 결과물 공유: https://claude-hunt.com

## 기술 스택

- Next.js 16 (App Router, Turbopack)
- React 19
- Tailwind CSS v4
- shadcn/ui (radix-mira 스타일, taupe 베이스, phosphor 아이콘)
- TypeScript / ESLint / Prettier
- Vitest / Testing Library
- 패키지 매니저: bun

## 시작하기

### 요구 사항

- bun (`packageManager`/lockfile 기준 최신 안정 버전)

### 설치 및 실행

```bash
bun install
bun dev
```

개발 서버는 기본적으로 [http://localhost:3000](http://localhost:3000) 에서 열립니다.

자주 쓰는 스크립트:

```bash
bun dev            # 개발 서버 실행
bun run build      # 프로덕션 빌드
bun run start      # 빌드 결과 실행
bun run lint       # ESLint
bun run typecheck  # tsc --noEmit
bun run format     # Prettier 포맷팅
bun run test       # Vitest 테스트 실행
```

## 프로젝트 구조

```
app/                    # App Router 엔트리 (page.tsx, layout.tsx, globals.css)
components/             # Todo 관련 컴포넌트 + shadcn/ui 컴포넌트(components/ui)
hooks/use-todos.ts      # Todo 상태 관리 및 localStorage 동기화
lib/types.ts            # Todo, Priority, Category 등 도메인 타입
lib/todo-utils.ts       # 정렬·검색 로직
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
