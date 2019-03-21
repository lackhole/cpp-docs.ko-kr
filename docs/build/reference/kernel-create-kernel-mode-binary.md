---
title: /kernel(커널 모드 이진 만들기)
ms.date: 11/04/2016
f1_keywords:
- /kernel
- /kernel-
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
ms.openlocfilehash: d065364cf6d3ae824098634c070f3651324aa52a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816453"
---
# <a name="kernel-create-kernel-mode-binary"></a>/kernel(커널 모드 이진 만들기)

Windows 커널에서 실행할 수 있는 이진 파일을 만듭니다.

## <a name="syntax"></a>구문

```
/kernel[-]
```

## <a name="arguments"></a>인수

**/kernel**<br/>
현재 프로젝트의 코드를 컴파일 및 커널 모드에서 실행 되는 코드에만 적용 되는 c + + 언어 규칙 집합을 사용 하 여 연결 합니다.

**/kernel-**<br/>
현재 프로젝트의 코드를 컴파일 및 커널 모드에서 실행 되는 코드에만 적용 되는 c + + 언어 규칙을 사용 하지 않고 연결 합니다.

## <a name="remarks"></a>설명

방법이 없는 `#pragma` 이 옵션을 제어 하에 해당 합니다.

지정 된 **/kernel** 옵션을 사용 하면 컴파일러 및 링커에서의 커널 모드에서 허용 되는 언어 기능을 조정 하는 데 충분 한 능력과에 고유한 런타임 안정성 문제를 방지 하려면 있는지 확인 커널 모드 c + +입니다. 커널 모드에서 중단 된 c + + 언어 기능의 사용을 금지 하 고 잠재적으로 중단 되지만 비활성화할 수 없습니다는 c + + 언어 기능에 대 한 경고를 제공 하 여 수행 됩니다.

합니다 **/kernel** 옵션 컴파일러와 링커 둘 다 빌드 단계를 적용 하 고 프로젝트 수준에서 설정 됩니다. 전달 된 **/kernel** 에 알리기 위해 컴파일러는 결과 이진 연결 후에 로드 되어야 할 Windows 커널이 전환 합니다. 컴파일러는 커널와 호환 되는 하위 집합에 대 한 c + + 언어 기능의 스펙트럼을 좁혀집니다.

다음 표에서 컴파일러 동작의 변경 내용은 때 **/kernel** 지정 됩니다.

|동작 유형|**/kernel** Behavior|
|-------------------|---------------------------|
|C++ 예외 처리|사용 안 함 모든 인스턴스를 `throw` 하 고 `try` 키워드는 컴파일러 오류를 내보냅니다 (예외 사양을 제외 하 고 `throw()`). 더 **/EH** 옵션은 호환 **/kernel**를 제외한 **/EH-** 합니다.|
|RTTI|사용 안 함 모든 인스턴스를 `dynamic_cast` 하 고 `typeid` 키워드 하지 않으면 컴파일러 오류를 내보냅니다 `dynamic_cast` 정적으로 사용 됩니다.|
|`new` 및 `delete`|명시적으로 정의 해야 합니다 `new()` 또는 `delete()` 연산자; 컴파일러도 아니고 런타임에서 default 정의 제공 합니다.|

호출 규칙을 사용자 지정 된 [/GS](gs-buffer-security-check.md) 빌드 옵션 및 모든 최적화가 사용 하는 경우 허용 됩니다 합니다 **/kernel** 옵션입니다. 인라인 처리 크게 영향을 받지 **/kernel**, 동일한 의미 체계는 컴파일러에서 적용 됩니다. 확인 하려는 경우는 `__forceinline` 인라인 한정자는 적용 해야 해당 경고, [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) 특정 알 수 있도록 설정할지 `__forceinline` 인라인 함수가 아닙니다.

컴파일러는 전달 하는 경우는 **/kernel** 스위치를 하는 미리 정의 라고 하는 전처리기 매크로 `_KERNEL_MODE` 이 고 값 **1**합니다. 이 조건에 따라 사용자 모드 또는 커널 모드 실행 환경 인지에 따라 코드를 컴파일하는 데 사용할 수 있습니다. 예를 들어, 다음 코드는 커널 모드 실행에 대해 컴파일할 때 클래스는 페이징할 메모리 세그먼트에 있어야 지정 합니다.

```cpp
#ifdef _KERNEL_MODE
#define NONPAGESECTION __declspec(code_seg("$kerneltext$"))
#else
#define NONPAGESECTION
#endif

class NONPAGESECTION MyNonPagedClass
{
   // ...
};
```

일부 대상 아키텍처의 다음과 같은 조합을 하며 **/arch** 옵션으로 사용할 때 오류를 생성 **/kernel**:

- **/arch: {SSE&#124;SSE2&#124;AVX}** x86에서 지원 되지 않습니다. 만 **/arch:ia32** 지원 됩니다 **/kernel** x86입니다.

- **/arch: avx** 지원 되지 않습니다 **/kernel** x64입니다.

사용 하 여 구축 **/kernel** 도 전달 **/kernel** 링커에 합니다. 그녀는 링커 동작에 영향을 줍니다이:

- 증분 링크 사용 되지 않습니다. 추가 하는 경우 **증분 /** 링커 명령줄에이 오류를 내보냅니다.

   **LINK: 심각한 오류 LNK1295: '/ 증분'와 호환 되지 않는 ' / 커널 ' 사양입니다. '/ 증분' 없이 연결**

- 링커는 각 개체 파일 (또는 정적 라이브러리에서 포함 된 보관 멤버) 여부를 고 수 컴파일된를 사용 하 여 참조를 검사 합니다 **/kernel** 옵션 이지만 없습니다. 이 조건을 충족 하는 모든 인스턴스를 하는 경우 링커 성공적으로 연결 하지만 표에 나와 있는 것 처럼 경고를 발생할 수 있습니다.

   ||**/kernel** obj|**/kernel-** obj, MASM obj, 또는 cvtresed|믹스 **/kernel** 하 고 **/kernel-** obj|
   |-|----------------------|-----------------------------------------------|-------------------------------------------------|
   |**link /kernel**|예|예|경고 LNK4257 예|
   |**link**|예|예|예|

   **/KERNEL;를 사용 하 여 컴파일되지 LNK4257 연결 개체 이미지를 실행할 수 없습니다.**

합니다 **/kernel** 옵션 및 **/driver** 옵션 독립적으로 작동 하 고 다른 영향을 모두 합니다.

### <a name="to-set-the-kernel-compiler-option-in-visual-studio"></a>Visual Studio에서 /kernel 컴파일러 옵션을 설정 하려면

1. 엽니다는 **속성 페이지** 프로젝트에 대 한 대화 상자. 자세한 내용은 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **C/c + +** 폴더입니다.

1. 선택 된 **명령줄** 속성 페이지.

1. 에 **추가 옵션** 상자에서 추가 `/kernel` 또는 `/kernel-`합니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
