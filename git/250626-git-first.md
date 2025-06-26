# TIL - 2025.06.26 (Git & GitHub)

## 1. Shell & Vim 기초

### Shell 명령어
- `ls`, `cd`, `mkdir`, `pwd`, `touch`, `mv`, `cp`, `rm`, `cat`

### Vim 모드
- normal: 명령 입력 (`h`, `j`, `k`, `l`, `dd`, `yy`, `p`, `u`, 등)
- insert: 입력(`i`, `a`, `o`)
- visual: 블록 설정(`v`)
- command-line: 저장/종료(`:w`, `:q`, `:wq`, `:q!`, `:10`)

---

## 2. Markdown 문법 요약
- 제목: `# ~ ######`
- 목록: `-`, `1.`
- 링크: `[텍스트](URL)`
- 코드 블록: \`\`\`언어
- 강조: `_italic_`, `**bold**`, `~~취소선~~`, \`code\`

---

## 3. Git 기본

### Git 구조
- Working Directory → `add` → Staging Area → `commit` → Local Repo → `push` → Remote Repo

### 주요 명령어
```bash
git config --global user.name "이름"
git config --global user.email "이메일"
git clone {repo_url}
git add {파일명}
git commit -m "메시지"
git push origin main
```

### Conventional Commit 예시
- `feat`: 기능 추가
- `fix`: 버그 수정
- `docs`: 문서 작성
- `refactor`, `style`, `test`, `chore` 등
```bash
feat: add login component
fix!: resolve login bug
```

---

## 4. Branch & Merge

### 기본 명령어
```bash
git branch {브랜치명}
git switch {브랜치명}
git merge {브랜치명}
git branch -D {브랜치명}
git diff main {브랜치명}
```

### Merge Conflict 처리
- `vi 파일` → 충돌 해결 후 `git add` → `git commit`
- 또는 `git rebase main`

---

## 5. Pre-commit

- 사전 커밋 체크 도구
```bash
pip install pre-commit
touch .pre-commit-config.yaml
pre-commit install
pre-commit run --all-files
```

---

## 6. Branch 전략

- **Git Flow**: 배포 주기가 있는 복잡한 서비스
- **GitHub Flow**: 간단하고 CI 기반
- **GitLab Flow**: 배포/이슈 대응 중심

---

## 7. Git & 협업

### Issue 관리
- 기능/버그/질문 분류, 템플릿/레이블 사용
- 마일스톤으로 스프린트 주기 관리

### Projects & Wiki
- 스크럼 보드 형태로 이슈 관리
- 문서화는 `wiki`로 분리

### PR 과정
1. `fork` & `clone`
2. 작업 후 `push` & PR 생성
3. 코드 리뷰 & 수정
4. `approve` → 팀장 merge

---

## 8. 실수 복구 명령

- `git restore {파일}`: 워킹 디렉토리 복구
- `git reset HEAD {파일}`: Staging 해제
- `git commit --amend`: 마지막 커밋 메시지 수정
- `git reset --hard HEAD~n`: n개 커밋 삭제
- `git revert HEAD~n..`: 커밋 되돌리기
- `git stash`: 변경사항 임시 저장

---

## 9. 마무리

- `.gitignore`: 추적 제외 설정
- `.ipynb` 변경사항 추적 어려움 → `.py`로 변환 권장
- 매일 TIL 작성하며 git 습관화하기
