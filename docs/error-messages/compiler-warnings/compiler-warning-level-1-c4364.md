---
title: 컴파일러 경고 (수준 1) C4364
ms.date: 11/04/2016
f1_keywords:
- C4364
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
ms.openlocfilehash: 716f440cddc3889ec719ef3b295a0d076175be93
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966525"
---
# <a name="compiler-warning-level-1-c4364"></a>컴파일러 경고 (수준 1) C4364

as_friend 특성이 없는 위치 (line_number)에서 이전에 확인 한 어셈블리 ' file '에 대해를 사용 \#. as_friend 적용 되지 않음

지정 된 메타 데이터 파일에 대 한 `#using` 지시어가 반복 되었지만 처음 발생 한 `as_friend` 한정자가 사용 되지 않았습니다. 컴파일러는 두 번째 `as_friend`을 무시 합니다.

자세한 내용은 [Friend 어셈블리 (C++)](../../dotnet/friend-assemblies-cpp.md)를 참조 하세요.

## <a name="example"></a>예제

다음 샘플에서는 구성 요소를 만듭니다.

```cpp
// C4364.cpp
// compile with: /clr /LD
ref class A {};
```

## <a name="example"></a>예제

다음 샘플에서는 C4364를 생성 합니다.

```cpp
// C4364_b.cpp
// compile with: /clr /W1 /c
#using " C4364.dll"
#using " C4364.dll" as_friend   // C4364
```