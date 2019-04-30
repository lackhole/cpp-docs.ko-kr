---
title: 컴파일러 오류 C3141
ms.date: 11/04/2016
f1_keywords:
- C3141
helpviewer_keywords:
- C3141
ms.assetid: b4fd65c3-50cc-46cd-8de0-6a6d24cb9cda
ms.openlocfilehash: e19de95b5b2c967d71a4b06aca431df8ffe9dc14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374939"
---
# <a name="compiler-error-c3141"></a>컴파일러 오류 C3141

'interface_name': 인터페이스에는 공용 상속만 지원

사용 하 여 정의 된 인터페이스를 [인터페이스 (또는 __interface)](../../cpp/interface.md) 키워드에는 공용 상속만 지원 합니다.

다음 샘플에서는 C3141 오류가 생성 됩니다.

```
// C3141.cpp
__interface IBase {};
__interface IDerived1 : protected IBase {};  // C3141
__interface IDerived2 : private IBase {};    // C3141
```