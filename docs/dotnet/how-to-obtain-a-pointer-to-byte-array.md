---
title: '방법: 바이트 배열에 대 한 포인터를 가져오려면'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- pointers, to Byte array
- Byte arrays
ms.assetid: aea18073-3341-47f4-9f0e-04e03327037e
ms.openlocfilehash: 28feb039cf7b91bbf12d94b1abebe0e5b9501d7f
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738872"
---
# <a name="how-to-obtain-a-pointer-to-byte-array"></a>방법: 바이트 배열에 대 한 포인터를 가져오려면

배열 블록에 대 한 포인터를 가져올 수 있습니다는 <xref:System.Byte> 첫 번째 요소의 주소를 포인터에 할당 하는 배열입니다.

## <a name="example"></a>예제

```
// pointer_to_Byte_array.cpp
// compile with: /clr
using namespace System;
int main() {
   Byte bArr[] = {1, 2, 3};
   Byte* pbArr = &bArr[0];

   array<Byte> ^ bArr2 = gcnew array<Byte>{1,2,3};
   interior_ptr<Byte> pbArr2 = &bArr2[0];
}
```

## <a name="see-also"></a>참고자료

[C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
