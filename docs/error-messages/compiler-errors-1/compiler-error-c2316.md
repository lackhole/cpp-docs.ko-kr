---
title: 컴파일러 오류 C2316
ms.date: 07/08/2019
f1_keywords:
- C2316
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
ms.openlocfilehash: 5a3d9052775a5e1cbedfd58ccaaf0ff039a8475d
ms.sourcegitcommit: 07b34ca1c1fecced9fadc95de15dc5fee4f31e5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67693439"
---
# <a name="compiler-error-c2316"></a>컴파일러 오류 C2316

> '*class_type*': 소멸자 및/또는 복사 생성자는 액세스할 수 없거나 삭제 해 낼 수 없습니다

값 또는 참조 하지만 복사 생성자, 대입 연산자에서 예외가 발생 했습니다 또는 둘 다 액세스할 수 없습니다.

## <a name="remarks"></a>설명

Visual Studio 2015의 규칙 변경에서 파생 된 MFC 예외는 잘못 된 catch 문을 적용이 오류 `CException`합니다. 때문에 `CException` 에 상속 된 전용 복사 생성자가 클래스 및 파생을 복사할 수 없는 값별로 발견 될 수 없습니다. 의미 있는 값으로 전달할 수 없습니다. 이전에 런타임에 확인할 수 없는 예외가 발생 하는 값으로 MFC 예외를 포착 하는 문을 catch 합니다. 이제 컴파일러 올바르게이 상황을 식별 하 고 오류 C2316을 보고 합니다. 이 문제를 해결 하려면 MFC TRY/CATCH 매크로 사용 하지 않고 있습니다 고유한 예외 처리기를 작성 하는 것이 좋습니다. 코드에 적합 하지 않은 경우 MFC 예외를 대신 참조로 catch 합니다.

## <a name="example"></a>예제

다음 샘플 C2316을 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C2316.cpp
// compile with: /EHsc
#include <stdio.h>

struct B
{
public:
    B() {}
    // Delete the following line to resolve.
private:
    // copy constructor
    B(const B&) {}
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
    catch (B b)    // C2316
    {
        printf_s("Caught an exception!\n");
    }
}
```
