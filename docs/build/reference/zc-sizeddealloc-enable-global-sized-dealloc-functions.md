---
title: '/Zc: sizeddealloc (전역 크기 할당 해제 함수 사용)'
ms.date: 03/06/2018
f1_keywords:
- sizedDealloc
- /Zc:sizedDealloc
helpviewer_keywords:
- -Zc compiler options (C++)
- sizedDealloc
- Enable Global Sized Deallocation Functions
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 3a73ace0-4d36-420a-b699-0ca6fc0dd134
ms.openlocfilehash: dc381058c6a2ef84542be1d3cdd00c410aa51c2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315484"
---
# <a name="zcsizeddealloc-enable-global-sized-deallocation-functions"></a>/Zc: sizeddealloc (전역 크기 할당 해제 함수 사용)

합니다 **/zc: sizeddealloc** 컴파일러 옵션 우선적으로 전역를 호출 하는 컴파일러가 `operator delete` 또는 `operator delete[]` 형식의 두 번째 매개 변수가 있는 함수 `size_t` 개체의 크기를 사용할 수 있습니다. 이러한 함수를 사용할 수는 `size_t` 비 할당자 성능을 최적화 하기 위해 매개 변수입니다.

## <a name="syntax"></a>구문

> **/Zc:sizedDealloc**[**-**]

## <a name="remarks"></a>설명

표준 C + + 11에서 정적 멤버 함수를 정의할 수 있습니다 `operator delete` 하 고 `operator delete[]` 초를 사용 하는 `size_t` 매개 변수입니다. 일반적으로 함께에서 사용 됩니다 이러한 [new 연산자](../../cpp/new-operator-cpp.md) 효율적 allocator 및 비 할당자 개체를 구현 하는 함수입니다. 그러나 C + + 11 전역 범위에서 할당 해제 함수의 해당 집합을 정의 하지 않았으므로 합니다. C + + 11, 전역 할당 해제 함수에서 형식의 두 번째 매개 변수가 있는 `size_t` placement delete 함수 것으로 간주 됩니다. 명시적으로 크기 인수를 전달 하 여 호출 해야 합니다.

표준 C + + 14 컴파일러의 동작을 변경 합니다. 정의 하는 경우 전역 `operator delete` 및 `operator delete[]` 형식의 두 번째 매개 변수를 사용 하는 `size_t`, 컴파일러는 멤버 범위 버전이 호출 되지 않습니다 하 고 개체의 크기는 사용 가능한 경우 이러한 함수를 호출 하려면 선호 합니다. 컴파일러는 암시적으로 크기 인수를 전달합니다. 컴파일러에서 할당 취소 되 고 개체의 크기를 확인할 수 없을 때 단일 인수 버전 이라고 합니다. 이 고, 그렇지 deallocation 함수 호출의 버전을 선택 하는 것에 대 한 일반적인 규칙은 계속 적용 합니다. 전역 함수를 호출 하는 범위 확인 연산자를 추가 하 여 명시적으로 지정할 수 있습니다 (`::`)를 할당 해제 함수 호출 합니다.

기본적으로 시각적 개체 C++ Visual Studio 2015부터이 c++14 표준 동작을 구현 합니다. 이 설정 하 여에 명시적으로 지정할 수 있습니다 합니다 **/zc: sizeddealloc** 컴파일러 옵션입니다. 잠재적으로 중요 나타냅니다 변경 합니다. 사용 된 **/zc: sizeddealloc-** 코드 형식의 두 번째 매개 변수를 사용 하는 배치 delete 연산자를 정의 하는 경우 예를 들어, 이전 동작을 유지 하는 옵션 `size_t`합니다. 형식의 두 번째 매개 변수가 있는 전역 할당 해제 함수의 기본 Visual Studio 라이브러리 구현의 `size_t` 단일 매개 변수 버전을 호출 합니다. 코드에만 단일 매개 변수 전역 제공 하는 경우 delete 연산자 및 operator delete, 전역 크기가 지정 된 할당 해제 함수의 기본 라이브러리 구현의 전역 함수를 호출 합니다.

합니다 **/zc: sizeddealloc** 컴파일러 옵션이 기본적으로 켜져 있습니다. 합니다 [/ permissive-](permissive-standards-conformance.md) 옵션이 적용 되지 않습니다 **/zc: sizeddealloc**합니다.

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성을** 드롭다운 메뉴에서 선택 **모든 구성**합니다.

1. **구성 속성** > **C/C++** > **명령줄** 속성 페이지를 선택합니다.

1. 수정 된 **추가 옵션** 포함할 속성을 **/zc: sizeddealloc** 또는 **/zc: sizeddealloc-** 를 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[/Zc(규칙)](zc-conformance.md)<br/>
