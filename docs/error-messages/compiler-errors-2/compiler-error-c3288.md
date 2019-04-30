---
title: 컴파일러 오류 C3288
ms.date: 11/04/2016
f1_keywords:
- C3288
helpviewer_keywords:
- C3288
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
ms.openlocfilehash: d076dabe0df91cefb90be5ec9e90f371331a51f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300628"
---
# <a name="compiler-error-c3288"></a>컴파일러 오류 C3288

'type': 핸들 형식에 대 한 역참조가 잘못 되었습니다.

컴파일러는 핸들 형식의 잘못 된 역참조를 발견 했습니다. 핸들 형식 역참조 하 고 참조를 할당할 수 있습니다. 자세한 내용은 [추적 참조 연산자](../../extensions/tracking-reference-operator-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3288를 생성합니다.

```
// C3288.cpp
// compile with: /clr
ref class R {};
int main() {
   *(System::Object^) nullptr;   // C3288

// OK
   (System::Object^) nullptr;   // OK
   R^ r;
   R% pr = *r;
}
```