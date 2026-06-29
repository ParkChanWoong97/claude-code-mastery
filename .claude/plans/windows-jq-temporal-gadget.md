# 상태표시줄 설정 계획 (Windows, jq 없이)

## Context
사용자가 Claude Code 상태표시줄에서 모델명, 현재 디렉토리, 컨텍스트 사용률(%), git 브랜치를 ANSI 색상으로 한 줄에 표시하고 싶어함. Windows 환경이므로 jq 의존 없이 PowerShell 내장 기능만 사용해야 함.

## 변경 대상

**파일:** `C:\Users\s_s12\.claude\statusline-command.ps1`  
기존 스크립트를 아래 4개 항목을 출력하도록 교체.

## 구현 내용

| 항목 | ANSI 색상 | 데이터 소스 |
|------|-----------|-------------|
| 모델명 | Cyan (36m) | `display_name` 필드 |
| 디렉토리 | Green (32m) | `cwd` 필드, 홈 경로 `~` 축약, `\` → `/` |
| 컨텍스트 % | Yellow (33m) | `used_percentage`, 없으면 `-` |
| Git 브랜치 | Magenta (35m) | `git -C <cwd> rev-parse --abbrev-ref HEAD` |

- jq **불필요** — PowerShell 내장 `ConvertFrom-Json` 사용
- `settings.json` 변경 없음 — 기존 command 경로 유지

## 출력 예시

```
Claude Sonnet 4.6 | ~/workpaces/claude-code-mastery | ctx:42.3% | main
```
(항목 사이 dim `|` 구분, 각 항목 ANSI 색상 적용)

## 실행 계획

statusline-setup 에이전트(ID: `af23199e44404982f`)가 `statusline-command.ps1`을 직접 수정.

## 검증 방법

Claude Code 터미널에서 새 대화 시작 후 상태표시줄에 4개 항목이 색상과 함께 표시되는지 확인.
