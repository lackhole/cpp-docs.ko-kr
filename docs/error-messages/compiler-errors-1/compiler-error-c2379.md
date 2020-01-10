---
title: 컴파일러 오류 C2379
ms.date: 11/04/2016
f1_keywords:
- C2379
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
ms.openlocfilehash: f096791a6120023e079b93452a4b35c669db2139
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302109"
---
# <a name="compiler-error-c2379"></a>컴파일러 오류 C2379

승격 시 형식 매개 변수 번호의 형식이 다릅니다.

지정 된 매개 변수의 형식은 이전 선언의 형식과 함께 기본 승격을 통해 호환 되지 않습니다. 이 오류는 ANSI C ([/za](../../build/reference/za-ze-disable-language-extensions.md))의 오류 이며 Microsoft 확장 ( **/ze**)을 사용 하는 경고입니다.

다음 샘플에서는 C2379를 생성 합니다.

```c
// C2379.c
// compile with: /Za
void func();
void func(char);   // C2379, char promotes to int
```
