---
title: 컴파일러 오류 C2720
ms.date: 11/04/2016
f1_keywords:
- C2720
helpviewer_keywords:
- C2720
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
ms.openlocfilehash: c6499fd3f279099ea7c5b31860e70bdaa285e3f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383050"
---
# <a name="compiler-error-c2720"></a>컴파일러 오류 C2720

> '*식별자*': '*지정자*' 멤버에 잘못 된 저장소 클래스 지정자

선언 외부의 클래스 멤버에서 스토리지 클래스를 사용할 수 없습니다. 이 오류를 해결 하려면 불필요 한 제거 [저장소 클래스](../../cpp/storage-classes-cpp.md) 클래스 선언 외부 멤버의 정의에서 지정자입니다.

## <a name="example"></a>예제

다음 샘플에서는 C2720 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.

```cpp
// C2720.cpp
struct S {
   static int i;
};
static S::i;   // C2720 - remove the unneeded 'static' to fix it
```