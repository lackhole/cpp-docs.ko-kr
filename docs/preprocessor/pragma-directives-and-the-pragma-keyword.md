---
title: Pragma 지시문 및 __Pragma 키워드
ms.date: 11/04/2016
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directives, C/C++'
- __pragma keyword
- pragma directives, C/C++
- pragmas, C/C++
- preprocessor
- pragmas
- preprocessor, pragmas
- pragma directives (#pragma)
ms.assetid: 9867b438-ac64-4e10-973f-c3955209873f
ms.openlocfilehash: b6c2ff579c6fafa78cbfd0a2879a71fca2bfaa01
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027443"
---
# <a name="pragma-directives-and-the-pragma-keyword"></a>Pragma 지시문 및 __Pragma 키워드

Pragma 지시어를 이용하면 하드웨어나 운영 체제와 관련된 특정한 기능과 관련된 기능을 컴파일러에 통보할 수 있습니다. Microsoft 컴파일러만을 위한 지시어를 사용한다면 **__pragma** 지시어를 매크로에 연동하여 사용할 수 있습니다.

## <a name="syntax"></a>구문

```
#pragma token-string
__pragma(token-string)
```

## <a name="remarks"></a>설명

C 및 C++은 호스트 컴퓨터나 운영 체제에 고유한 기능을 제어할 수 있도록 몇 가지 기능을 구현할 수 있습니다. 예를 들어, 일부 프로그램은 데이터가 저장되는 메모리 영역을 정밀하게 제어하거나 특정 함수가 매개 변수를 수신하는 방법을 제어해야 합니다. **#pragma** 지시문을 이용하면 C 및 C++ 언어로 개발한 코드가 전반적인 호환성을 유지하면서 시스템 및 운영 체제별로 기능을 제공하는 방법이 가능해집니다.

Pragma의 정의에 따라 시스템이나 운영체제별로 다르며, 일반적으로 모든 컴파일러마다 다릅니다. 새로운 전처리기 기능을 제공하거나 구현사항에 대한 정보를 컴파일러에 제공하기 위해 Progma를 조건문과 함께 사용할 수 있습니다.

`token-string`은 특정 컴파일러 명령이나 인수 등과 같은 것을 제공하는 일련의 문자 집합입니다. pragma 줄의 첫 번째 문자는 공백이 오면 안 되고, 반드시 표식기호(**#**)여야 합니다. 공백 문자를 이용하여 표식기호(**#**)와 "pragma"사이를 띄울 수는 있습니다. **#pragma** 뒤에 오는, 변환기가 전처리 토큰으로 구문 분석할 수 있는 모든 텍스트를 작성합니다. **#pragma** 인수로 매크로를 사용할 수 있습니다.

컴파일러가 인식할 수 없는 pragma를 찾으면 경고를 표시하고 컴파일을 계속합니다.

Microsoft C 및 C++ 컴파일러는 다음의 pragma를 인식합니다.

||||
|-|-|-|
|[alloc_text](../preprocessor/alloc-text.md)|[auto_inline](../preprocessor/auto-inline.md)|[bss_seg](../preprocessor/bss-seg.md)|
|[check_stack](../preprocessor/check-stack.md)|[code_seg](../preprocessor/code-seg.md)|[comment](../preprocessor/comment-c-cpp.md)|
|[구성 요소](../preprocessor/component.md)|[conform](../preprocessor/conform.md) <sup>1</sup>|[const_seg](../preprocessor/const-seg.md)|
|[data_seg](../preprocessor/data-seg.md)|[deprecated](../preprocessor/deprecated-c-cpp.md)|[detect_mismatch](../preprocessor/detect-mismatch.md)|
|[fenv_access](../preprocessor/fenv-access.md)|[float_control](../preprocessor/float-control.md)|[fp_contract](../preprocessor/fp-contract.md)|
|[함수](../preprocessor/function-c-cpp.md)|[hdrstop](../preprocessor/hdrstop.md)|[include_alias](../preprocessor/include-alias.md)|
|[init_seg](../preprocessor/init-seg.md) <sup>1</sup>|[inline_depth](../preprocessor/inline-depth.md)|[inline_recursion](../preprocessor/inline-recursion.md)|
|[intrinsic](../preprocessor/intrinsic.md)|[loop](../preprocessor/loop.md) <sup>1</sup>|[make_public](../preprocessor/make-public.md)|
|[managed](../preprocessor/managed-unmanaged.md)|[message](../preprocessor/message.md)||
|[omp](../preprocessor/omp.md)|[once](../preprocessor/once.md)||
|[optimize](../preprocessor/optimize.md)|[pack](../preprocessor/pack.md)|[pointers_to_members](../preprocessor/pointers-to-members.md) <sup>1</sup>|
|[pop_macro](../preprocessor/pop-macro.md)|[push_macro](../preprocessor/push-macro.md)|[region, endregion](../preprocessor/region-endregion.md)|
|[runtime_checks](../preprocessor/runtime-checks.md)|[section](../preprocessor/section.md)|[setlocale](../preprocessor/setlocale.md)|
|[strict_gs_check](../preprocessor/strict-gs-check.md)|[unmanaged](../preprocessor/managed-unmanaged.md)|[vtordisp](../preprocessor/vtordisp.md) <sup>1</sup>|
|[경고](../preprocessor/warning.md)|||

<sup>1</sup> C++ 컴파일러 전용 pragma입니다.

## <a name="pragmas-and-compiler-options"></a>Pragma 및 컴파일러 옵션

어떤 pragma는 컴파일러 옵션과 같이 동작하는 기능을 제공합니다. 소스 코드에 pragma가 발견되면 컴파일러 옵션에 지정된 동작을 재정의합니다. 예를 들어 [/zp8](../build/reference/zp-struct-member-alignment.md)을 지정하면 [팩](../preprocessor/pack.md)과 관련된 코드 섹션에 대한 컴파일러 설정을 재정의합니다.

```
cl /Zp8 ...

<file> - packing is 8
// ...
#pragma pack(push, 1) - packing is now 1
// ...
#pragma pack(pop) - packing is 8
</file>
```

## <a name="the-pragma-keyword"></a>__pragma() 키워드

**Microsoft 전용**

컴파일러는  **#pragma** 지시어와 기능이 동일하지만 매크로상에서 인라인으로 사용할 수 있는 **__pragma** 키워드도 지원합니다. **#pragma** 지시어의 경우 컴파일러가 표식기호('#')를 [문자열 연산자 (#)](../preprocessor/stringizing-operator-hash.md)로 매크로 정의에서 지시문을 사용할 수 없습니다.

다음 코드 예제는 **__pragma** 키워드를 매크로에서 사용하는 예를 보여줍니다. 이 코드는 "컴파일러 COM 지원 샘플"의 ACDUAL 샘플에 있는 mfcdual.h 헤더에서 발췌되었습니다.

```cpp
#define CATCH_ALL_DUAL \
CATCH(COleException, e) \
{ \
_hr = e->m_sc; \
} \
AND_CATCH_ALL(e) \
{ \
__pragma(warning(push)) \
__pragma(warning(disable:6246)) /*disable _ctlState prefast warning*/ \
AFX_MANAGE_STATE(pThis->m_pModuleState); \
__pragma(warning(pop)) \
_hr = DualHandleException(_riidSource, e); \
} \
END_CATCH_ALL \
return _hr; \
```

**End Microsoft 전용**

## <a name="see-also"></a>참고자료

[C/C++ 전처리기 도움말](../preprocessor/c-cpp-preprocessor-reference.md)<br/>
[C Pragma](../c-language/c-pragmas.md)<br/>
[키워드](../cpp/keywords-cpp.md)