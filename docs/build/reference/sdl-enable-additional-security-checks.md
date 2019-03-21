---
title: /sdl(추가 보안 검사 사용)
ms.date: 11/26/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.SDLCheck
ms.assetid: 3dcf86a0-3169-4240-9f29-e04a9f535826
ms.openlocfilehash: 0618b796d492395c3e0e5413047ac0260082baff
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814204"
---
# <a name="sdl-enable-additional-security-checks"></a>/sdl(추가 보안 검사 사용)

권장되는 SDL(Security Development Lifecycle) 검사를 추가합니다. 이러한 검사에는 오류와 같은 추가 보안 관련 경고 및 추가 보안 코드 생성 기능이 포함됩니다.

## <a name="syntax"></a>구문

```
/sdl[-]
```

## <a name="remarks"></a>설명

**/sdl** 에서 제공 하는 기준 보안 검사의 상위 집합을 활성화 [/GS](gs-buffer-security-check.md) 재정의 **/GS-** 합니다. 기본적으로 **/sdl** 꺼져 있습니다. **/sdl-** 추가 보안 검사를 사용 하지 않도록 설정 합니다.

## <a name="compile-time-checks"></a>컴파일 시 검사

**/sdl** 이러한 경고를 오류로 사용 하도록 설정 합니다.

|/SDL에 의해 활성화된 경고|해당 명령줄 스위치|설명|
|------------------------------|-------------------------------------|-----------------|
|[C4146](../../error-messages/compiler-warnings/compiler-warning-level-2-c4146.md)|/we4146|단항 빼기 연산자가 부호 없는 형식에 적용되어 부호 없는 결과가 발생했습니다.|
|[C4308](../../error-messages/compiler-warnings/compiler-warning-level-2-c4308.md)|/we4308|음의 정수 상수가 부호 없는 형식으로 변환되어 의미 없는 결과가 발생할 수 있습니다.|
|[C4532](../../error-messages/compiler-warnings/compiler-warning-level-1-c4532.md)|/we4532|이용 `continue`, `break` 또는 `goto` 키워드를 `__finally` / `finally` 블록 비정상적으로 종료 하는 동안 동작이 정의 되지 않았습니다.|
|[C4533](../../error-messages/compiler-warnings/compiler-warning-level-1-c4533.md)|/we4533|변수를 초기화 하는 코드가 실행되지 않습니다.|
|[C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md)|/we4700|초기화되지 않은 지역 변수 사용.|
|[C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)|/we4703|잠재적으로 초기화되지 않은 지역 포인터 변수 사용.|
|[C4789](../../error-messages/compiler-warnings/compiler-warning-level-1-c4789.md)|/we4789|특정 CRT(C 런타임) 함수를 사용할 때 버퍼가 오버런됩니다.|
|[C4995](../../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)|/we4995|Pragma로 표시 된 함수를 사용 [사용 되지 않는](../../preprocessor/deprecated-c-cpp.md)합니다.|
|[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)|/we4996|로 표시 된 함수를 사용 [사용 되지 않는](../../cpp/deprecated-cpp.md)합니다.|

## <a name="runtime-checks"></a>런타임 검사

때 **/sdl** 가 사용 하도록 설정 컴파일러 런타임 시 이러한 검사를 수행 하는 코드를 생성 합니다.

- Strict 모드를 사용 하도록 설정 **/GS** 런타임 버퍼 오버런 탐지를 사용 하 여 컴파일할 때와 동일한 `#pragma strict_gs_check(push, on)`입니다.

- 제한된 포인터 삭제를 수행합니다. 역참조를 포함하지 않으며 사용자 정의된 소멸자가 없는 식에서 포인터 참조는 `delete`에 대한 호출 이후 유효하지 않은 주소로 설정됩니다. 이렇게 하면 오래된 포인터 참조가 재사용되지 않습니다.

- 클래스 멤버 포인터 초기화를 수행합니다. 자동으로 초기화 클래스에 대 한 포인터 형식의 멤버 **nullptr** 개체 인스턴스화 (생성자 실행) 이전에 있습니다. 이렇게 하면 생성자를 명시적으로 초기화 하지 않는 초기화 되지 않은 포인터의 사용을 금지할 수 있습니다. 컴파일러에서 생성 된 멤버 포인터 초기화 라고으로:

  - 개체는 사용자 지정 (사용자 정의)를 사용 하 여 할당 되지 않습니다. `operator new`

  - 개체 배열의 일환으로 할당 되지 않습니다 (예를 들어 `new A[x]`)

  - 클래스는 관리 또는 가져온 되지

  - 클래스에는 사용자 정의 기본 생성자입니다.

  컴파일러에서 생성 된 클래스 초기화 함수로 초기화할 멤버 포인터와 하지 속성 또는 상수 여야 합니다.

## <a name="remarks"></a>설명

자세한 내용은 [경고, /sdl 및 초기화 되지 않은 변수 검색 향상](https://cloudblogs.microsoft.com/microsoftsecure/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection/)합니다.

#### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **C/c + +** 폴더입니다.

1. 에 **일반적인** 페이지에서 옵션을 선택 합니다는 **SDL 검사** 드롭 다운 목록.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
