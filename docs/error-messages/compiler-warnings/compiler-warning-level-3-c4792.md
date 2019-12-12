---
title: 컴파일러 경고(수준 3) C4792
ms.date: 11/04/2016
f1_keywords:
- C4792
helpviewer_keywords:
- C4792
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
ms.openlocfilehash: f0efed41fad2648d7e681fa4e5575e7f36fb6aeb
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991681"
---
# <a name="compiler-warning-level-3-c4792"></a>컴파일러 경고(수준 3) C4792

'function' 함수가 sysimport를 사용하여 선언되고 네이티브 코드에서 참조되었습니다. 링크에 필요한 라이브러리를 가져오세요.

DllImport를 사용하여 프로그램으로 가져온 네이티브 함수가 관리되지 않는 함수에서 호출되었습니다. 따라서 DLL에 대한 가져오기 라이브러리에 연결해야 합니다.

이 경고는 컴파일 방식을 변경하거나 코드에서는 확인할 수 없습니다. [warning](../../preprocessor/warning.md) pragma를 사용하여 이 경고를 사용하지 않도록 설정합니다.

다음 샘플에서는 C4792를 생성합니다.

```cpp
// C4792.cpp
// compile with: /clr /W3
// C4792 expected
using namespace System::Runtime::InteropServices;
[DllImport("msvcrt")]
extern "C" int __cdecl puts(const char *);
int main() {}

// Uncomment the following line to resolve.
// #pragma warning(disable : 4792)
#pragma unmanaged
void func(void){
   puts("test");
}
```
