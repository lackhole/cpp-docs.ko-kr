---
title: /Zc(규칙)
ms.date: 03/06/2018
f1_keywords:
- /zc
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: e24dd53f9c805f57ce974a81a4963434f1868095
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316212"
---
# <a name="zc-conformance"></a>/Zc(규칙)

사용할 수는 **/Zc** 컴파일러 옵션을 표준 또는 Microsoft 전용 컴파일러 동작을 지정 합니다.

## <a name="syntax"></a>구문

> **/Zc:**_option_{,_option_}

## <a name="remarks"></a>설명

Visual Studio가 C에 대 한 확장을 구현 하는 경우 또는 C++ 표준 호환 되지 않습니다는 사용할 수 있습니다는 `/Zc` 표준 준수 또는 Microsoft 전용 동작을 지정 하는 규칙 옵션입니다. 몇 가지 옵션을 Microsoft 특정 동작이 기존 코드에 대규모 주요 변경을 방지 하기 위해 기본값입니다. 다른 경우에 기본 동작은 표준, 향상 된 보안, 성능 또는 호환성에서 비용의 주요 변경 내용을 능가 하는 위치 합니다. 최신 버전의 Visual Studio에서 각 규칙 옵션의 기본 설정을 변경할 수 있습니다. 각 규칙 옵션에 대 한 자세한 내용은 해당 옵션에 대 한 항목을 참조 하세요. 합니다 [/ permissive-](permissive-standards-conformance.md) 컴파일러 옵션은 암시적으로 해당와 호환 되는 설정에는 기본적으로 설정 되지 않은 규칙 옵션을 설정 합니다.

이들은 `/Zc` 컴파일러 옵션:

|옵션|동작|
|---|---|
|[alignedNew\[-\]](zc-alignednew.md)|C + + 17 과다 정렬 된 동적 할당을 사용 하도록 설정 (에서 기본적으로 C + +에서 17).|
|[auto\[-\]](zc-auto-deduce-variable-type.md)|새 표준을 적용 C++ 에 대 한 의미 `auto` (에서 기본적으로).|
|[__cplusplus\[-\]](zc-cplusplus.md)|사용 하도록 설정 합니다 **__cplusplus** 매크로 지원 되는 표준 보고서를 (기본적으로 꺼져 있음).|
|[externConstexpr\[-\]](zc-externconstexpr.md)|외부 링크를 사용 하도록 설정 `constexpr` 변수 (기본적으로 꺼져 있음).|
|[forScope\[-\]](zc-forscope-force-conformance-in-for-loop-scope.md)|표준을 적용 C++ `for` 범위 지정 규칙 (에서 기본적으로).|
|[implicitNoexcept\[-\]](zc-implicitnoexcept-implicit-exception-specifiers.md)|암시적 사용 `noexcept` 필수 함수에서 (에서 기본적으로).|
|[inline\[-\]](zc-inline-remove-unreferenced-comdat.md)|COMDAT 되었거나 내부 링크만 있는 참조 되지 않은 함수 또는 데이터를 제거 (기본적으로 꺼져 있음).|
|[noexceptTypes\[-\]](zc-noexcepttypes.md)|C + + 17 noexcept 규칙 적용 (에서 C + + 17 이상 기본적으로).|
|[referenceBinding\[-\]](zc-referencebinding-enforce-reference-binding-rules.md)|UDT 임시 비 const lvalue 참조에 바인딩되지 않습니다 (기본적으로 꺼져 있음).|
|[rvalueCast\[-\]](zc-rvaluecast-enforce-type-conversion-rules.md)|표준을 적용 C++ 명시적 형식 변환 규칙 (기본적으로 꺼져 있음).|
|[sizedDealloc\[-\]](zc-sizeddealloc-enable-global-sized-dealloc-functions.md)|C + + 14 전역 크기가 지정 된 된 할당 해제 함수 사용 (에서 기본적으로).|
|[strictStrings\[-\]](zc-strictstrings-disable-string-literal-type-conversion.md)|사용 하지 않도록 설정 하는 문자열 리터럴 `char*` 또는 `wchar_t*` 변환 (기본적으로 꺼져 있음).|
|[ternary\[-\]](zc-ternary.md)|피연산자 형식에 대 한 조건부 연산자 규칙 적용 (기본적으로 꺼져 있음).|
|[threadSafeInit\[-\]](zc-threadsafeinit-thread-safe-local-static-initialization.md)|스레드로부터 안전한 로컬 정적 초기화를 사용 하도록 설정 (에서 기본적으로).|
|[throwingNew\[-\]](zc-throwingnew-assume-operator-new-throws.md)|가정 `operator new` 실패 시 throw (기본적으로 꺼져 있음).|
|[trigraphs\[-\]](zc-trigraphs-trigraphs-substitution.md)|삼중 자 (사용 되지 않는 해제 기본적으로)을 사용 하도록 설정 합니다.|
|[twoPhase-](zc-twophase.md)|비준수 템플릿 구문 분석 동작 (기본적으로 준수)를 사용 합니다.|
|[wchar_t\[-\]](zc-wchar-t-wchar-t-is-native-type.md)|`wchar_t` 네이티브 형식, 형식 정의가 아닙니다. (에서 기본적으로).|

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
