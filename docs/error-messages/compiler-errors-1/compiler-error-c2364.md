---
title: 컴파일러 오류 C2364
ms.date: 11/04/2016
f1_keywords:
- C2364
helpviewer_keywords:
- C2364
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
ms.openlocfilehash: 051468ea861190dd3f6a28dc272f1bab155145af
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230401"
---
# <a name="compiler-error-c2364"></a>컴파일러 오류 C2364

'type': 사용자 지정 특성 형식이 잘못 되었습니다.

사용자 지정 특성에 대 한 명명 된 인수는 컴파일 시간 상수로 제한 합니다. 정수 계열 형식 예를 들어 (int, char 등), system:: type ^, 및 system:: object ^ 합니다.

## <a name="example"></a>예제

다음 샘플 C2364를 생성합니다.

```
// c2364.cpp
// compile with: /clr /c
using namespace System;

[attribute(AttributeTargets::All)]
public ref struct ABC {
public:
   // Delete the following line to resolve.
   ABC( Enum^ ) {}   // C2364
   ABC( int ) {}   // OK
};
```