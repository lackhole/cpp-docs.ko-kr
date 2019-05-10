---
title: 컴파일러 오류 C2316
ms.date: 11/04/2016
f1_keywords:
- C2316
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
ms.openlocfilehash: 53e7743ec0d84451feb1dc1cd8849439aa142336
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345720"
---
# <a name="compiler-error-c2316"></a>컴파일러 오류 C2316

> '*예외*': 소멸자 및/또는 복사 생성자에 액세스할 수 없는 대로 낼 수 없습니다

값별 또는 참조별 예외가 catch되었지만 복사 생성자 및/또는 대입 연산자에 액세스할 수 없습니다.

이 코드는 시각적 개체의 버전에서 허용 된 C++ Visual Studio 2003 전에 하지만 이제는 오류를 제공 합니다.

Visual Studio 2015의 규칙 변경에서 파생 된 MFC 예외는 잘못 된 catch 문을 적용이 오류 `CException`합니다. 때문에 `CException` 에 상속 된 전용 복사 생성자가 클래스 및 파생 복사할 값별로 발견 될 수 없습니다. 의미 있는 값으로 전달할 수 없습니다. Catch 문은 런타임에 예외를 확인할 수 없는 이전에 발생 하는 값으로 MFC 예외를 포착 하는 하지만 이제 컴파일러 올바르게 식별이 상황과 보고서 오류 C2316 합니다. 이 문제를 해결 하려면 사용자 고유의 예외 처리기를 작성 하지만 코드에 적합 하지 않은 경우 예외를 catch MFC 참조로 대신 것이 아니라 MFC TRY/CATCH 매크로 사용 하는 것이 좋습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2316을 생성합니다.

```
// C2316.cpp
// compile with: /EHsc
#include <stdio.h>

extern "C" int printf_s(const char*, ...);

struct B
{
public:
    B() {}
    // Delete the following line to resolve.
private:
    // copy constructor
    B(const B&)
    {
    }
};

void f(const B&)
{
}

int main()
{
    try
    {
        B aB;
        f(aB);
    }
    catch (B b) {   // C2316
        printf_s("Caught an exception!\n");
    }
}
```