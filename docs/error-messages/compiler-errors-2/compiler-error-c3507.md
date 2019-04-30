---
title: 컴파일러 오류 C3507
ms.date: 11/04/2016
f1_keywords:
- C3507
helpviewer_keywords:
- C3507
ms.assetid: 75f89767-f6f9-40f6-9820-81a49e09abdf
ms.openlocfilehash: 731e84955192688a87c020b2b65a80ab5671cad6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363936"
---
# <a name="compiler-error-c3507"></a>컴파일러 오류 C3507

ProgID 'id'; 39 개 이하의 문자를 포함할 수 없습니다. 모든 문장 부호를 포함 하거나 '.'; 또는 숫자로 시작

합니다 [progid](../../windows/progid.md) 특성에 사용할 수 있는 값에 제한 사항이 있습니다.

다음 샘플에서는 C3507 오류가 생성 됩니다.

```
// C3507.cpp
[module(name="x")];
[
coclass,
progid("0123456789012345678901234567890123456789"),
uuid("00000000-0000-0000-0000-000000000001") // C3507 expected
]
struct CMyStruct {
};
int main() {
}
```