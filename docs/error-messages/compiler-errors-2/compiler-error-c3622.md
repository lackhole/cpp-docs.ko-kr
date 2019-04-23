---
title: 컴파일러 오류 C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: ed307f46db1261d79d5b0ec6b36852cac2e6d13e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776121"
---
# <a name="compiler-error-c3622"></a>컴파일러 오류 C3622

'class': 'keyword'를 인스턴스화할 수 없는 클래스 선언

로 표시 된 클래스를 인스턴스화하려고 했습니다 [추상](../../extensions/abstract-cpp-component-extensions.md)합니다. 로 표시 된 클래스가 `abstract` 기본 클래스로 사용할 수 있지만 인스턴스화할 수 없습니다.

## <a name="example"></a>예제

다음 샘플 C3622를 생성합니다.

```
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
