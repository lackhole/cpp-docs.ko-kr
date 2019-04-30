---
title: 컴파일러 오류 C3101
ms.date: 11/04/2016
f1_keywords:
- C3101
helpviewer_keywords:
- C3101
ms.assetid: 4f673766-d4f7-4632-94a5-d36a83f7f4b5
ms.openlocfilehash: d39afc548010df95bdf31b2c7708bc4fa0310bcd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404197"
---
# <a name="compiler-error-c3101"></a>컴파일러 오류 C3101

명명 된 특성 인수 'field'에 대 한 식이 잘못 되었습니다.

명명 된 특성 인수를 초기화 하는 경우 값은 컴파일 시간 상수 여야 합니다.

특성에 대 한 자세한 내용은 참조 하세요. [사용자 정의 특성](../../extensions/user-defined-attributes-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플 C3101를 생성합니다.

```
// C3101.cpp
// compile with: /clr /c
ref class AAttribute : System::Attribute {
public:
   int Field;
};

extern int i;

[assembly:A(Field = i)];   // C3101
[assembly:A(Field = 0)];   // OK
```