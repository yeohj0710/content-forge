# projects/

작업 단위 폴더. 이 안의 내용물은 git에 올라가지 않는다 (클라이언트 에셋·대용량 산출물 보관용).

새 작업 폴더 구조 (에이전트가 자동 생성):

```
YYYYMMDD-작업명/
├── brief.md           요청 원문 + 확정 사양
├── blueprint.md       설계도
├── asset-manifest.md  에셋 체크리스트
├── assets/
│   ├── provided/      사람이 수급한 원본 에셋 (P##)
│   ├── generated/     GPT Image 생성 결과 (G##)
│   └── prompts/       생성 프롬프트 txt (G##/V##, 이미지·클립당 1개)
│       └── G##-*-attachments/  프롬프트와 함께 업로드할 첨부 에셋 (에이전트가 세팅)
├── edit-guide.md      (영상 트랙) 편집 가이드
└── output/            최종 export / clips/
```
