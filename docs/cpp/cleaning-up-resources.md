---
title: 리소스 정리
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], cleaning up resources
- exception handling [C++], cleaning up resources
- C++ exception handling, termination handlers
- resources [C++], cleaning up
- exception handling [C++], cleanup code
- try-catch keyword [C++], termination handlers
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
ms.openlocfilehash: 225c3ccaf3342f11ad4eb6d6575ad3ac542acfd2
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246643"
---
# <a name="cleaning-up-resources"></a>리소스 정리

종료 처리기를 실행하는 동안 종료 처리기가 호출되기 전에 어떤 리소스가 실제로 할당되는지 알 수 없을 수 있습니다. It is possible that the **__try** statement block was interrupted before all resources were allocated, so that not all resources were opened.

따라서 만일에 대비해 종료 처리 정리를 진행하기 전에 어떤 리소스가 실제로 열렸는지 확인해야 합니다. 권장 절차는 다음과 같습니다.

1. 핸들을 NULL로 초기화합니다.

1. In the **__try** statement block, allocate resources. 리소스가 할당되면 핸들은 양수 값으로 설정됩니다.

1. In the **__finally** statement block, release each resource whose corresponding handle or flag variable is nonzero or not NULL.

## <a name="example"></a>예제

For example, the following code uses a termination handler to close three files and a memory block that were allocated in the **__try** statement block. 리소스를 정리하기 전에 코드는 먼저 리소스가 할당되었는지 확인합니다.

```cpp
// exceptions_Cleaning_up_Resources.cpp
#include <stdlib.h>
#include <malloc.h>
#include <stdio.h>
#include <windows.h>

void fileOps() {
   FILE  *fp1 = NULL,
         *fp2 = NULL,
         *fp3 = NULL;
   LPVOID lpvoid = NULL;
   errno_t err;

   __try {
      lpvoid = malloc( BUFSIZ );

      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );
      err = fopen_s(&fp3, "CARS.DAT", "w+" );
   }
   __finally {
      if ( fp1 )
         fclose( fp1 );
      if ( fp2 )
         fclose( fp2 );
      if ( fp3 )
         fclose( fp3 );
      if ( lpvoid )
         free( lpvoid );
   }
}

int main() {
   fileOps();
}
```

## <a name="see-also"></a>참조

[Writing a termination handler](../cpp/writing-a-termination-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)