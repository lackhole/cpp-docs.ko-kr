---
title: 컴파일러 오류 C2430
ms.date: 11/04/2016
f1_keywords:
- C2430
helpviewer_keywords:
- C2430
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
ms.openlocfilehash: 754758e652539e4f2d9b12e568b8ef5ccf41d8db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165699"
---
# <a name="compiler-error-c2430"></a>컴파일러 오류 C2430

'identifier'에 둘 이상의 인덱스 등록

둘 이상의 등록 크기가 조정 됩니다. 컴파일러는 배율 조정 된 인덱싱을 지원 하지만 하나의 등록 확장할 수 있습니다.

## <a name="example"></a>예제

다음 샘플 C2430를 생성합니다.

```
// C2430.cpp
// processor: x86
int main() {
   _asm mov eax, [ebx*2+ecx*4] // C2430
}
```