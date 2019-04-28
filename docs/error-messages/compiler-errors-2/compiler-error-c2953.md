---
title: 컴파일러 오류 C2953
ms.date: 11/04/2016
f1_keywords:
- C2953
helpviewer_keywords:
- C2953
ms.assetid: 8dbcfa24-8296-4e40-bdc4-5526c07d8892
ms.openlocfilehash: 8fa0e533b23f735f948fdad0ecf11beb3766f452
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187627"
---
# <a name="compiler-error-c2953"></a>컴파일러 오류 C2953

'identifier': 클래스 템플릿이 이미 정의되었습니다.

소스 파일을 확인하고 다른 정의에 대한 파일을 포함합니다.

다음 샘플에서는 C2953을 생성합니다.

```
// C2953.cpp
// compile with: /c
template <class T>  class A {};
template <class T>  class A {};   // C2953
template <class T>  class B {};   // OK
```