# 8주차 실습 가이드 — 포트폴리오 허브

> 실습 목표 시간: **1시간 30분**. 시간이 부족하면 7단계(개인화)는 최소한으로 하고 배포·PR까지 먼저 끝내세요.

## ⏱️ 시간 배분

| 단계 | 내용 | 목표 시간 |
|:---:|---|:---:|
| 1~3 | Fork, Codespaces, `dev` 브랜치 | 5분 |
| 4 | 내 결과물 링크 정리 (`links.md`) | 15분 |
| 5~6 | Agent로 생성 + 미리보기 | 20분 |
| 7~8 | 개인화 + 공개 전 점검 | 20분 |
| 9~13 | README, 배포, 태그, PR | 20분 |
| — | 여유분 | 10분 |

---

## 1. Fork

1. [`hitech26-w8-portfolio`](https://github.com/kopo-kangseo-cybersec/hitech26-w8-portfolio) 원본 저장소에서 **Fork** 클릭
2. Owner가 **내 계정**인지 확인하고 **Create fork**

## 2. Codespaces 열기

1. 내 Fork 저장소에서 **Code → Codespaces → Create codespace on main**
2. 브라우저에 VS Code 화면이 뜰 때까지 기다립니다 (1~2분)

## 3. `dev` 브랜치 만들기

하단 터미널에서:

```bash
git checkout -b dev
```

> `main`은 원본 그대로 보존, 작업은 `dev`에서, 배포는 `gh-pages`에서 — 3주차부터 써온 방식 그대로입니다.

## 4. 내 결과물 링크 정리하기

1. `links.md`를 열고 표를 채웁니다.
2. 링크는 새 탭으로 **직접 열어서 동작하는지** 확인하면서 채우세요.
   - 내 저장소 목록: `https://github.com/내아이디?tab=repositories`
   - 각 저장소의 **Settings → Pages**에 배포 주소가 표시됩니다.
3. 배포하지 못한 결과물은 사이트 주소에 `준비 중`이라고 적습니다.
4. **한 줄 소감은 직접** 씁니다.

다 채웠으면 커밋해둡니다:

```bash
git add links.md
git commit -m "docs: 내 결과물 링크 정리"
```

## 5. Copilot Agent로 생성하기

1. Copilot Chat을 열고 모드를 **Agent**로 바꿉니다.
2. 아래 프롬프트를 붙여넣고 실행합니다. `#links.md`는 파일을 첨부하는 표시입니다. (`#`을 입력하면 파일 목록이 뜹니다)

```text
#links.md 파일에 정리한 내 결과물로 포트폴리오 사이트를 만들어줘.

- 파일: index.html, style.css (자바스크립트는 꼭 필요할 때만)
- 상단: 내 이름과 한 줄 소개, "웹콘텐츠 제작 하이테크 과정 2026" 표시
- 결과물마다 카드 하나: 주차, 제목, 사용한 AI 방식, 한 줄 소감,
  [사이트 보기] [코드 보기] 버튼
- 사이트 주소가 "준비 중"인 결과물은 버튼 대신 "준비 중" 배지 표시
- 하단: 8주 동안 AI 활용 방식이 어떻게 바뀌었는지 보여주는 간단한 타임라인
- 모바일에서도 보기 좋은 반응형
- 외부 링크는 새 탭으로 열고 rel="noopener noreferrer" 붙이기
- links.md에 없는 개인정보(이메일, 전화번호 등)는 절대 넣지 말 것
```

3. Agent가 파일을 만들면 **Keep**(또는 Accept)으로 반영합니다.

## 6. 미리보기

터미널에서:

```bash
python3 -m http.server 8000
```

오른쪽 아래에 뜨는 알림에서 **Open in Browser**를 누르면 새 탭에서 페이지가 열립니다. (알림을 놓쳤다면 하단 **PORTS** 탭 → 8000번 → 지구본 아이콘)

✅ **체크포인트**
- 카드 개수가 `links.md`의 결과물 수와 같은가요?
- [사이트 보기] 버튼을 몇 개 눌러봤을 때 내 결과물이 실제로 열리나요?
- "준비 중" 결과물에 배지가 보이나요?

미리보기를 끝낼 때는 터미널에서 `Ctrl + C`를 누릅니다.

## 7. 개인화 (내 것으로 만들기)

아래 중 **하나 이상**은 꼭 바꿔보세요. 직접 고쳐도 되고, Agent에게 요청해도 됩니다.

```text
전체 색상을 남색과 민트 계열로 바꿔줘.
```

```text
카드에 마우스를 올리면 살짝 떠오르는 효과를 넣어줘.
```

```text
가장 마음에 드는 결과물 카드에 "Best" 표시를 달아줘. 지뢰찾기 카드야.
```

- 한 줄 소개, 소감 문구는 직접 다듬어보세요.
- 바꾼 내용은 9단계 README의 "커스터마이징한 부분"에 적습니다.

## 8. 공개 전 점검 🔒

포트폴리오는 누구나 볼 수 있는 페이지이고, 여기서 내 다른 결과물로 바로 이동할 수 있습니다. 올리기 전에 확인하세요.

- [ ] 페이지에 이메일·전화번호·학번 등 개인정보가 없다
- [ ] 7주차 감정일기에 실제 개인적인 내용이 남아 있지 않다 (테스트용 글이라도 공개되어도 괜찮은 내용인지 확인)
- [ ] 연결한 링크가 모두 내 결과물로 정상 연결된다 (엉뚱한 주소, 깨진 링크 없음)

> 💡 `target="_blank"`로 새 탭을 열 때 `rel="noopener"`를 붙이는 건, 새로 열린 페이지가 원래 페이지를 조작하지 못하게 막는 습관입니다. 최신 브라우저는 기본으로 막아주지만, 명시해두는 게 안전한 작성법입니다.

## 9. README.md 작성하기

`README.md`의 각 섹션을 채웁니다. 짧아도 괜찮습니다.

## 10. 커밋 & 푸시

```bash
git add .
git commit -m "feat: 포트폴리오 허브 완성"
git push -u origin dev
```

## 11. GitHub Pages 배포

```bash
git checkout -b gh-pages
git push -u origin gh-pages
git checkout dev
```

1. 내 Fork 저장소 → **Settings → Pages**
2. Source: **Deploy from a branch** / Branch: **gh-pages**, 폴더 **/(root)** → **Save**
3. 1~2분 뒤 표시되는 주소로 접속해 확인합니다
   - `https://내아이디.github.io/hitech26-w8-portfolio/`

## 12. 태그 & Release

```bash
git tag v1.0
git push origin v1.0
```

GitHub 저장소 → **Releases → Draft a new release** → 태그 `v1.0` 선택 → 한두 줄 설명 작성 → **Publish release**

## 13. PR 제출

1. 내 Fork 저장소에서 **Contribute → Open pull request**
2. 보내는 브랜치가 **`dev`** 인지 확인
3. 자동으로 뜨는 템플릿을 채우고 **Create pull request**

---

## 🚀 선택 도전 (시간이 남는다면)

- 결과물 화면을 캡처해서 `images/` 폴더에 넣고, 카드에 썸네일로 보여주기
- 다크 모드 전환 버튼 넣기
- 결과물 정보를 `projects.json`으로 분리하고, 자바스크립트로 불러와 카드를 그리게 바꾸기 — 나중에 결과물이 늘어도 데이터만 고치면 됩니다

## 🧹 실습이 끝나면

Codespaces는 켜져 있는 동안 무료 사용량을 씁니다. 작업이 끝났으면 [github.com/codespaces](https://github.com/codespaces)에서 이번 Codespace를 **Stop** 또는 **Delete** 하세요. (코드는 이미 푸시했으니 지워도 안전합니다)
