---
title: 컴파일러 경고(수준 4) C4233
ms.date: 10/25/2017
f1_keywords:
- C4233
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
ms.openlocfilehash: 361e00b7361aab51ea077d7e248503f3654e5e58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401061"
---
# <a name="compiler-warning-level-4-c4233"></a>컴파일러 경고(수준 4) C4233

> 비표준 확장이 사용 됨: '*키워드*' 에서만 지원 되는 키워드 C++, C 아님

컴파일러가 소스 코드를 C로 컴파일된 대신 C++, 사용할 수 있는 키워드에만 유효 하 고 C++. 컴파일러가 소스 파일의 확장명은.c 또는 사용 하는 경우 C로 소스 파일을 컴파일합니다 [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)합니다.

이 경고는 오류를 자동으로 승격 됩니다. 사용 하 여이 동작을 수정 하려는 경우 [#pragma 경고](../../preprocessor/warning.md)합니다. 예를 들어,를 수준 4 경고로 4233, 소스 코드 파일에이 줄을 추가 합니다.

```cpp
#pragma warning(4:4233)
```
