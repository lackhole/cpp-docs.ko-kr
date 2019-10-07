---
title: auto 키워드
ms.date: 05/07/2019
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
ms.openlocfilehash: a695c33ab55601bb8d81b00f963646f6a48f09d5
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222250"
---
# <a name="auto-keyword"></a>auto 키워드

**auto** 키워드는 선언 지정자입니다. 그러나 C++ 표준에는 이 키워드의 원래 의미와 수정된 의미가 정의되어 있습니다. Visual Studio 2010 이전를 **자동** 키워드에서 변수를 선언 합니다 *자동* 저장소 클래스, 즉 변수는 로컬 수명을 갖고입니다. Visual Studio 2010을 사용 하 여 시작 합니다 **자동** 선언의 초기화 식에서 형식이 추론 되는 변수를 선언 하는 키워드입니다. [/Zc: auto&#91;-&#93; ](../build/reference/zc-auto-deduce-variable-type.md) 컴파일러 옵션은 **auto** 키워드의 의미를 제어합니다.

## <a name="syntax"></a>구문

```cpp
auto declarator ;
auto declarator initializer;
```

## <a name="remarks"></a>설명

**auto** 키워드 정의는 C 프로그래밍 언어가 아닌 C++ 프로그래밍 언어로 변경됩니다.

다음 항목에서는 **auto** 키워드 및 해당 컴파일러 옵션을 설명합니다.

- [auto(C++)](../cpp/auto-cpp.md)는 **auto** 키워드의 새 정의를 설명합니다.

- [/Zc: auto(변수 형식 추론)](../build/reference/zc-auto-deduce-variable-type.md)은 사용할 **auto** 키워드의 정의를 컴파일러에 알리는 컴파일러 옵션을 설명합니다.

## <a name="see-also"></a>참고 자료

[C++ 키워드](../cpp/keywords-cpp.md)
