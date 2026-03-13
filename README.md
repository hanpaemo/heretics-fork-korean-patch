# Heretic's Fork 한글패치

![Heretic's Fork](https://store-images.s-microsoft.com/image/apps.51990.14585991086498496.73c9ffcf-bc3b-4d73-9cfa-b2acf0d00ca3.2e3fe94f-0edd-4e5f-99f1-ded0e2e7e9b3)

공식 한국어 지원이 없는 **Heretic's Fork**의 비공식 한글패치입니다.

카드 설명, 도전 과제, 캐릭터 대화, 이메일, 스토리 텍스트 등 게임 내 거의 모든 텍스트를 번역하고, 한국어 전용 폰트(Do Hyeon)를 적용한 완성 버전입니다.

## 번역 범위

| 분류 | 내용 | 상태 |
|------|------|------|
| UI / 메뉴 | 옵션, 메인 메뉴, 플레이리스트, 이메일, 튜토리얼 등 | ✅ 완료 |
| 카드 설명 | 공격/방어/지원 카드 이름, 설명, 사용 텍스트, 증폭 효과 | ✅ 완료 |
| 도전 과제 | 구역별 도전 과제, 잠금 해제 조건, 보상 설명 | ✅ 완료 |
| 캐릭터 대화 | Denny, Fred, Klippy, Gilbert 등 캐릭터 대사 전체 | ✅ 완료 |
| 이메일 / 스토리 | 인게임 이메일, 스토리 텍스트, 엔딩 메시지 | ✅ 완료 |
| DLC 콘텐츠 | 변종(Variant), 추가 캐릭터, DLC 카드 및 도전 과제 | ✅ 완료 |
| **합계** | **1,350개 항목** | ✅ |

## 다운로드

👉 [GitHub Releases에서 다운로드](https://github.com/hanpaemo/heretics-fork-korean-patch/releases)

## 설치 방법

### 1단계 — 다운로드
위 링크에서 `한패모_HereticksFork-한글패치.zip`을 다운로드합니다.

### 2단계 — 압축 해제
게임 설치 폴더에 **덮어쓰기**로 압축을 해제합니다.
```
기본 경로: C:\Program Files (x86)\Steam\steamapps\common\Heretic's Fork
```

### 3단계 — data.win 패치 실행
게임 폴더에서 `patch_datawin.py`를 실행합니다.
```
python patch_datawin.py
```

⚠️ **Python 3.10 이상**과 **Pillow**, **numpy** 라이브러리가 필요합니다:
```
pip install Pillow numpy
```

이 스크립트는 게임의 `data.win` 파일에서 일본어 폰트 비트맵을 한글로 교체합니다.
원본 파일은 `data.win.bak`으로 자동 백업됩니다.

### 4단계 — 게임 실행
게임을 실행하고 **Options → Language**에서 **"日本語 (Japanese)"**를 선택합니다.

> 일본어 칼럼을 한국어로 교체한 방식이므로 일본어를 선택해야 합니다.

## 자주 묻는 질문

**Q. 왜 일본어를 선택해야 하나요?**
A. 게임에 한국어 언어 옵션이 없으므로, 기존 일본어(JAPANESE) 칼럼을 한국어로 교체하는 방식을 사용합니다. 게임에서 "日本語"를 선택하면 한국어가 표시됩니다.

**Q. data.win 패치를 왜 별도로 실행해야 하나요?**
A. 이 게임은 GameMaker YYC(네이티브 컴파일) 엔진을 사용하며, 폰트가 비트맵 스프라이트로 `data.win`에 내장되어 있습니다. 단순히 TTF 파일만 교체해서는 한글이 표시되지 않고, 내장된 폰트 비트맵 텍스처를 직접 수정해야 합니다.

**Q. Python이 없어요 / 스크립트 실행이 어려워요**
A. 추후 실행 파일(.exe) 형태의 원클릭 설치 프로그램을 제공할 예정입니다. 그 전까지는 [Python 공식 사이트](https://www.python.org/downloads/)에서 설치 후 위 명령어를 실행해주세요.

**Q. Steam 파일 무결성 검사 후 번역이 사라졌어요**
A. 무결성 검사는 패치 파일을 원본으로 복원하므로, 검사 후 패치를 다시 설치하시면 됩니다.

**Q. 게임 업데이트 후 번역이 안 돼요**
A. 게임 업데이트에 따라 패치 재설치가 필요할 수 있습니다. GitHub에서 최신 버전을 확인해주세요.

## 기술 정보

- **게임 엔진**: GameMaker (YYC — YoYo Compiler, 네이티브 C++)
- **번역 방식**: CSV 칼럼 교체 (JAPANESE → Korean) + data.win FONT/TXTR 청크 직접 패치
- **텍스처 포맷**: GameMaker fioq (커스텀 QOI) + BZ2 압축 (QOZ2)
- **한국어 폰트**: Do Hyeon (도현) — Google Fonts 오픈소스
- **텍스트 렌더링**: Scribble 라이브러리 (jujuadams)
- **지원 버전**: Steam PC (Windows)
- **번역 항목**: 1,350개 (FULL 기준)
- **사용 한글 글리프**: 865자 (번역에 실제 사용된 글자만 렌더링)
- **패치 버전**: v1.0

## 변경 이력

### v1.0 (2026-03-13)
- 최초 배포 — 1,350개 항목 번역
- 카드 설명, 도전 과제, 캐릭터 대화, 이메일, 스토리, DLC 전체 포함
- 위키 참조 번역 퀄리티 검수 (용어 통일, 캐릭터 말투 보존)
- 한국어 전용 폰트 Do Hyeon (도현) 적용
- data.win FONT/TXTR 직접 패치 — 한글 비트맵 글리프 자동 생성

## 오류 제보

번역 오류나 누락된 텍스트를 발견하시면 아래로 알려주세요.
- [GitHub Issues](https://github.com/hanpaemo/heretics-fork-korean-patch/issues)
- [한패모 블로그](https://hanpaemo.blogspot.com) 댓글

## 제작

**한패모** (hanpaemo) — 한국어 비공식 게임 번역 프로젝트
