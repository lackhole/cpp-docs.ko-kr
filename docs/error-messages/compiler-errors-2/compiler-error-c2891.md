---
title: 컴파일러 오류 C2891
ms.date: 11/04/2016
f1_keywords:
- C2891
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
ms.openlocfilehash: d9a1cdafdf7d3a2843aee4a20f71c7e6a4693150
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366370"
---
# <a name="compiler-error-c2891"></a>컴파일러 오류 C2891

'parameter': 템플릿 매개 변수의 주소를 가져올 수 없습니다.

lvalue가 아닌 경우에 템플릿 매개 변수의 주소를 사용할 수 없습니다. 형식 매개 변수 주소가 없기 때문에 lvalue 않습니다. Lvalue 없는 템플릿 매개 변수 목록에 비형식 값도 수행 주소가 없습니다. 템플릿 매개 변수로 전달 된 값은 템플릿 인수 컴파일러에서 생성 된 복사본 이므로 이것이 컴파일러 오류 C2891 발생 하는 코드의 예입니다.

```
template <int i> int* f() { return &i; }
```

참조 형식과 같이 lvalue는 템플릿 매개 변수 수 주소로 수행 합니다.

```
template <int& r> int* f() { return &r; }
```

이 오류를 해결 하려면 lvalue 경우가 템플릿 매개 변수의 주소를 사용 하지 않습니다.