---
title: 컴파일러 오류 C3069
ms.date: 11/04/2016
f1_keywords:
- C3069
helpviewer_keywords:
- C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
ms.openlocfilehash: 6c6451d31da2bb708d3f233225be713981b062e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406758"
---
# <a name="compiler-error-c3069"></a>컴파일러 오류 C3069

'operator': 열거형 형식에 사용할 수 없습니다.

CLR 열거형에 대해서는 연산자가 지원되지 않습니다.  자세한 내용은 [방법: 열거형 정의 및 사용 C++/CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3069를 생성합니다.

```
// C3069.cpp
// compile with: /clr
enum struct E { e1 };
enum F { f1 };

int main() {
   E e = E::e1;
   bool tf;
   tf = !e;   // C3069

   // supported for native enums
   F f = f1;
   tf = !f;
}
```