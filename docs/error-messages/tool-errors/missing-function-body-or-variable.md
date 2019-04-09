---
title: 함수 본문 또는 변수 누락
ms.date: 11/04/2016
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
ms.openlocfilehash: c287d804df3222475d7cf32c6eb025f642dfb913
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031862"
---
# <a name="missing-function-body-or-variable"></a>함수 본문 또는 변수 누락

함수 프로토타입을 사용 하 여 컴파일러 오류 없이 계속할 수 있지만 함수 코드 또는 예약 된 변수 공간이 없을 링커 주소에 대 한 호출을 확인할 수 없습니다. 링커를 해결 해야 하는 함수에 대 한 호출을 만들 때까지이 오류가 표시 되지 않습니다.

## <a name="example"></a>예제

Main 함수 호출의 프로토타입 함수가 존재 생각 하는 컴파일러를 허용 하기 때문에 lnk2019가 발생 합니다.  링커를 찾지 못합니다.

```
// LNK2019_MFBV.cpp
// LNK2019 expected
void DoSomething(void);
int main() {
   DoSomething();
}
```

## <a name="example"></a>예제

C + +에서는 클래스 정의에서 클래스 및 프로토타입 뿐 아니라 특정 함수의 구현이 포함 해야 합니다. 헤더 파일 외부에서 클래스를 정의 하는 경우 포함 해야 함수 전의 클래스 이름 (`Classname::memberfunction`).

```
// LNK2019_MFBV_2.cpp
// LNK2019 expected
struct A {
   static void Test();
};

// Should be void A::Test() {}
void Test() {}

int main() {
   A AObject;
   AObject.Test();
}
```

## <a name="see-also"></a>참고자료

[링커 도구 오류 LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)