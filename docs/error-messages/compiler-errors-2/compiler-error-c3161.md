---
title: 컴파일러 오류 C3161
ms.date: 11/04/2016
f1_keywords:
- C3161
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
ms.openlocfilehash: 22ecc176036308699c3ad7bd8c015836be910073
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174214"
---
# <a name="compiler-error-c3161"></a>컴파일러 오류 C3161

'interface': 중첩 클래스, 구조체, 공용 구조체 또는 인터페이스의 인터페이스 유효 하지 않은; 클래스, 구조체 또는 공용 구조체에서는 올바르지 않습니다.

[__interface](../../cpp/interface.md) 전역 범위 또는 네임 스페이스 내에 나타날 수 있습니다. 클래스, 구조체 또는 공용 구조체는 인터페이스에 나타날 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3161 오류가 발생 합니다.

```
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```