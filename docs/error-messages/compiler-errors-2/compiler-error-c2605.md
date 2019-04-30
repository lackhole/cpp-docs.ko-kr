---
title: 컴파일러 오류 C2605
ms.date: 11/04/2016
f1_keywords:
- C2605
helpviewer_keywords:
- C2605
ms.assetid: a0e6f132-5acf-4e19-b277-ddf196d182bf
ms.openlocfilehash: c1a3f1132edb90e119d97061fbbfb293d364ef3a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62215229"
---
# <a name="compiler-error-c2605"></a>컴파일러 오류 C2605

'name': 이 메서드는 관리되는 클래스나 WinRT 클래스에서 예약됩니다.

특정 이름은 내부 함수용으로 컴파일러에서 예약됩니다.  자세한 내용은 [소멸자 및 종료자](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2605 오류가 발생하는 경우를 보여 줍니다.

```
// C2605.cpp
// compile with: /clr /c
ref class R {
protected:
   void Finalize() {}   // C2605
};
```