---
title: '방법: system:: string의 문자 액세스'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
ms.openlocfilehash: 6b9e30a18ab1d2b8463ccccae0b265bc20904020
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775974"
---
# <a name="how-to-access-characters-in-a-systemstring"></a>방법: system:: string의 문자 액세스

문자에 액세스할 수 있습니다는 <xref:System.String> 관리 되지 않는 고성능 호출에 대 한 개체 사용 하는 함수의 `wchar_t*` 문자열입니다. 메서드 생성의 첫 번째 문자는 내부 포인터는 <xref:System.String> 개체입니다. 이 포인터 수 직접 조작 또는 고정 되며 일반적인 필요한 함수에 전달 된 `wchar_t` 문자열입니다.

## <a name="example"></a>예제

`PtrToStringChars` 반환을 <xref:System.Char>, 내부 포인터는 (라고도 `byref`). 따라서 가비지 수집의 대상이 됩니다. 네이티브 함수에 전달 하려는 경우가 아니면이 포인터를 고정할 필요가 없습니다.

다음과 같은 코드를 생각해 볼 수 있습니다.  고정 하기 때문에 필요 하지 않습니다 `ppchar` 내부 포인터 이며 업데이트도 가비지 수집기가 가리키는 문자열을 이동 하면 `ppchar`합니다. 없이 [pin_ptr (C + + /cli CLI)](../extensions/pin-ptr-cpp-cli.md)코드가 작동 하 고 잠재적인 성능 저하 인해 발생할 수 없습니다를 고정 하 여 합니다.

전달 하는 경우 `ppchar` 네이티브 함수에 다음을 고정 포인터 여야; 가비지 수집기가 관리 되지 않는 스택 프레임에 포인터를 업데이트할 수 없습니다.

```
// PtrToStringChars.cpp
// compile with: /clr
#include<vcclr.h>
using namespace System;

int main() {
   String ^ mystring = "abcdefg";

   interior_ptr<const Char> ppchar = PtrToStringChars( mystring );

   for ( ; *ppchar != L'\0'; ++ppchar )
      Console::Write(*ppchar);
}
```

```Output
abcdefg
```

## <a name="example"></a>예제

이 예제에서는 고정이 필요한 위치를 표시 합니다.

```
// PtrToStringChars_2.cpp
// compile with: /clr
#include <string.h>
#include <vcclr.h>
// using namespace System;

size_t getlen(System::String ^ s) {
   // Since this is an outside string, we want to be secure.
   // To be secure, we need a maximum size.
   size_t maxsize = 256;
   // make sure it doesn't move during the unmanaged call
   pin_ptr<const wchar_t> pinchars = PtrToStringChars(s);
   return wcsnlen(pinchars, maxsize);
};

int main() {
   System::Console::WriteLine(getlen("testing"));
}
```

```Output
7
```

## <a name="example"></a>예제

내부 포인터는 네이티브 c + + 포인터의 모든 속성에 있습니다. 예를 들어, 연결 된 데이터 구조를 탐색 하 고 삽입 및 하나의 포인터를 사용 하 여 삭제를 수행 하려면 사용할 수 있습니다.

```
// PtrToStringChars_3.cpp
// compile with: /clr /LD
using namespace System;
ref struct ListNode {
   Int32 elem;
   ListNode ^ Next;
};

void deleteNode( ListNode ^ list, Int32 e ) {
   interior_ptr<ListNode ^> ptrToNext = &list;
   while (*ptrToNext != nullptr) {
      if ( (*ptrToNext) -> elem == e )
         *ptrToNext = (*ptrToNext) -> Next;   // delete node
      else
         ptrToNext = &(*ptrToNext) -> Next;   // move to next node
   }
}
```

## <a name="see-also"></a>참고자료

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
