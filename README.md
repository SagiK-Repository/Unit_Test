문서정보 : 2023.01.05. 작성, 작성자 [@SAgiKPJH](https://github.com/SAgiKPJH)

<br>

# Unit Test - 생산성과 품질을 위한 단위 테스트 원칙과 패턴

<img src="https://user-images.githubusercontent.com/66783849/210682313-e7e3693f-6523-4d4f-87ec-6e528fb5d5b5.png" width="250">

### 목적
- 책 [Unit Test - 생산성과 품질을 위한 단위 테스트 원칙과 패턴]를 읽고 요약한다.

### 목표

- [x] [1부. 더 큰 그림](https://github.com/SagiK-Repository/Unit_Test/blob/main/README.md#1%EB%B6%80-%EB%8D%94-%ED%81%B0-%EA%B7%B8%EB%A6%BC)
  - [x] [1장. 단위 테스트 목표](https://github.com/SagiK-Repository/Unit_Test/blob/main/README.md#1%EC%9E%A5-%EB%8B%A8%EC%9C%84-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%AA%A9%ED%91%9C)
  - [x] [2장. 단위 테스트란 무엇인가](https://github.com/SagiK-Repository/Unit_Test/blob/main/README.md#2%EC%9E%A5-%EB%8B%A8%EC%9C%84-%ED%85%8C%EC%8A%A4%ED%8A%B8%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80)
  - [x] [3장. 단위 테스트 구조](https://github.com/SagiK-Repository/Unit_Test/blob/main/README.md#3%EC%9E%A5-%EB%8B%A8%EC%9C%84-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EA%B5%AC%EC%A1%B0)
- [x] [2부. 개발자에게 도움이 되는 테스트 만들기](https://github.com/SagiK-Repository/Unit_Test/blob/main/README.md#2%EB%B6%80-%EA%B0%9C%EB%B0%9C%EC%9E%90%EC%97%90%EA%B2%8C-%EB%8F%84%EC%9B%80%EC%9D%B4-%EB%90%98%EB%8A%94-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0)
  - [x] [4장. 좋은 단위 테스트의 4대 요소](https://github.com/SagiK-Repository/Unit_Test/blob/main/README.md#4%EC%9E%A5-%EC%A2%8B%EC%9D%80-%EB%8B%A8%EC%9C%84-%ED%85%8C%EC%8A%A4%ED%8A%B8%EC%9D%98-4%EB%8C%80-%EC%9A%94%EC%86%8C)
  - [x] [5장. 목과 테스트 취약성](https://github.com/SagiK-Repository/Unit_Test/blob/main/README.md#5%EC%9E%A5-%EB%AA%A9%EA%B3%BC-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%B7%A8%EC%95%BD%EC%84%B1)
  - [x] [6장. 단위 테스트 스타일](https://github.com/SagiK-Repository/Unit_Test/blob/main/README.md#6%EC%9E%A5-%EB%8B%A8%EC%9C%84-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%8A%A4%ED%83%80%EC%9D%BC)
  - [x] [7장. 가치 있는 단위 테스트를 위한 리팩터링](https://github.com/SagiK-Repository/Unit_Test/blob/main/README.md#7%EC%9E%A5-%EA%B0%80%EC%B9%98-%EC%9E%88%EB%8A%94-%EB%8B%A8%EC%9C%84-%ED%85%8C%EC%8A%A4%ED%8A%B8%EB%A5%BC-%EC%9C%84%ED%95%9C-%EB%A6%AC%ED%8C%A9%ED%84%B0%EB%A7%81)
- [ ] 3부. 통합 테스트
  - [ ] 8장. 통합 테스트를 하는 이유
  - [ ] 9장. 목 처리에 대한 모범 사례
  - [ ] 10장. 데이터베이스 테스트
- [ ] 4부. 단위 테스트 안티 패턴

### 제작자
[@SAgiKPJH](https://github.com/SAgiKPJH)

### 참조

- [Unit Test - 생산성과 품질을 위한 단위 테스트 원칙과 패턴](http://www.yes24.com/Product/Goods/104084175)
- [테스트 마스터하기(요약)](https://velog.io/@jkijki12/%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%A7%88%EC%8A%A4%ED%84%B0%ED%95%98%EA%B8%B0-1-%EB%8B%A8%EC%9C%84-%ED%85%8C%EC%8A%A4%ED%8A%B8%EC%9D%98-%EB%AA%A9%ED%91%9C)

<br><br>

---

<br><br>

# 1부. 더 큰 그림

## 1장. 단위 테스트 목표

### 단위테스트
<img src="https://user-images.githubusercontent.com/66783849/210682832-fe015bdb-383d-40ba-ba34-3974bc132e29.png" width="250"><br>
테스트 부재에 따른 진척도 및 작업 소요기간<br>
테스트가 없으면 이후 기하급수적으로 작업소요시간이 늘어난다. 이는 유지보수 및 신규 기능을 적용이 어렵기 때문.

<br>

### 코드 커버리지(테스트 커버리지)

- 코드 커버리지(테스트 커버리지) = 실행코드 라인 수 / 전체 라인수, (100%가 되면 좋다)
  - 예시1. 전체 라인수 3줄, 실행 코드 라인수 2줄
    ```cs
    pulic static bool IsStringLong(string input){
      if (input.length > 5)
          return true;
      return false;
    }
    ```
  - 예시2. 코드 커버리지 100%
    ```cs
    pulic static bool IsStringLong(string input){
      return input.length > 5;
    }
    ```

<br>

### 분기 커버리지

- 분기 커버리지 = 통과 분기 / 전체 분기 (외부 라이브러리에 대한 분기를 조심)
  - 예시 1
    ```cs
    public void Function(string input)
    {
        if(IsStringLong(input))
            Console.WriteLine("Is Over 5 Line");
    }
    ```
  - 예시 1의 경우, 5줄 이상만 동작, 진행하기에 50%이다.
  - 하지만 string이라는 .Net에는 여러 분기가 존재하는데...
    - null, "", 너무 긴 문자열, 문자열이 아닌 것
    - 이러한 4가지의 분기로 나뉘어 진다. 이러한 점을 조심할 것.


<br><br>

## 2장. 단위 테스트란 무엇인가

<br>

### 단위 테스트
- 작은 코드 조각(단위)을 검증하고, 빠르게 수행하고, 격리된 방식으로 처리하는 자동화 테스트.
- 예시
  ```cs
  pulic static bool IsStringLong(string input){
      return input.length > 5;
  }
  [Fact]
  public void Test()
  {
      // Arrange
      
      // Act
      bool result = IsStringLong("abc");
  
      // Assert
      Assert.Equal(result, true);
  }
  ```

<br><br>

## 3장. 단위 테스트 구조

### Test 코드 작성 주의사항

1. if 문은 쓰지 말자
2. AAA패턴(준비 실행 검증)에서 실행 부분은 무조건 한줄
3. 하나의 기능에 하나의 테스트 (기능이 많으면 테스트를 늘린다)

<br>

### Test 방법

- 사용 nuget pakage
  - xunit
  - nunit
- 단위테스트 명명법
  - `[테스트 대상 메서드(메서드이름)]_[시나리오(테스트 조건)]_[예상결과(기대결과)]`
  ```cs
  public class CacluatorTests
  {
    [Fact]
    //public void Sum_of_two_numbers() // 바로 읽히는 것을 추구하면 이것 또한 좋다.
    public void Sum_TwoNumbers_RetunsSum()
    {
        double first = 10;
        double second = 20;
        var sut = new Caculator();

        double result = sut.Sum(first, second);

        Assert.Equal(result, 30);
    }
  }
  ```
  - 어디까지나 읽히기 쉬우면 좋다.
    - `public void IsDeliveryValid_InvalidDate_ReturnsFalse()`
    - `public void Delivery_with_invalid_date_should_be_considered_invalid()`
    - `public void Delivery_with_a_past_date_is_invalid()`
      - 단도직입적으로 설명했으므로, 좋다.

### Test 방법

- `[Fact]` : 사실을 이야기 한다.
- `[Theory]` : 이론 동작에 대한 사실의 묶음이다.
- `[InlineData]` : 시스템에 대한 별도의 사실을 나타낸다.

### 검증문 라이브러리

- Fluent Assertions 뿐만 아니라 .Net에는 다양한 검증문이 존재한다.
  - `Assert.Equal(result, expected);`
  - `result.Should().Be(expected);`
- 가독성이 좋은 내용을 잘 선택하자.


<br><br>

# 2부. 개발자에게 도움이 되는 테스트 만들기

## 4장. 좋은 단위 테스트의 4대 요소

### 좋은 테스트

- 좋은 테스트를 만들자.
- 리팩터링 내성 + 회귀 방지 + 빠른 피드백 : 실현불가능한 이상적인 테스트
  - 리팩터링 내성 + 회귀 방지 : 엔드 투 엔드 테스트
  - 리팩터링 내성 + 빠른 피드백 : 간단한 테스트
  - 회귀 방지 + 빠른 피드백 : 깨지기 쉬운 테스트
- 블랙박스 테스트, 화이트박스 테스트

<br><br>

## 5장. 목과 테스트 취약성

- 테스트 대역
  - 더미
  - 스텁
  - 스파이
  - 목
  - 페이크
- 목 (목, 스파이) : 외부로 나가는 상호 작용을 모방하고 검사하는데 도움.
- 스텁(stub) (스텁, 더미, 페이크) : 내부로 들어오는 상호 작용을 모방하고 검사하는데 도움.
- 예시는 나중에...

<br><br>

## 6장. 단위 테스트 스타일

- 출력 기반 테스트 : 리펙터링 내성을 지키기 위한 노력은 낮고, 유지비도 낮다.
- 상태 기반 테스트 : 리펙터링 내성을 지키기 위한 노력은 중간, 유지비도 중간.
- 통신 기반 테스트 : 리펙터링 내성을 지키기 위한 노력은 중간, 유지비도 높다.
- 함수형 프로그래밍
  - 목과 연동하는 예제는 나중에...

<br><br>

## 7장. 가치 있는 단위 테스트를 위한 리팩터링

<img src="https://user-images.githubusercontent.com/66783849/211224659-1424d166-fc8d-4a7f-b90a-bc4b2319d204.png" width="450">
- 4가지 코드 유형
  - 도메인 모델 및 알고리즘
  - 지나치게 복잡한 코드
  - 간단한 코드
  - 컨트롤러
- 코드의 복잡도, 도메인 유의성, 협적자수로 분류된 네 가지 코드 유형

### TIP
- 코드가 더 중요해지거나 복잡해질수록 협력자는 더 적어야 한다.
- 좋지 않은 테스트를 작성하는 것 보다는  테스트를 전혀 작성하지 않는 편이 낫다.
- 지나치게 복잡한 코드는 분할할 것. (험블 객체 패턴)

### 가치있는 단위테스트를 위한 리팩터링

- 1단계 : 암시적 의존성을 명시적으로 만들기
- 2단계 : 애플리케이션 서비스 계층 도입
- 3단계 : 애플리케이션 서비스 복잡도 낮추기
- 4단계 : 새 Company 클래스 소개

### 복잡도 방지

- CanExecute/Execute 패턴 사용
- 도메인 이벤트를 사용해 도메인 모델 변경 사항 추적

<br><br>

# 3부. 통합 테스트

<br><br>

## 8장. 통합 테스트를 하는 이유

- 통합테스트
  - 단일 동작 단위를 검증
  - 빠르게 수행
  - 다른 테스트와 별도로 처리
- 단위테스트와 통합 테스트 개수의 균형을 맞추어야 한다.
  <img src="https://user-images.githubusercontent.com/66783849/211224659-1424d166-fc8d-4a7f-b90a-bc4b2319d204.png" width="450">
  - 단위테스트 - 도메인 모델 및 알고리즘
  - 통합테스트 - 컨트롤러
  - 간단한 코드 및 복잡한 코드는 테스트 하지 않아야 한다.

### 테스트 피라미드



<br><br>

## 9장. 목 처리에 대한 모범 사례

<br><br>

## 10장. 데이터베이스 테스트

<br><br>

# 4부. 단위 테스트 안티 패턴

<br><br>

