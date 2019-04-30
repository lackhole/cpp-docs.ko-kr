---
title: 컴파일러 오류 C2011
ms.date: 11/04/2016
f1_keywords:
- C2011
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
ms.openlocfilehash: 14969c9cdf4b00844d2001bf4817ea7ffc9bfba6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361557"
---
# <a name="compiler-error-c2011"></a>컴파일러 오류 C2011

'identifier': 'type' 형식 재정의

식별자가 `type`으로 이미 정의되었습니다. 식별자 재정의를 확인하세요.

헤더 파일 또는 형식 라이브러리를 동일한 파일로 두 번 이상 가져오는 경우 C2011 오류가 발생할 수도 있습니다. Include 가드를 사용 하 여 헤더 파일에 정의 된 형식의 여러 번 포함을 방지 하려면 또는 `#pragma` [되 면](../../preprocessor/once.md) 헤더 파일의 지시문입니다.

다시 정의 된 형식의 초기 선언을 찾아야 하는 경우 사용할 수는 [/P](../../build/reference/p-preprocess-to-a-file.md) 컴파일러 플래그 전처리 된 출력을 생성 하도록 컴파일러에 전달 합니다. 텍스트 검색 도구를 사용하여 출력 파일에서 다시 정의된 식별자의 인스턴스를 찾을 수 있습니다.

다음 샘플에서는 C2011 오류가 발생하는 경우 및 이를 해결하는 한 가지 방법을 보여 줍니다.

```
// C2011.cpp
// compile with: /c
struct S;
union S;   // C2011
union S2;   // OK
```