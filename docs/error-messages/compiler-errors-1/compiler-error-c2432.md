---
title: 컴파일러 오류 C2432
ms.date: 11/04/2016
f1_keywords:
- C2432
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
ms.openlocfilehash: e2983d966a6290ce19713c63feb502c8ffc74bf1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166843"
---
# <a name="compiler-error-c2432"></a>컴파일러 오류 C2432

잘못 된 16 비트 데이터에에서 대 한 'identifier'

16 비트 레지스터 인덱스 또는 기본 등록으로 사용 됩니다. 컴파일러는 16 비트 데이터 참조를 지원 하지 않습니다. 32 비트 코드를 컴파일할 때에 인덱스 또는 기본 등록으로 16 비트 레지스터를 사용할 수 없습니다.

다음 샘플에서는 C2432 오류가 생성 됩니다.

```
// C2432.cpp
// processor: x86
int main() {
   _asm mov eax, DWORD PTR [bx]   // C2432
}
```