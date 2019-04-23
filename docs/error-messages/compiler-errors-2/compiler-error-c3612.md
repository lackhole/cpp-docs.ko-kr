---
title: 컴파일러 오류 C3612
ms.date: 11/04/2016
f1_keywords:
- C3612
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
ms.openlocfilehash: ab18381d3f263e3207662e1667ac5c835983412f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779117"
---
# <a name="compiler-error-c3612"></a>컴파일러 오류 C3612

'type': 봉인 된 클래스는 abstract 일 수 없습니다.

사용 하 여 정의 된 형식을 `value` 는 기본적으로 sealed 기준의 모든 메서드를 구현 하지 않는 한 클래스는 추상입니다. 봉인 된 추상 클래스에서 기본 클래스도 수 나이 인스턴스화할 수 있습니다.

자세한 내용은 [클래스 및 구조체](../../extensions/classes-and-structs-cpp-component-extensions.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3612를 생성합니다.

```
// C3612.cpp
// compile with: /clr /c
value struct V: public System::ICloneable {};   // C3612

// OK
value struct V2: public System::ICloneable {
   Object^ Clone();
};
```