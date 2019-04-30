---
title: 컴파일러 오류 C2390
ms.date: 11/04/2016
f1_keywords:
- C2390
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
ms.openlocfilehash: 89f6ebb02326413e8dca67d333e555321da4e645
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393638"
---
# <a name="compiler-error-c2390"></a>컴파일러 오류 C2390

'identifier': 'specifier' 잘못 된 저장소 클래스

저장소 클래스가 전역 범위 식별자에 대해 올바르지 않습니다. 기본 저장소 클래스는 잘못 된 클래스 대신 사용 됩니다.

가능한 해결 방법:

- 식별자가 함수를 사용 하 여 선언 `extern` 저장소입니다.

- 식별자가 정식 매개 변수 또는 로컬 변수를 자동 저장소를 사용 하 여 선언 합니다.

- 식별자가 전역 변수, 저장소 클래스 (자동 저장소) 없이 선언 합니다.

## <a name="example"></a>예제

- 다음 샘플에서는 C2390 오류가 생성 됩니다.

```
// C2390.cpp
register int i;   // C2390

int main() {
   register int j;   // OK
}
```