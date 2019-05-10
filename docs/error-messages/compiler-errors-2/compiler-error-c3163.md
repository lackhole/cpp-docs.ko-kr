---
title: 컴파일러 오류 C3163
ms.date: 11/04/2016
f1_keywords:
- C3163
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
ms.openlocfilehash: eda3910c99f4c8ea96568f2d475c5d6a1e4cdc7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174227"
---
# <a name="compiler-error-c3163"></a>컴파일러 오류 C3163

'construct': 특성이 이전 선언과 일관성이 없습니다

정의에 적용 되는 특성 선언에 적용 되는 특성을 사용 하 여 충돌 합니다.

C3163를 해결 하는 방법을 정방향 선언에 특성을 제거 하는 경우 모든 특성에 대 한 정방향 선언 해야 정의 특성 보다 작을 수 또는 같아야 합니다를.

C3163 오류의 가능한 원인은 Microsoft 소스 코드 주석 언어 (SAL) 포함 됩니다. SAL 매크로가 확장 하지 않고 프로젝트를 사용 하 여 컴파일하지 않으면 합니다 **/analyze** 플래그입니다. 없이 정상적으로 컴파일한 / 분석 하는 프로그램을 사용 하 여 다시 컴파일을 시도 하면 C3163 throw 할 수 있습니다는 /analyze 옵션입니다. SAL에 대 한 자세한 내용은 참조 하세요. [SAL 주석은](../../c-runtime-library/sal-annotations.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3163를 생성합니다.

```
// C3163.cpp
// compile with: /clr /c
using namespace System;

[CLSCompliant(true)] void f();
[CLSCompliant(false)] void f() {}   // C3163
// try the following line instead
// [CLSCompliant(true)] void f() {}
```

## <a name="see-also"></a>참고자료

[SAL 주석](../../c-runtime-library/sal-annotations.md)