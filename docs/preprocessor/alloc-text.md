---
title: alloc_text
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
ms.openlocfilehash: 399e8956a511f289b480e66db7f03cac0a6c7c20
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031367"
---
# <a name="alloctext"></a>alloc_text
지정한 함수 정의가 상주하는 코드 섹션의 이름을 지정합니다. pragma는 명명된 함수의 함수 선언자와 함수 정의 간에 발생해야 합니다.

## <a name="syntax"></a>구문

```
#pragma alloc_text( "
textsection
", function1, ... )
```

## <a name="remarks"></a>설명

합니다 **alloc_text** pragma를 처리 하지 않습니다 C++ 멤버 함수 또는 오버 로드 된 함수입니다. C 링크로 선언 된 함수에만 적용 됩니다-즉, 사용 하 여 선언 된 함수는 **extern "C"** 링크 사양입니다. C++ 링크가 있는 함수에 pragma를 사용하려고 하면 컴파일러 오류가 발생합니다.

함수 주소를 사용 하 여 이후 `__based` 지원 되지 않는 섹션 위치를 사용 해야 하는 지정 하는 **alloc_text** pragma입니다. 지정 된 이름을 *textsection* 큰따옴표로 묶어야 합니다.

합니다 **alloc_text** pragma는 지정된 된 함수 및 이러한 함수의 정의 하기 전에 모든 선언 뒤에 나타나야 합니다.

참조 하는 함수는 **alloc_text** pragma는 pragma와 동일한 모듈에서 정의 해야 합니다. 이와 같이 수행되지 않고 정의되지 않은 함수가 나중에 다른 텍스트 섹션으로 컴파일되면 오류가 잡힐 수도 있고 안 될 수도 있습니다. 프로그램은 보통 올바르게 실행되더라도 함수는 원하는 섹션에서 할당되지 않습니다.

다른 제한 **alloc_text** 는 다음과 같습니다.

- 함수 내에서 사용할 수 없습니다.

- 함수가 선언된 후, 그리고 함수가 정의되기 전에 사용되어야 합니다.

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)