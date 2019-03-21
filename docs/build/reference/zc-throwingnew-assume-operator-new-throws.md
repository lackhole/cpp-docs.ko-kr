---
title: '/Zc: throwingnew (operator new throw 가정)'
ms.date: 03/01/2018
f1_keywords:
- throwingNew
- /Zc:throwingNew
helpviewer_keywords:
- -Zc compiler options (C++)
- throwingNew
- Assume operator new Throws
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 20ff0101-9677-4d83-8c7b-8ec9ca49f04f
ms.openlocfilehash: c8c7b4e7246cc3bb1b3a73cde4f6830eb7178dd2
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813515"
---
# <a name="zcthrowingnew-assume-operator-new-throws"></a>/Zc: throwingnew (operator new throw 가정)

경우는 **/zc: throwingnew** 옵션을 지정 하면 컴파일러 최적화에 대 한 호출 `operator new` 반환 null 포인터에 대 한 검사를 건너뜁니다. 이 옵션의 구현을 모두 연결 되어 있음을 가정 하는 컴파일러가 `operator new` 및 사용자 지정 할당자는 c + + 표준을 준수 하 고 할당 실패 시 throw 합니다. Visual Studio에서 기본적으로 컴파일러 pessimistically 생성 null 검사 (**/Zc:throwingNew-**) 호출에 대 한 이러한, 사용자가 throw 되지 않는 구현에 연결할 수 있으므로 `operator new` 하거나 사용자 지정 할당자 루틴 작성 null 포인터를 반환 합니다.

## <a name="syntax"></a>구문

> **/Zc:throwingNew**[**-**]

## <a name="remarks"></a>설명

ISO C + + 98 이후 표준에 지정 하는 기본 [new 연산자](../../standard-library/new-operators.md#op_new) throw `std::bad_alloc` 메모리 할당이 실패 하는 경우. 할당 오류가에 null 포인터를 반환 하는 Visual Studio 6.0까지 Visual c + +의 버전입니다. Visual Studio 2002 년부터 `operator new` 표준을 준수 하 고 실패 시 throw 합니다. 이전 스타일의 할당을 사용 하는 코드를 지원 하려면 Visual Studio는 링커가 구현을 제공 `operator new` 에서 실패 한 경우 null 포인터를 반환 하는 nothrownew.obj와 연결 합니다. 기본적으로 컴파일러는 또한 방어 null 검사 실패 시 즉시는 충돌을 일으키는에서 이러한 이전 스타일 할당자를 생성 합니다. 합니다 **/zc: throwingnew** 옵션 컴파일러가 이러한 null 검사를 생략 하도록 지정, 모든 메모리를 연결 하는 가정에 할당자 표준을 준수 합니다. 명시적 throw 되지 않는에 적용 되지 않습니다 `operator new` 형식의 추가 매개 변수를 사용 하 여 선언 된 오버 로드 `std::nothrow_t` 명시적인 있고 `noexcept` 사양입니다.

개념적으로 사용 가능한 저장소에서 개체를 만들려면 컴파일러 코드 생성 해당 메모리를 할당할 메모리를 초기화 하는 해당 생성자를 호출 하는 고 합니다. 일반적으로 MSVC 컴파일러를이 코드에 맞지 않는, throw 되지 않는 할당자를 연결할 경우 알 수 없으며, 때문에 기본적으로도 생성 생성자를 호출 하기 전에 null 검사를 합니다. Null 포인터를 이렇게 throw 되지 않는 할당이 실패 하는 경우 생성자 호출에서 역참조 합니다. 대부분의 경우에서 이러한 검사는 필요 하기 때문에 기본 `operator new` 할당자 null 포인터를 반환 하는 대신 throw 합니다. 검사 한 가지 아쉬운 부작용 수도 있습니다. 이러한 코드의 크기를 블 로트, 이러한 부담을 줄 분기 예측 및 devirtualization 또는 초기화 된 개체에서 const 전파와 같은 다른 유용한 컴파일러 최적화는 금지 확인 링크는 지원 코드에만 존재 *nothrownew.obj와 연결* 했거나 사용자 지정 비준수 `operator new` 구현 합니다. 비준수를 사용 하지 않는 경우 `operator new`를 사용 하는 것이 좋습니다 **/zc: throwingnew** 코드를 최적화할 수 있습니다.

**/zc: throwingnew** 옵션이 기본적으로 꺼져 있고 영향을 받지는 [관대 한 /-](permissive-standards-conformance.md) 옵션입니다.

링크 타임 코드 생성 (LTCG)를 사용 하 여 컴파일하는 경우 지정할 필요가 없습니다 **/zc: throwingnew**합니다. LTCG를 사용 하 여 코드를 컴파일하면 컴파일러 감지할 수 있습니다 기본 준수 `operator new` 구현이 사용 됩니다. 그렇다면 컴파일러 배제 null 검사를 자동으로 합니다. 링커는에 대 한 합니다 **/ThrowingNew** 를 알려 주는 플래그 경우 구현의 `operator new` 준수 됩니다. 새 사용자 지정 연산자 구현에 대 한 원본에서이 지시어를 포함 하 여 링커에이 플래그를 지정할 수 있습니다.

```cpp
#pragma comment(linker, "/ThrowingNew")
```

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 하세요 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **Configuration** 드롭다운 메뉴에서 선택 **모든 구성**합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 수정 된 **추가 옵션** 포함할 속성을 **/zc: throwingnew** 또는 **/Zc:throwingNew-** 를 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/Zc(규칙)](zc-conformance.md)<br/>
[noexcept(C++)](../../cpp/noexcept-cpp.md)<br/>
[예외 사양(throw)(C++)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[(예외)를 종료 합니다.](../../standard-library/exception-functions.md#terminate)<br/>
