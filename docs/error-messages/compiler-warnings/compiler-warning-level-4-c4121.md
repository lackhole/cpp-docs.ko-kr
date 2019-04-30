---
title: 컴파일러 경고 (수준 4) C4121
ms.date: 11/04/2016
f1_keywords:
- C4121
helpviewer_keywords:
- C4121
ms.assetid: 8c5b85c9-2543-426b-88bc-319c50158c7e
ms.openlocfilehash: 0d02c5aff188a82062ae537f053157795d8925d8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401373"
---
# <a name="compiler-warning-level-4-c4121"></a>컴파일러 경고 (수준 4) C4121

'symbol' : 멤버의 맞춤은 압축에 민감했음

컴파일러가 압축 경계의 구조체 멤버를 맞추기 위해 안쪽 여백을 추가하였지만 압축 값은 멤버의 크기보다 적습니다. 예를 들어 다음 코드 조각은 C4121를 생성합니다.

```
// C4121.cpp
// compile with: /W4 /c
#pragma pack(2)
struct s
{
   char a;
   int b; // C4121
   long long c;
};
```

이 문제를 해결하려면 다음 중 하나를 변경하십시오.

- 압축 크기를 경고를 발생시킨 멤버의 크기 이상으로 변경합니다. 예를 들어 이 조각에서는 `pack(2)`을 `pack(4)` 또는 `pack(8)`으로 변경합니다.

- 멤버 선언을 크기별로 내림차순으로 다시 정렬합니다. 조각에서 `long long` 멤버가 `int` 앞에 오고 `int`가 `char` 앞에 오도록 구조체 멤버의 순서를 역순으로 바꿉니다.

이 경고는 컴파일러가 데이터 멤버 앞에 압축을 추가할 때만 발생합니다. 압축이 데이터 형식에 맞추지 않은 메모리 위치에 데이터를 배치했지만 안쪽 여백이 데이터 멤버 앞에 배치되지 않을 때는 발생하지 않습니다. 데이터가 데이터 크기의 배수인 경계에 맞추지 않으면 성능이 저하될 수 있습니다. 맞추지 않은 데이터의 읽기 및 쓰기로 인해 일부 아키텍처에 프로세스 오류가 발생할 수 있고 오류를 해결하려면 두 배나 세 배의 시간이 걸릴 수 있습니다. 맞추지 않은 데이터 액세스는 일부 RISC 아키텍처에 이식할 수 없습니다.

사용할 수 있습니다 [#pragma 팩](../../preprocessor/pack.md) 하거나 [/Zp](../../build/reference/zp-struct-member-alignment.md) 구조체 맞춤을 지정 합니다. (컴파일러 때이 경고를 생성 하지 않습니다 **/Zp1** 지정 됩니다.)