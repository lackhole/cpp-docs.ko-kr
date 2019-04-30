---
title: 컴파일러 경고(수준 4) C4820
ms.date: 11/04/2016
f1_keywords:
- C4820
helpviewer_keywords:
- C4820
ms.assetid: 17aa29f4-c287-49b8-bc43-8ed82ffed5ea
ms.openlocfilehash: adf8b365bc39acc1ce729e89260f8385ecb6c048
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280401"
---
# <a name="compiler-warning-level-4-c4820"></a>컴파일러 경고(수준 4) C4820

'bytes'바이트 채움 문자가 construct 'member_name' 뒤에 추가되었습니다.

형식 및 요소의 순서는 구조체의 끝에 패딩 추가 하도록 컴파일러에 발생 합니다. 참조 [맞춤](../../cpp/align-cpp.md) 패딩 구조체에 대 한 자세한 내용은 합니다.

기본적으로 이 경고는 해제되어 있습니다. 자세한 내용은 [기본적으로 해제되어 있는 컴파일러 경고](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 를 참조하세요.

다음 샘플에서는 C4820 오류가 생성 됩니다.

```
// C4820.cpp
// compile with: /W4 /c
#pragma warning(default : 4820)

// Delete the following 4 lines to resolve.
__declspec(align(2)) struct MyStruct {
   char a;
   int i;   // C4820
};

// OK
#pragma pack(1)
__declspec(align(1)) struct MyStruct2 {
   char a;
   int i;
};
```