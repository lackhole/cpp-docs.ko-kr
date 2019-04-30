---
title: 컴파일러 경고(수준 4) C4366
ms.date: 11/04/2016
f1_keywords:
- C4366
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
ms.openlocfilehash: 11fcb0070359201de39ca5f33c83d000e02f0835
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391558"
---
# <a name="compiler-warning-level-4-c4366"></a>컴파일러 경고(수준 4) C4366

단항 'operator' 연산자의 결과 정렬 되지 않을 수 있습니다.

구조체 멤버 수 없는 정렬 된 압축으로 인해, 하는 경우 컴파일러 경고가 표시 됩니다 때 맞춰진된 포인터에 멤버의 주소는 할당 된 합니다. 기본적으로 모든 포인터는 정렬 됩니다.

C4366를 해결 하려면 구조체의 맞춤을 변경 하거나 사용 하 여 포인터를 선언 합니다 [__unaligned](../../cpp/unaligned.md) 키워드입니다.

자세한 내용은 __unaligned 참조 하 고 [팩](../../preprocessor/pack.md)합니다.

## <a name="example"></a>예제

다음 샘플 C4366를 생성합니다.

```
// C4366.cpp
// compile with: /W4 /c
// processor: IPF x64
#pragma pack(1)
struct X {
   short s1;
   int s2;
};

int main() {
   X x;
   short * ps1 = &x.s1;   // OK
   int * ps2 = &x.s2;   // C4366
}
```