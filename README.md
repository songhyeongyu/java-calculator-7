# java-calculator-precourse


## 소개

Java 문자열 덧셈 계산기는 사용자가 입력한 문자열에서 숫자를 추출하고 합산하는 간단한 프로그램입니다. 기본적으로 ","와 ":"을 구분자로 사용하지만, 사용자가 커스텀 구분자를 정의할 수도 있습니다. 이 프로그램은 주어진 문자열을 파싱하여 숫자를 더하고, 결과를 출력합니다.

## 주요 기능

1. **문자열 입력**: 프로그램이 실행되면 "덧셈할 문자열을 입력해 주세요."라는 메시지를 출력하고 사용자로부터 문자열을 입력받습니다.
2. **기본 구분자 처리**: 입력된 문자열에서 기본 구분자인 `,`와 `:`을 사용해 숫자를 분리합니다.
3. **커스텀 구분자 지원**: 사용자가 문자열의 앞부분에 `//`와 구분자를 추가하고 그 뒤에 `\n`을 입력하면 커스텀 구분자를 사용할 수 있습니다. 예를 들어, `//;\n1;2;3`이라는 입력은 `;`를 구분자로 사용하여 숫자를 분리합니다.
4. **합산 결과 출력**: 분리된 숫자를 모두 더한 결과를 출력합니다. 예를 들어, 입력이 `1,2:3`이면 결과는 `6`으로 출력됩니다.
5. **예외 처리**: 음수가 입력되거나 잘못된 형식의 구분자가 입력되면 예외를 발생시킵니다.
6. **빈 문자열 처리**: 빈 문자열이 입력될 경우 결과는 `0`으로 출력됩니다.

## 사용 방법

1. 프로그램을 실행합니다.
2. "덧셈할 문자열을 입력해 주세요."라는 메시지가 출력되면 문자열을 입력합니다.
3. 입력한 문자열에 따라 기본 구분자(`,`, `:`) 또는 커스텀 구분자를 사용하여 숫자를 분리합니다.
4. 결과는 입력된 숫자의 합으로 출력됩니다.

## 코드 설명

### `CalculatorRunner` 클래스

- **`run()` 메서드**: 프로그램의 주요 실행 로직을 포함하고 있습니다. 사용자로부터 문자열을 입력받고, 구분자를 통해 숫자를 분리한 후 결과를 출력합니다.
- **`calculateSum(String inputString, Set<Character> newSeparator)` 메서드**: 입력된 문자열을 주어진 구분자를 기준으로 분리하고, 각 숫자를 합산하여 결과를 반환합니다.

### `SeparateHelper` 클래스

- **`BASIC_SEPARATOR`**: 기본 구분자를 정의한 `Set`입니다. 기본 구분자는 `,`와 `:`입니다.
- **`isSeparator(String input)` 메서드**: 입력된 문자열이 커스텀 구분자를 포함하는지 확인합니다.
- **`findSeparator(String input)` 메서드**: 커스텀 구분자를 추출합니다.
- **`splitString(String input)` 메서드**: 커스텀 구분자를 처리하고 나머지 숫자 문자열을 반환합니다.
- **`addStringToCharSet(String separator)` 메서드**: 새로운 구분자를 기존 구분자 세트에 추가합니다.

### `IOHelper` 클래스

- **`getInput()` 메서드**: 사용자로부터 입력을 받습니다. 입력 도중 예외가 발생하면 `null`을 반환합니다.
- **`printResult(int result)` 메서드**: 계산된 합산 결과를 출력합니다.

## 예시

- **기본 구분자 사용**
    - 입력: `1,2:3`
    - 출력: `결과 : 6`
- **커스텀 구분자 사용**
    - 입력: `//;\n1;2;3`
    - 출력: `결과 : 6`
- **빈 문자열 입력**
    - 입력: `` (빈 문자열)
    - 출력: `결과 : 0`

## 예외 사항

- **음수 입력 시**: 음수가 포함된 경우 `IllegalArgumentException`이 발생합니다.
- **잘못된 구분자**: 연속된 구분자나 정의되지 않은 구분자가 들어올 경우 예외가 발생합니다.

## 의존성

- 이 프로그램은 `camp.nextstep.edu.missionutils.Console` 라이브러리를 사용하여 사용자 입력을 처리합니다.
