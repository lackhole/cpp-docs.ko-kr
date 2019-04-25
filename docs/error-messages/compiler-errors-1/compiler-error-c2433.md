---
title: 컴파일러 오류 C2433
ms.date: 11/04/2016
f1_keywords:
- C2433
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
ms.openlocfilehash: 8a98fcf7570605694569b7ae466ae0a3c7cf14bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62166739"
---
# <a name="compiler-error-c2433"></a>컴파일러 오류 C2433

'identifier': 'modifier' 데이터 선언에서 허용 되지 않습니다

합니다 `friend`, `virtual`, 및 `inline` 데이터 선언에 대 한 한정자를 사용할 수 없습니다.

## <a name="example"></a>예제

다음 샘플에서는 C2433 오류가 발생 합니다.

```
// C2433.cpp
class C{};

int main() {
   inline C c;   // C2433
}
```