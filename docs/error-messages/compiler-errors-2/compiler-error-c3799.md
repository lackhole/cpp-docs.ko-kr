---
title: 컴파일러 오류 C3799
ms.date: 11/04/2016
f1_keywords:
- C3799
helpviewer_keywords:
- C3799
ms.assetid: 336a2811-9370-4e6e-b03b-325bda470805
ms.openlocfilehash: 19ff414bde9bb24fca62fd10cfef6d18109199e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400125"
---
# <a name="compiler-error-c3799"></a>컴파일러 오류 C3799

인덱싱된 속성에는 빈 매개 변수 목록을 사용할 수 없습니다.

인덱싱된 속성을 잘못 선언 되었습니다. 자세한 내용은 [방법: 속성에서 사용 하 여 C++/CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3799 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C3799.cpp
// compile with: /clr /c
ref struct C {
   property int default[] {   // C3799
   // try the following line instead
   // property int default[int] {
      int get(int index) { return 0; }
      void set(int index, int value) {}
   }
};
```