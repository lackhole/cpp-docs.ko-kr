---
title: 컴파일러 오류 C3831
ms.date: 11/04/2016
f1_keywords:
- C3831
helpviewer_keywords:
- C3831
ms.assetid: a125d8dc-b75a-4ea0-b6c7-fe7b119dba25
ms.openlocfilehash: d9aa703f12fd175d9f7fc00eb76e76097a32e860
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390557"
---
# <a name="compiler-error-c3831"></a>컴파일러 오류 C3831

'member': 'class' 고정 된 데이터 멤버 또는 고정 포인터를 반환 하는 멤버 함수를 사용할 수 없습니다

[pin_ptr (C++/CLI)](../../extensions/pin-ptr-cpp-cli.md) 잘못 사용 했습니다.

## <a name="example"></a>예제

다음 샘플에서는 C3831 오류가 생성 됩니다.

```
// C3831a.cpp
// compile with: /clr
ref class Y
{
public:
   int i;
};

ref class X
{
   pin_ptr<int> mbr_Y;   // C3831
   int^ mbr_Y2;   // OK
};

int main() {
   Y y;
   pin_ptr<int> p = &y.i;
}
```
