---
title: 컴파일러 오류 C2286
ms.date: 11/04/2016
f1_keywords:
- C2286
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
ms.openlocfilehash: 7d3b8297c5f5da29b99abe78999396e8c44df0fd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182771"
---
# <a name="compiler-error-c2286"></a>컴파일러 오류 C2286

'identifier' 표현의 멤버에 대 한 포인터 선언이 무시 됩니다. '상속'-이미 설정 되어

클래스에 대 한 두 가지 다른 멤버에 대 한 포인터 표현이 존재 합니다.

자세한 내용은 [상속 키워드](../../cpp/inheritance-keywords.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2286을 생성합니다.

```
// C2286.cpp
// compile with: /c
class __single_inheritance X;
class __multiple_inheritance X;   // C2286
class  __multiple_inheritance Y;   // OK
```