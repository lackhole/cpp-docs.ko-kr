---
title: 컴파일러 경고(수준 1) C4326
ms.date: 08/27/2018
f1_keywords:
- C4326
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
ms.openlocfilehash: d14a1902db4dcf2224ce6a58db120a81ebb5620f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327355"
---
# <a name="compiler-warning-level-1-c4326"></a>컴파일러 경고(수준 1) C4326

> 반환 형식 '*함수*'있어야'*type1*' of '*type2*'

## <a name="remarks"></a>설명

함수 반환 형식 이외의 *type1*합니다. 예를 들어,를 사용 하 여 [/Za](../../build/reference/za-ze-disable-language-extensions.md)를 **주** 반환 하지 않았습니다는 **int**합니다.

## <a name="example"></a>예제

다음 샘플 C4326 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C4326.cpp
// compile with: /Za /W1
char main()
{
    // C4326, instead use int main()
}
```