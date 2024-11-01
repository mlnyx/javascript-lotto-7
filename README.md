# javascript-lotto-precourse

## 프로젝트 개요

JavaScript를 활용하여 **로또 발매기**를 구현한 미션입니다.
사용자가 입력한 금액에 비례해서 로또를 자동 생성하고,
사용자가 입력한 당첨 번호와 비교해 당첨 통계를 출력하는 기능을 제공합니다.

## 주요 기능

- **구입 금액에 따른 로또 발행**: 입력된 구입 금액을 기준으로 1,000원 단위로 로또 티켓 발행
- **로또 번호 생성**: 1부터 45 사이의 숫자 중 중복되지 않는 6개의 숫자로 로또 번호 생성
- **당첨 번호 추첨**: 당첨 번호 6개와 보너스 번호 1개를 사용자로부터 입력받아 당첨 여부 판정
- **당첨 조건 및 상금**:
  - 1등: 6개 번호 일치 / 2,000,000,000원
  - 2등: 5개 번호 + 보너스 번호 일치 / 30,000,000원
  - 3등: 5개 번호 일치 / 1,500,000원
  - 4등: 4개 번호 일치 / 50,000원
  - 5등: 3개 번호 일치 / 5,000원
- **당첨 통계 및 수익률 계산**: 사용자가 구매한 로또 번호와 당첨 번호를 비교하여 당첨 내역 및 총 수익률을 계산하여 출력

## 구현 기능 목록

### 1. 사용자 입력 처리

- **로또 구입 금액 입력**: 로또 구입 금액을 입력받고, 입력 값이 1,000원 단위로 받을 수 있는 기능 구현
- **당첨 번호 및 보너스 번호 입력**: 당첨 번호 6개와 보너스 번호 1개를 따로 입력 받고, 당첨 번호 같은 경우엔 쉼표(,)로 구분하는 기능 구현

### 2. 로또 번호 생성

- **구매한 로또 번호 생성**: 사용자가 입력한 구입 금액을 기준으로 로또 티켓 수를 계산하여, 각 티켓에 대해 1부터 45 사이의 중복되지 않은 6개의 번호를 생성하는 기능 구현
- **로또 번호 정렬**: 생성된 로또 번호는 오름차순으로 정렬하여 저장하는 기능 구현

### 3. 당첨 결과 판별

- **당첨 번호 비교**: 사용자가 구매한 로또 번호와 당첨 번호를 비교하여 일치하는 번호 수를 확인하는 기능 구현
- **당첨 등수 결정**: 번호 일치 개수와 보너스 번호 일치 여부를 바탕으로 당첨 등수(1등~5등)를 결정하는 기능 구현
- **당첨 통계 계산**: 각 등수별 당첨 개수를 집계하고, 구입 금액 대비 총 수익률을 계산하는 기능 구현

### 4. 결과 출력

- **구매한 로또 번호 출력**: 사용자가 구매한 로또 티켓 번호를 출력하는 기능 구현
- **당첨 결과 출력**: 각 등수별 당첨 개수와 상금을 출력하며, 총 수익률을 소수점 둘째 자리까지 반올림하여 출력하는 기능 구현

### 5. 에러 처리

- **입력 오류 처리\_1**: 로또 구입 금액이 1,000원 단위가 아닐 경우 "[ERROR]"로 시작하는 에러 메시지를 출력하는 기능 구현
- **입력 오류 처리\_2**: 당첨 번호 입력이 잘못되었을 경우 "[ERROR]"로 시작하는 에러 메시지를 출력하는 기능 구현
- **번호 범위 검증**: 로또 번호가 1부터 45 사이인지 확인하며, 범위를 벗어난 경우 "[ERROR]"로 시작하는 에러 메시지를 출력하는 기능 구현

## 각 파일 역할 정리

- Lotto.js (Lotto 클래스):

로또 번호와 관련된 모든 로직 처리
로또 번호 유효성 검사 (#validate 메서드)
당첨 여부 확인, 번호 생성 등 번호와 관련된 기능 추가

- App.js:

Lotto 클래스와 상호작용하여 게임의 흐름 관리
사용자 입력(구입 금액 입력 등)과 결과 출력 처리
게임 진행에 필요한 로또 인스턴스 생성 및 관리
