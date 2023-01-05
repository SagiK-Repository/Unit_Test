문서정보 : 2023.01.05. 작성, 작성자 [@SAgiKPJH](https://github.com/SAgiKPJH)

<br>

# 파이썬 코딩의 기술 개정2판

<img src="https://user-images.githubusercontent.com/66783849/210682313-e7e3693f-6523-4d4f-87ec-6e528fb5d5b5.png" width="250">

### 목적
- 책 [Unit Test - 생산성과 품질을 위한 단위 테스트 원칙과 패턴]를 읽고 요약한다.

### 목표

- [x] 1부. 더 큰 그림
  - [x] 1장. 단위 테스트 목표
  - [x] 2장. 단위 테스트란 무엇인가
  - [ ] 3장. 단위 테스트 구조
- [ ] 2부. 개발자에게 도움이 되는 테스트 만들기
  - [ ] 4장. 좋은 단위 테스트의 4대 요소
  - [ ] 5장. 목과 테스트 취약성
  - [ ] 6장. 단위 테스트 스타일
  - [ ] 7장. 가치 있는 단위 테스트를 위한 리팩터링
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
    if (input.length > 5)
        return true;
    return false;
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
  - `[테스트 대상 매서드]_[시나리오]_[예상결과(기대결과)]`

<br><br>

# 2부. 개발자에게 도움이 되는 테스트 만들기

<br><br>

## 4장. 좋은 단위 테스트의 4대 요소

<br><br>

## 5장. 목과 테스트 취약성

<br><br>

## 6장. 단위 테스트 스타일

<br><br>

## 7장. 가치 있는 단위 테스트를 위한 리팩터링

<br><br>

# 3부. 통합 테스트

<br><br>

## 8장. 통합 테스트를 하는 이유

<br><br>

## 9장. 목 처리에 대한 모범 사례

<br><br>

## 10장. 데이터베이스 테스트

<br><br>

# 4부. 단위 테스트 안티 패턴

<br><br>

