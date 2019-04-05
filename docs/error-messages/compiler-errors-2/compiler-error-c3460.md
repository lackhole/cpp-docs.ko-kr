---
title: 컴파일러 오류 C3460
ms.date: 11/04/2016
f1_keywords:
- C3460
helpviewer_keywords:
- C3460
ms.assetid: adbf8775-10ca-4654-acdf-58dd765351cd
ms.openlocfilehash: 9ffbc5102855574aba668a2c501cd08dbaebe5b8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58775181"
---
# <a name="compiler-error-c3460"></a>컴파일러 오류 C3460

'type': 사용자 정의 형식만 전달할 수 있습니다.

자세한 내용은 [형식 전달 (C + + /cli CLI)](../../extensions/type-forwarding-cpp-cli.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 구성 요소를 만듭니다.

```
// C3460.cpp
// compile with: /LD /clr
public ref class R {};
```

## <a name="example"></a>예제

다음 샘플에서는 C3460을 생성합니다.

```
// C3460_b.cpp
// compile with: /clr /c
#using "C3460.dll"
[assembly:TypeForwardedTo(int::typeid)];   // C3460
[assembly:TypeForwardedTo(R::typeid)];
```