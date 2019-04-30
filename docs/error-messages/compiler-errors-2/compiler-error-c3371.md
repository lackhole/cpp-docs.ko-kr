---
title: 컴파일러 오류 C3371
ms.date: 11/04/2016
f1_keywords:
- C3371
helpviewer_keywords:
- C3371
ms.assetid: f7ecf1aa-ed0a-4f73-81e5-62cf98f88ea1
ms.openlocfilehash: 7967f6fa92434dcac35ec732f42a32531bfcce03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300494"
---
# <a name="compiler-error-c3371"></a>컴파일러 오류 C3371

'idl_module': 여기서는 'name' 속성만 사용할 수 있습니다.

함수 선언에서 직접[idl_module](../../windows/idl-module.md) 을 사용할 때 이름 이외의 매개 변수를 가질 수 없습니다.

다음 샘플에서는 C3371을 생성합니다.

```
// C3371.cpp
[idl_module(name="Name", dllname="Some.dll")];
[idl_module(name="Name", helpstring="Some help")]   // C3371
int f1();
// try
// [idl_module(name="Name")]
// int f1();

int main()
{
}
```