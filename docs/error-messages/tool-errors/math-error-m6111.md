---
title: 수학 오류 M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: 44f406881d64d13e23ca2c0911ee278c864a2c11
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393410"
---
# <a name="math-error-m6111"></a>수학 오류 M6111

언더플로 스택

부동 소수점 연산 8087/287 387 프로세서 또는 에뮬레이터에는 스택 언더플로 했습니다.

이 오류는 호출 하 여 자주 발생을 `long double` 함수 값을 반환 하지 않습니다. 예를 들어, 다음이 오류를 생성 컴파일 및 실행 하는 경우:

```
long double ld() {};
main ()
{
  ld();
}
```

프로그램은 139 종료 코드로 종료 됩니다.