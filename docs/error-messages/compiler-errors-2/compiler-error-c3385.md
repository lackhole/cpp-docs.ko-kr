---
title: 컴파일러 오류 C3385
ms.date: 11/04/2016
f1_keywords:
- C3385
helpviewer_keywords:
- C3385
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
ms.openlocfilehash: 0cf8f75588339420c688db6e808a62a9fb0ac15c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328772"
---
# <a name="compiler-error-c3385"></a>컴파일러 오류 C3385

'class::function': DllImport 사용자 지정 특성을 가진 함수는 클래스의 인스턴스를 반환할 수 없습니다.

`DllImport` 특성으로 지정된 .dll 파일에 있는 것으로 정의된 함수는 클래스의 인스턴스를 반환할 수 없습니다.

다음 샘플에서는 C3385를 생성합니다.

```
// C3385.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

struct SomeStruct1 {};

public ref struct Wrap {
   [ DllImport("somedll.dll", CharSet=CharSet::Unicode) ]
   static SomeStruct1 f1([In, Out] SomeStruct1 *pS);   // C3385
};
```
