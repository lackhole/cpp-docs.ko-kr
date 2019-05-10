---
title: 컴파일러 경고(수준 1) C4530
ms.date: 11/04/2016
f1_keywords:
- C4530
helpviewer_keywords:
- C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
ms.openlocfilehash: a542f9b6bb73e561592e1e779aa6ee493612e6ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160720"
---
# <a name="compiler-warning-level-1-c4530"></a>컴파일러 경고(수준 1) C4530

C++예외 처리기가 사용 되었지만 해제 의미 체계가 활성화 되지 않았습니다. /EHsc를 지정 합니다.

C++예외 처리를 사용 하지만 [/EHsc](../../build/reference/eh-exception-handling-model.md) 선택 하지 않았습니다.

/EHsc 옵션을 설정 하지 프레임의 throw 및 catch 하는 함수 사이 자동 저장소를 사용 하 여 개체 소멸 되지 않습니다. 그러나 자동 저장소를 사용 하 여 개체에서 생성 되는를 **시도** 또는 **catch** 블록 제거 됩니다.

다음 샘플에서는 C4530 오류가 생성 됩니다.

```
// C4530.cpp
// compile with: /W1
int main() {
   try{} catch(int*) {}   // C4530
}
```

경고를 해결 하려면 /EHsc를 사용 하 여 예제를 컴파일하십시오.