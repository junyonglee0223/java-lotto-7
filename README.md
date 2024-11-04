# java-lotto-precourse

## 주요 기능
1. 로또 구매 및 발행
2. 당첨 번호 입력 및 검증
3. 당첨 내역 및 수익률 계산

## 기능 목록

1. **Lotto 객체 구체화**
   - 로또 번호를 관리하는 `Lotto` 객체를 구현합니다.
   - `Lotto` 객체가 직접 랜덤 번호를 생성하지 않도록, 랜덤 숫자 생성 기능은 `LottoGenerator` 객체로 분리하여 구현합니다.
   - **디렉토리**: `lotto.domain`

2. **Prize 객체 구현**
   - 당첨 여부와 상금을 관리하는 `Prize` 객체를 구현합니다.
   - `Prize` 객체는 일치하는 숫자 개수에 따른 당첨 금액을 `enum` 방식으로 관리하여, 각 등수의 조건과 상금을 설정합니다.
   - **디렉토리**: `lotto.domain`

3. **입력 객체 구현**
   - 사용자의 입력을 관리하는 `LottoInput` 객체를 구현합니다.
   - 구입 금액, 당첨 번호 리스트, 보너스 번호를 입력받고 검증합니다.
   - **디렉토리**: `lotto.input`

4. **입력 금액 검증 객체 구현**
   - 구입 금액이 1,000원 단위인지 검증하는 `PurchaseValidator` 객체를 구현합니다.
   - 잘못된 입력이 들어올 경우 예외를 발생시킵니다.
   - **디렉토리**: `lotto.util`

5. **구매 내역 출력 객체 구현**
   - 사용자가 구매한 로또 번호 리스트를 출력하는 `LottoPurchase` 객체를 구현합니다.
   - 구매한 로또 번호는 오름차순으로 정렬하여 출력합니다.
   - **디렉토리**: `lotto.purchase`

6. **당첨 내역 출력 객체 구현**
   - `LottoResult` 객체를 통해 사용자가 구매한 로또 번호와 당첨 번호, 보너스 번호를 비교하여 일치하는 번호 개수별로 당첨 내역을 출력합니다.
   - **디렉토리**: `lotto.result`

7. **수익률 출력 객체 구현**
   - 수익률을 계산하고 출력하는 `ProfitCalculator` 객체를 구현합니다.
   - 총 구입 금액과 당첨금 총액을 바탕으로 수익률을 소수점 둘째 자리까지 계산하여 출력합니다.
   - **디렉토리**: `lotto.service`