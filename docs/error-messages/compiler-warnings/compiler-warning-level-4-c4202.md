---
title: 컴파일러 경고(수준 4) C4202
ms.date: 11/04/2016
f1_keywords:
- C4202
helpviewer_keywords:
- C4202
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
ms.openlocfilehash: c66e2243ee5eca55105de27c9824ee8ced338500
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401269"
---
# <a name="compiler-warning-level-4-c4202"></a>컴파일러 경고(수준 4) C4202

비표준 확장이 사용 됨: '...': 프로토타입 매개 변수가 이름 목록이 잘못 되었습니다.

이전 스타일 함수 정의는 가변 인수가 들어 있습니다. 이러한 정의 ANSI 호환성 오류를 생성 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>예제

```
// C4202.c
// compile with: /W4
void func( a, b, ...)   // C4202
int a, b;
{}

int main()
{
}
```