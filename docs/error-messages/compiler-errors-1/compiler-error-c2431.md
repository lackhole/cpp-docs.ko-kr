---
title: 컴파일러 오류 C2431
ms.date: 11/04/2016
f1_keywords:
- C2431
helpviewer_keywords:
- C2431
ms.assetid: 88a5b648-c89f-47d1-a20e-63231ab4f0f7
ms.openlocfilehash: 6298748b341d58c5d931566f714530a4858e46ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165881"
---
# <a name="compiler-error-c2431"></a>컴파일러 오류 C2431

'identifier'에 잘못 된 인덱스 레지스터

ESP 등록을 크기 조정 또는 인덱스와 기본 등록으로 사용 합니다. X86 프로세서 중 하나를 허용 하지 않습니다 인코딩에 형제입니다.

다음 샘플에서는 C2431 오류가 생성 됩니다.

```
// C2431.cpp
// processor: x86
int main() {
   _asm mov ax, [ESI + 2*ESP]   // C2431
   _asm mov ax, [esp + esp]   // C2431
}
```