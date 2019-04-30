---
title: 컴파일러 경고(수준 3) C4535
ms.date: 11/04/2016
f1_keywords:
- C4535
helpviewer_keywords:
- C4535
ms.assetid: 2c5ad1aa-2558-41d1-8f06-47fef74c8d9b
ms.openlocfilehash: 2483e5803c5de7d63bd2fa9fed97730b7c894137
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401867"
---
# <a name="compiler-warning-level-3-c4535"></a>컴파일러 경고(수준 3) C4535

calling _set_se_translator() requires /EHa

사용 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) 필요 합니다 [/EHa](../../build/reference/eh-exception-handling-model.md) 컴파일러 옵션 및 not **/EHs**합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4535 오류가 발생 합니다.

```
// C4535.cpp
// compile with: /W3 /EHsc /c
// C4535 expected
// to fix, compile with /EHa instead
#include <stdio.h>
#include <windows.h>
#include <eh.h>

void SEFunc();
void trans_func( unsigned int, EXCEPTION_POINTERS* );

class SE_Exception {
private:
   unsigned int nSE;
public:
   SE_Exception() {}
   SE_Exception( unsigned int n ) : nSE( n ) {}
   ~SE_Exception() {}
   unsigned int getSeNumber() { return nSE; }
};

int main() {
   try {
      _set_se_translator( trans_func );
      SEFunc();
   }
   catch( SE_Exception e ) {
      printf_s( "Caught a __try exception with SE_Exception.\n" );
   }
}

void SEFunc() {
   __try {
      int x, y=0;
      x = 5 / y;
   }
   __finally {
      printf_s( "In finally\n" );
   }
}

void trans_func( unsigned int u, EXCEPTION_POINTERS* pExp ) {
   printf_s( "In trans_func.\n" );
   throw SE_Exception();
}
```