---
title: 컴파일러 경고(수준 4) C4207
ms.date: 11/04/2016
f1_keywords:
- C4207
helpviewer_keywords:
- C4207
ms.assetid: f4e09e3e-ac87-4489-8e3f-c8f76b82e721
ms.openlocfilehash: 44f49705bf197d7a42b80e50983e47a4c0ce7bed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401204"
---
# <a name="compiler-warning-level-4-c4207"></a>컴파일러 경고(수준 4) C4207

비표준 확장이 사용 됨: 확장 이니셜라이저 형식

Microsoft 확장명 (/Ze)으로 크기가 지정 되지 않은 배열을 초기화할 수 있습니다 `char` 중괄호 내에 있는 문자열을 사용 합니다.

## <a name="example"></a>예제

```
// C4207.c
// compile with: /W4
char c[] = { 'a', 'b', "cdefg" }; // C4207

int main()
{
}
```

이러한 초기화는 ANSI 호환성 사용할 수 없습니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).