---
title: C++의 전역 상수
ms.date: 11/04/2016
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
ms.openlocfilehash: 2f0621f52fe445f8f2058ef902824ddc1f5e2bb5
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64856099"
---
# <a name="global-constants-in-c"></a>C++의 전역 상수

C++전역 상수에 정적 링크가 있습니다. 3. 다릅니다. 전역 상수를 사용 하려는 경우 C++ 확인 되지 않은 외부 오류가 여러 파일에 표시 합니다. 컴파일러는 변수에 대 한 예약 된 공간이 없습니다, 전역 상수를 최적화 합니다.

이 오류를 해결 하는 한 가지 방법은 헤더 파일에 const 초기화를 포함 하 고 필요한 경우 처럼 함수 프로토타입에서 CPP 파일에서 해당 헤더를 포함 하는 경우 다른 방법은 변수를 비상수 것을 평가할 때에 대 한 상수 참조를 사용 하는 것입니다.

다음 샘플에서는 C2019를 생성합니다.

```cpp
// global_constants.cpp
// LNK2019 expected
void test(void);
const int lnktest1 = 0;

int main() {
   test();
}
```

그리고

```cpp
// global_constants_2.cpp
// compile with: global_constants.cpp
extern int lnktest1;

void test() {
  int i = lnktest1;   // LNK2019
}
```

## <a name="see-also"></a>참고자료

[링커 도구 오류 LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)