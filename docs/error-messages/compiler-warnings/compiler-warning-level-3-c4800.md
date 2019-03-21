---
title: 컴파일러 경고 (수준 4) C4800
ms.date: 03/14/2019
f1_keywords:
- C4800
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
ms.openlocfilehash: 46418063625e16385497740a4f7e3d837e923156
ms.sourcegitcommit: a901c4acbfc80ca10663d37c09921f04c5b6dd17
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2019
ms.locfileid: "58142575"
---
# <a name="compiler-warning-level-4-c4800"></a>컴파일러 경고 (수준 4) C4800

::: moniker range=">= vs-2019"
Visual Studio 2019 이상:
> 암시적 변환에서 '*형식*' bool로 합니다. 가능한 정보 손실
::: moniker-end

C4800 Visual Studio 2015 및 이전 버전 수준 3 경고입니다.
> '*형식*': bool 'true' 또는 'false' (성능 경고)로 값을 강제 적용

값 형식으로 암시적으로 변환 되 면이 경고가 생성 됩니다 `bool`합니다. 할당 하 여이 메시지는 발생 하는 일반적으로 `int` 변수를 `bool` 변수 위치는 `int` 변수 값만 포함 **true** 하 고 **false**, 수 형식으로 다시 선언할 `bool`합니다. 형식을 사용 하 여 식을 다시 작성할 수 없습니다 `bool`를 추가 하 여 "`!=0`" 형식을 제공 하는 식과 `bool`합니다. 식 형식으로 캐스팅 `bool` 이 의도적인 경고를 사용 하지 않도록 설정 하지 않습니다.

::: moniker range=">= vs-2017"
이 경고는 Visual Studio 2017에서 내보내지지 않습니다.
::: moniker-end

::: moniker range=">= vs-2019"
이 경고는 Visual Studio 2019부터 기본적으로 꺼져 있습니다. 사용 하 여 __/w__*n*__4800__ C4800 수준으로 사용 하도록 설정 하려면 *n* 경고, 또는 [/wall](../../build/reference/compiler-option-warning-level.md) 모든 경고를 사용 하도록 설정 하는 기본적으로 해제 되어 있습니다. 자세한 내용은 [컴파일러 경고 하는 Off By Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)합니다.
::: moniker-end

## <a name="example"></a>예제

다음 샘플 C4800 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C4800.cpp
// compile with: /W4 /w44800
int main() {
   int i = 0;

   // To fix, instead try:
   // bool i = 0;

   bool j = i;   // C4800
   j++;
}
```