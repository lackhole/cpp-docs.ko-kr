---
title: 컴파일러 오류 C3400
ms.date: 11/04/2016
f1_keywords:
- C3400
helpviewer_keywords:
- C3400
ms.assetid: d44169a8-73b6-4766-b406-b3a6c93f2a4d
ms.openlocfilehash: c4b4cb64da83115ab5b6a5234cda2ea3c7ba3a53
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768629"
---
# <a name="compiler-error-c3400"></a>컴파일러 오류 C3400

'constraint_1' 및 'constraint_2'와 관련된 순환 제약 조건 종속성입니다.

컴파일러가 순환 제약 조건을 검색했습니다.

자세한 내용은 [제네릭 형식 매개 변수에 대 한 제약 조건 (C + + CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C3400을 생성합니다.

```
// C3400.cpp
// compile with: /clr /c
generic<class T, class U>
where T : U
where U : T   // C3400
public ref struct R {};
```