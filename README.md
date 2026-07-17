# Content Forge

**Claude Code + Figma MCP / Higgsfield MCP + 사람의 협업으로, 어떤 콘텐츠든 "있어 보이게" 만드는 워크플로우.**

단일 AI 에이전트로도 전체 제작이 가능하지만, 이 프로젝트는 각 단계를 가장 잘하는 주체에게 배분한다:

- **Claude Code** — 설계, 에셋 요구 명세, Figma 조립(편집 가능한 텍스트 레이어), 영상 클립 생성·편집 설계
- **GPT Image 등 이미지 모델** — 텍스트 없는 배경/비주얼 생성 (사람이 실행)
- **사람** — 에셋 수급(누끼·로고·실사), 이미지 생성 실행, 영상 후편집·자막

## 사용법

1. Claude Code 새 세션을 연다 (작업 디렉토리: 이 저장소).
2. `prompts/bootstrap-image.txt`(이미지) 또는 `prompts/bootstrap-video.txt`(영상)의 내용을 붙여넣고,
   바로 아래에 작업 요청을 이어 적는다.
3. 에이전트가 [AGENTS.md](AGENTS.md)를 읽고 설계 → 에셋 매니페스트 순으로 진행한다.
4. 매니페스트대로 에셋을 준비해 `projects/<작업>/assets/`에 넣어주면, 에이전트가 검수 후 제작에 들어간다.

## 핵심 원칙 (요약)

1. **텍스트-비주얼 분리** — 생성 모델 산출물에는 텍스트 금지. 텍스트는 Figma 레이어/영상 자막(후편집)으로만.
2. **설계 우선** — 도구를 만지기 전에 blueprint부터.
3. **에셋은 과하게** — 풍부한 에셋이 곧 퀄리티.
4. **프롬프트는 파일로** — 이미지 1장 = 프롬프트 txt 1개. 수정은 프롬프트 교체 → 재생성 → 갈아끼우기.

전체 워크플로우는 [AGENTS.md](AGENTS.md) 참고.

## 구조

```
prompts/     부트스트랩 프롬프트 (새 세션 시작용)
templates/   blueprint / asset-manifest / image-prompt / edit-guide 템플릿
projects/    작업 단위 폴더 (git 미추적 — 클라이언트 에셋·산출물 보관)
```
