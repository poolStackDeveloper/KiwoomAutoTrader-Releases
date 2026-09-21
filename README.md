# Kiwoom Auto Trader — Windows 배포

이 저장소는 실행 파일과 업데이트 배포 전용입니다. 소스코드는 별도의 비공개 저장소에서 관리합니다.

## 실행

**[KiwoomAutoTrader.Updater.exe 다운로드](https://github.com/poolStackDeveloper/KiwoomAutoTrader-Releases/releases/latest/download/KiwoomAutoTrader.Updater.exe)**

Windows x64에서 위 파일 하나를 실행하세요. .NET 8 런타임을 포함하므로 별도 설치가 필요하지 않습니다.

1. 실행할 때 최신 버전을 확인합니다.
2. 새 버전은 서명·SHA-256 확인 후 자동 설치합니다.
3. 거래 프로그램을 실행합니다. 모의·실전 모두 연결·동기화가 완료되면 주문 허용 토글은 기본 ON이며, 자동매매는 ‘시작’ 버튼을 눌러야 실행됩니다.
4. 실행 중에는 프로그램의 **업데이트 확인** 버튼으로 새 버전과 변경 사항을 확인하고 설치할 수 있습니다.

프로그램 실행 중에는 외부 업데이터가 강제 종료하지 않습니다. 앱 안에서 업데이트하려면 자동매매 중지·주문 잠금 후 미체결 및 V1 보유 포지션을 정리하세요. 설정·계좌정보·거래 기록은 업데이트 과정에서 유지됩니다.

일반 ‘중지’는 자동매매만 멈추며 주문 토글 상태는 유지합니다. 토글 OFF는 주문과 자동매매를 함께 잠급니다. 긴급 중지·연결 장애 시에도 토글은 OFF가 됩니다. NoTrade 전략은 시작해도 주문하지 않으며, 다른 전략도 조건을 만족할 때만 주문합니다.

다운로드 및 변경 사항: [Releases](https://github.com/poolStackDeveloper/KiwoomAutoTrader-Releases/releases)

## 저장 위치

- 계좌 설정·거래 DB: `%LOCALAPPDATA%\KiwoomAutoTrader` (민감 payload는 Windows DPAPI 암호화)
- 프로그램 버전·업데이트: `%LOCALAPPDATA%\KiwoomAutoTraderUpdater`

인터넷이 끊기면 기존 설치가 있는 경우 검증한 기존 버전을 실행합니다. 첫 설치에는 인터넷이 필요합니다. 업데이트 파일의 RSA 서명 검증은 Windows Authenticode 코드 서명과 별개이며, 실행 파일에 Authenticode 서명은 적용되지 않았습니다.

## 모의투자

처음에는 키움 REST API의 모의투자용 App Key·Secret을 프로그램 설정에서 등록하세요. 모의·실전 모두 계좌번호 8자리 또는 10자리를 그대로 입력하며 하이픈 입력도 가능합니다. 숫자를 임의로 덧붙이지 마세요. 키·계좌정보를 GitHub Issue나 댓글에 올리지 마세요.

기본 전략은 NoTrade입니다. OpeningRangeMomentumV1은 설정에서 명시적으로 선택해야 합니다. 실제 키움 서버의 주문·체결 연동과 전략 수익성 검증은 별도이며, 포함된 합성 백테스트 결과는 기대수익이 아닙니다.
