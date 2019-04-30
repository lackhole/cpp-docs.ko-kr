---
title: 컴파일러 오류 C3914
ms.date: 11/04/2016
f1_keywords:
- C3914
helpviewer_keywords:
- C3914
ms.assetid: 8f3190e6-ee50-4916-9ecc-3b8748b2e1e7
ms.openlocfilehash: e7c04da2b7574d3af0e1c05ae4adc3ad513faa0b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406615"
---
# <a name="compiler-error-c3914"></a>컴파일러 오류 C3914

기본 속성은 정적일 수 없습니다.

기본 속성을 잘못 선언 되었습니다.  자세한 내용은 [방법: 속성에서 사용 하 여 C++/CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3914 생성 및이 해결 하는 방법을 보여 줍니다.

```
// C3914.cpp
// compile with: /clr /c
ref struct X {
   static property int default[int] {   // C3914
   // try the following line instead
   // property int default[int] {
      int get(int) { return 0; }
      void set(int, int) {}
   }
};
```