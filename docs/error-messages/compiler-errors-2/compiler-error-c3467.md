---
title: 컴파일러 오류 C3467
ms.date: 11/04/2016
f1_keywords:
- C3467
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
ms.openlocfilehash: 70375950543b9525fca10fff3084c923095fa35e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776095"
---
# <a name="compiler-error-c3467"></a>컴파일러 오류 C3467

'type': 이 형식은 이미 전달되었습니다.

컴파일러가 동일한 형식에 대한 2개 이상의 전달 형식 선언을 찾았습니다. 형식마다 선언은 하나씩만 허용됩니다.

자세한 내용은 [형식 전달 (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 구성 요소를 만듭니다.

```
// C3467.cpp
// compile with: /LD /clr
public ref class R {};
```

## <a name="example"></a>예제

다음 샘플에서는 C3467을 생성합니다.

```
// C3467_b.cpp
// compile with: /clr /c
#using "C3467.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467
```