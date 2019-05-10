---
title: 컴파일러 경고(수준 4) C4256
ms.date: 11/04/2016
f1_keywords:
- C4256
helpviewer_keywords:
- C4256
ms.assetid: a755a32e-895a-4837-a2b5-4ea06b736798
ms.openlocfilehash: 3e8a3ab1b11c719730016e6a0cd248770cd89af8
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447780"
---
# <a name="compiler-warning-level-4-c4256"></a>컴파일러 경고(수준 4) C4256

'function': 가상 기본 클래스 생성자가 '...'; 호출은 시각적 개체의 이전 버전과 호환 되지 않을 수 있습니다.C++

호환 되지 않을 수도 있습니다.

다음 코드 예제를 살펴봅니다. 경우 생성자 S2::S2 정의 (int i,...)는 Microsoft의 버전을 사용 하 여 컴파일된 C++ 현재 버전을 사용해 서 컴파일된 버전 7, 하지만 다음 예제에서는 이전 컴파일러, S3에 대 한 생성자 호출 올바르게 작동 하지 않습니다. 특별 한 경우 호출 규칙 변경 합니다. 두 항목이 모두 Visual C++ 6.0을 사용해서 컴파일된 경우, 줄임표에 대해 전달된 매개 변수가 없지 않은 한 어느 항목에서도 호출이 올바르게 작동하지 않습니다.

이 경고를 해결 하려면

1. 생성자에서 줄임표 (...)를 사용 하지 마세요.

1. 해당 프로젝트의 모든 구성 요소 (라이브러리를 정의 하거나이 클래스를 참조 하는 포함), 현재 버전을 사용 하 여 빌드됩니다 다음이 사용 하 여 경고를 사용 하지 않도록 설정 하는 있는지 확인 합니다 [경고](../../preprocessor/warning.md) pragma입니다.

다음 샘플에서는 C4256 오류가 생성 됩니다.

```
// C4256.cpp
// compile with: /W4
// #pragma warning(disable : 4256)
struct S1
{
};

struct S2: virtual public S1
{
   S2( int i, ... )    // C4256
   {
      i = 0;
   }
   /*
   // try the following line instead
   S2( int i)
   {
      i = 0;
   }
   */
};

void func1()
{
   S2 S3( 2, 1, 2 );   // C4256
   // try the following line instead
   // S2 S3( 2 );
}

int main()
{
}
```