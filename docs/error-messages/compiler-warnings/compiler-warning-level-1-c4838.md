---
title: 컴파일러 경고 (수준 1) C4838
ms.date: 11/04/2016
f1_keywords:
- C4838
helpviewer_keywords:
- C4838
ms.assetid: fea07924-5feb-4ed4-99b5-1a8c41d28db6
ms.openlocfilehash: dcb7062c751320a9f9c612b42caf6d018047d8d2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380840"
---
# <a name="compiler-warning-level-1-c4838"></a>컴파일러 경고 (수준 1) C4838

'type_1'에서 'type_2' 변환에 축소 변환을 수행 해야

집계 또는 목록 초기화를 사용 하는 경우 암시적 축소 변환을 찾을 수 있습니다.

C 언어에서 할당 및 초기화에 암시적 축소 변환을 허용 하 고 C++ 많은 코드 오류의 원인인 예기치 않은 축소 하는 경우에 다음과 같이 적합 합니다. 안전 하며 코드를 확인 하는 C++ 표준 축소 변환을 초기화 목록에서 발생 하는 경우 진단 메시지에 필요한 합니다. 시각적 개체의 C++에서 진단이 [컴파일러 오류 C2397](../../error-messages/compiler-errors-1/compiler-error-c2397.md) Visual Studio 2015부터 지원 되는 균일 초기화 구문을 사용 하는 경우. 컴파일러는 C4838 목록 또는 Visual Studio 2013에서 지원 되는 집계 초기화 구문을 사용 하는 경우 경고를 생성 합니다.

변환 된 값의 가능한 범위는 대상에 맞출 수 있는 경우에 축소 변환 해도 수 있습니다. 이 경우 알고 컴파일러 이상. 축소 변환을 의도적으로 하는 경우 확인의 의도 명시적 정적 캐스트를 사용 하 여 합니다. 그렇지 않은 경우이 경고 메시지 코드에 버그가 있다고 거의 항상 나타냅니다. 입력을 처리 하기에 충분히 초기화 하면 개체 형식이 확인 하 여 해결할 수 있습니다.

다음 샘플 C4838 생성 및이 해결 하는 방법을 보여 줍니다.

```
// C4838.cpp -- C++ narrowing conversion diagnostics
// Compile by using: cl /EHsc C4838.cpp

struct S1 {
    int m1;
    double m2, m3;
};

void function_C4838(double d1) {
    double ad[] = { 1, d1 }; // OK
    int ai[] = { 1, d1 };    // warning C4838
    S1 s11 = { 1, 2, d1 };   // OK
    S1 s12 { d1, 2, 3 };     // warning C4838
    S1 s13 { static_cast<int>(d1), 2, 3 }; // possible fix for C4838
}
```