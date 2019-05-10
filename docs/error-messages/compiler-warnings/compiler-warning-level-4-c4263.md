---
title: 컴파일러 경고(수준 4) C4263
ms.date: 11/04/2016
f1_keywords:
- C4263
helpviewer_keywords:
- C4263
ms.assetid: daabb05d-ab56-460f-ab6c-c74d222ef649
ms.openlocfilehash: a035646aab2589523adb9eb0b201e2d4d781632c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400931"
---
# <a name="compiler-warning-level-4-c4263"></a>컴파일러 경고(수준 4) C4263

'function': 멤버 함수가 기본 클래스 가상 멤버 함수를 재정의 하지 않습니다

클래스 함수 정의의 기본 클래스 하지만 하지 만큼 인수의 형식이 가상 함수와 이름이 같은 합니다. 이 기본 클래스의 가상 함수를 효과적으로 숨깁니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

다음 샘플에서는 C4263 오류가 생성 됩니다.

```
// C4263.cpp
// compile with: /W4
#pragma warning(default:4263)
#pragma warning(default:4264)
class B {
public:
   virtual void func();
};

class D : public B {
   void func(int);   // C4263
};

int main() {
}
```