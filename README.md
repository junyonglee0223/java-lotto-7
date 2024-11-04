# java-lotto-precourse

## 주요 기능
1. 로또 구매 및 발행
2. 당첨 번호 입력 및 검증
3. 당첨 내역 및 수익률 계산

## 기능 목록

1. **Lotto 객체 구체화**
   - 로또 번호를 관리하는 `Lotto` 객체를 구현합니다.
   - `Lotto` 객체가 직접 랜덤 번호를 생성하지 않도록, 랜덤 숫자 생성 기능은 `LottoGenerator` 객체로 분리하여 구현합니다.
   - 검증 로직 추가: 로또 번호가 6개여야 하며, 각 번호는 1부터 45 사이의 값이어야 하고 중복되지 않아야 합니다. 이를 `validate` 메서드에서 확인합니다.
   - **디렉토리**: `lotto.domain`

2. **Prize 객체 구현**
   - 당첨 여부와 상금을 관리하는 `Prize` 객체를 구현합니다.
   - `Prize` 객체는 일치하는 숫자 개수에 따른 당첨 금액을 `enum` 방식으로 관리하여, 각 등수의 조건과 상금을 설정합니다.
   - 당첨금액에 대한 인덱스를 추가합니다.
   - **디렉토리**: `lotto.domain`

3. **입력 객체 구현**
   - 사용자의 입력을 관리하는 `LottoInput` 객체를 구현합니다.
   - 구입 금액, 당첨 번호 리스트, 보너스 번호를 입력받고 검증합니다.
   - **디렉토리**: `lotto.input`

4. **입력 객체 테스트 구현**
   - `LottoInputTest` 클래스에서 `LottoInput` 객체의 입력 검증 로직에 대한 테스트를 수행합니다.
   - 테스트는 `assertThatThrownBy`를 사용하여 예외 발생을 검증합니다.:
      - 올바른 형식의 구입 금액 입력 시 정상 처리
      - 구입 금액이 숫자가 아닐 경우 예외 발생
      - 당첨 번호 개수가 6개가 아닐 때 예외 발생
      - 잘못된 형식(숫자가 아닌 경우)의 당첨 번호 입력 시 예외 발생
      - 잘못된 형식(숫자가 아닌 경우)의 보너스 번호 입력 시 예외 발생
   - **디렉토리**: `lotto.input`

5. **입력 금액 검증 객체 구현**
   - 구입 금액이 1,000원 단위인지 검증하는 `PurchaseValidator` 객체를 구현합니다.
   - 잘못된 입력이 들어올 경우 예외를 발생시킵니다.
   - **디렉토리**: `lotto.util`

6. **구매 내역 출력 객체 구현**
   - 사용자가 구매한 로또 번호 리스트를 출력하는 `LottoPurchase` 객체를 구현합니다.
   - 구매한 로또 번호는 오름차순으로 정렬하여 출력합니다.
   - **디렉토리**: `lotto.purchase`

7. **당첨 내역 출력 객체 구현**
   - `LottoResult` 객체를 통해 사용자가 구매한 로또 번호와 당첨 번호, 보너스 번호를 비교하여 일치하는 번호 개수별로 당첨 내역을 출력합니다.
   - **디렉토리**: `lotto.result`

8. **수익률 출력 객체 구현**
   - 수익률을 계산하고 출력하는 `ProfitCalculator` 객체를 구현합니다.
   - 총 구입 금액과 당첨금 총액을 바탕으로 수익률을 소수점 둘째 자리까지 계산하여 출력합니다.
   - **디렉토리**: `lotto.service`