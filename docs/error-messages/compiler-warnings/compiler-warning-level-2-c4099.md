---
title: 컴파일러 경고 (수준 2) C4099
ms.date: 11/04/2016
f1_keywords:
- C4099
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
ms.openlocfilehash: d685f1f40826b975623dbedc2ba8115c6b3edc45
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052174"
---
# <a name="compiler-warning-level-2-c4099"></a>컴파일러 경고 (수준 2) C4099

' identifier ': ' objecttype1 '를 사용 하 여 먼저 ' objecttype2 '를 사용 하 여 표시 한 형식 이름입니다.

구조체로 선언 된 개체가 클래스로 정의 되거나 클래스로 선언 된 개체가 구조체로 정의 됩니다. 컴파일러는 정의에 지정 된 형식을 사용 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4099를 생성 합니다.

```cpp
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```