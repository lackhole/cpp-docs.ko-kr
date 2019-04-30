---
title: const_seg
ms.date: 09/17/2018
f1_keywords:
- vc-pragma.const_seg
- const_seg_CPP
helpviewer_keywords:
- pragmas, const_seg
- const_seg pragma
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
ms.openlocfilehash: c58f154f5e1ab6906b45d59f454a7dc2b5c0bfbe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366591"
---
# <a name="constseg"></a>const_seg
세그먼트를 지정 합니다. 여기서 [const](../cpp/const-cpp.md) 변수.obj 파일에 저장 됩니다.

## <a name="syntax"></a>구문

```
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )
```

### <a name="parameters"></a>매개 변수

**push**<br/>
(선택 사항) 내부 컴파일러 스택의 레코드를 배치합니다. A **푸시** 있을 수 있습니다는 *식별자* 하 고 *세그먼트 이름이*합니다.

**pop**<br/>
(선택 사항) 내부 컴파일러 스택의 맨 위에서 레코드를 제거합니다.

*identifier*<br/>
(선택 사항) 와 함께 사용할 때 **푸시**, 내부 컴파일러 스택의 레코드에 이름을 할당 합니다. 와 함께 사용할 때 **pop**, 될 때까지 내부 스택에서 기록을 팝 *식별자* 가 제거 *식별자* 없는 내부 스택에서 아무 것도 팝 합니다.

사용 하 여 *식별자* 여러 레코드는 단일으로 팝 될 수 있습니다 **pop** 명령입니다.

"*segment-name*"<br/>
(선택 사항) 세그먼트의 이름입니다. 와 함께 사용할 경우 **pop**, 스택이 팝 되 고 *세그먼트 이름이* 활성 세그먼트 이름이 됩니다.

"*segment-class*"<br/>
(선택 사항) 호환성을 위해 포함 된 C++ 버전 2.0 이전 합니다. 무시됩니다.

## <a name="remarks"></a>설명

의미 *세그먼트* 하 고 *섹션* 이 항목에서 서로 바꿀 수 있습니다.

OBJ 파일을 사용 하 여 볼 수 있습니다 합니다 [dumpbin](../build/reference/dumpbin-command-line.md) 응용 프로그램입니다. `const` 변수에 대한 .obj 파일의 기본 세그먼트는 .rdata입니다. 스칼라 같은 일부 `const` 변수는 자동으로 코드 스트림으로 인라인 처리됩니다. 인라인 처리된 코드는 .rdata에 나타나지 않습니다.

`const_seg`에 동적 초기화가 필요한 개체를 정의하면 정의되지 않은 동작이 발생합니다.

매개 변수 없는 `#pragma const_seg`는 세그먼트를 .rdata로 다시 설정합니다.

## <a name="example"></a>예제

```cpp
// pragma_directive_const_seg.cpp
// compile with: /EHsc
#include <iostream>

const int i = 7;               // inlined, not stored in .rdata
const char sz1[]= "test1";     // stored in .rdata

#pragma const_seg(".my_data1")
const char sz2[]= "test2";     // stored in .my_data1

#pragma const_seg(push, stack1, ".my_data2")
const char sz3[]= "test3";     // stored in .my_data2

#pragma const_seg(pop, stack1) // pop stack1 from stack
const char sz4[]= "test4";     // stored in .my_data1

int main() {
    using namespace std;
   // const data must be referenced to be put in .obj
   cout << sz1 << endl;
   cout << sz2 << endl;
   cout << sz3 << endl;
   cout << sz4 << endl;
}
```

```Output
test1
test2
test3
test4
```

## <a name="comments"></a>설명

참조 [/section](../build/reference/section-specify-section-attributes.md) 섹션을 만들 때 사용 하지 않아야 하는 이름의 목록에 대 한 합니다.

초기화 된 데이터에 대 한 섹션도 지정할 수 있습니다 ([data_seg](../preprocessor/data-seg.md)), 초기화 되지 않은 데이터 ([bss_seg](../preprocessor/bss-seg.md)), 및 함수 ([code_seg](../preprocessor/code-seg.md)).

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)