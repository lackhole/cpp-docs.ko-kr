---
title: 수학 오류 M6201
ms.date: 11/04/2016
f1_keywords:
- M6201
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
ms.openlocfilehash: 6d3f107de7e45653374036ecafaa864cb3eff5b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393248"
---
# <a name="math-error-m6201"></a>수학 오류 M6201

'function': 오류 (_d)

지정된 된 함수에 인수로 함수에 대 한 유효한 입력된 값의 도메인을 벗어났습니다.

## <a name="example"></a>예제

```
result = sqrt(-1.0)   // C statement
result = SQRT(-1.0)   !  FORTRAN statement
```

이 오류를 호출 합니다 `_matherr` 함수 이름, 해당 인수 및 오류 유형을 사용 하 여 함수입니다. 다시 작성할 수 있습니다는 `_matherr` 특정 런타임 부동 소수점 수학 오류 처리 사용자 지정 하는 함수입니다.