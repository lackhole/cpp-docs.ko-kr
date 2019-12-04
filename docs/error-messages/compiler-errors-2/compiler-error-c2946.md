---
title: 컴파일러 오류 C2946
ms.date: 11/04/2016
f1_keywords:
- C2946
helpviewer_keywords:
- C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
ms.openlocfilehash: c0ea10b3614e20e7f47c8f6632843544b4842751
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755371"
---
# <a name="compiler-error-c2946"></a>컴파일러 오류 C2946

명시적 인스턴스화. 'class'는 템플릿-클래스 특수화가 아닙니다.

템플릿이 아닌 클래스를 명시적으로 인스턴스화할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2946을 생성합니다.

```cpp
// C2946.cpp
class C {};
template C;  // C2946
int main() {}
```
