# terminal-itda

폰에서 내 PC의 터미널과 AI(Claude Code, Codex)를 이어서 쓰는 프로그램입니다.
PC에 설치하고, 폰 앱으로 QR을 찍으면 연결됩니다.

## 설치 (터미널에 한 줄)

**macOS**
```sh
curl -fsSL https://github.com/da-itda/terminal-itda/releases/latest/download/install.sh | sh
```

**Windows** — 준비 중  
**Linux** — 준비 중

설치 스크립트가 하는 일
1. 이 PC(OS·CPU)에 맞는 itda를 받아 설치합니다. 이미 있으면 최신 버전으로 업데이트합니다.
2. Claude Code, Codex, herdr를 확인합니다. 없으면 설치할지 물어보고, 오래된 버전은 업데이트할지 물어봅니다.
3. 백그라운드 실행과 터미널 연동을 설정하고, 폰 연결용 QR을 보여 줍니다.

## 업데이트
```sh
itda update
```

이 저장소에는 설치 파일만 있습니다.
