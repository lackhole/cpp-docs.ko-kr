---
title: 컴파일러 오류 C3807
ms.date: 11/04/2016
f1_keywords:
- C3807
helpviewer_keywords:
- C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
ms.openlocfilehash: b5599914666af95a29667acc1ad4ad35eef7608f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391935"
---
# <a name="compiler-error-c3807"></a>컴파일러 오류 C3807

'type': ComImport 특성이 있는 클래스는 'type2'에서 파생 될 수 없습니다, 인터페이스 구현만 허용 됩니다

파생 된 형식은 <xref:System.Runtime.InteropServices.ComImportAttribute> 만 인터페이스를 구현할 수 있습니다.

## <a name="example"></a>예제

다음 샘플 C3807를 생성합니다.

```
// C3807.cpp
// compile with: /clr /c
ref struct S {};
interface struct I {};

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 : S {};   // C3807
ref struct S2 : I {};
```