---
title: 컴파일러 오류 C3880
ms.date: 11/04/2016
f1_keywords:
- C3880
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
ms.openlocfilehash: 0b169309db88291f8a83b6d1192787b6396e84a5
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770504"
---
# <a name="compiler-error-c3880"></a>컴파일러 오류 C3880

'var': 리터럴 데이터 멤버가 될 수 없습니다.

형식의 [리터럴](../../extensions/literal-cpp-component-extensions.md) 설정 해야 합니다 또는 컴파일 타임 다음 형식 중 하나로 변환할:

- 정수 계열 형식

- string

- 정수 계열 또는 기본 형식 사용 하 여 열거형

다음 샘플에서는 C3880 오류가 생성 됩니다.

```
// C3880.cpp
// compile with: /clr /c
ref struct Y1 {
   literal System::Decimal staticConst1 = 10;   // C3880
   literal int staticConst2 = 10;   // OK
};
```