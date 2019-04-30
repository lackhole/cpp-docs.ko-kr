---
title: 지정자
ms.date: 11/04/2016
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
ms.openlocfilehash: aef967b26321f289cb8c7bd0402d7fe8f12b77b6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330988"
---
# <a name="specifiers"></a>지정자

이 항목에서는 [선언](declarations-and-definitions-cpp.md)의 *decl-specifiers* (선언 지정자) 구성 요소에 대해 설명합니다.

다음 자리 표시자 및 언어 키워드는 선언 지정자입니다.

*storage-class-specifier*

*type-specifier*

*function-specifier*

[friend](friend-cpp.md)

[typedef](aliases-and-typedefs-cpp.md) `(` *extended-decl-modifier-seq* `)`

[__declspec](declspec.md) `(` *extended-decl-modifier-seq* `)`

## <a name="remarks"></a>설명

선언의 *decl-specifiers* 부분은 *decl-specifiers*의 가장 긴 시퀀스이며, 포인터 또는 참조 한정자를 포함하지 않는 형식 이름을 의미하기 위해 사용할 수 있습니다. 선언의 나머지 부분은 *declarator* 로서, 소개된 이름을 포함합니다.

다음 표에서는 4개의 선언을 나열한 후 각 선언의 *decl-specifers* 및 *declarator* 구성 요소를 따로 나열합니다.

|선언|*decl-specifiers*|`declarator`|
|-----------------|------------------------|------------------|
|`char *lpszAppName;`|**char**|`*lpszAppName`|
|`typedef char * LPSTR;`|**char**|`*LPSTR`|
|`const int func1();`|**const int**|`func1`|
|`volatile void *pvvObj;`|**volatile void**|`*pvvObj`|

**signed**, **unsigned**, **long** 및 **short**는 모두 **int**를 암시하므로 이러한 키워드 다음에 오는 **typedef** 이름은 *decl-specifiers*가 아닌 *declarator-list*의 멤버로 간주됩니다.

> [!NOTE]
>  이름은 다시 선언할 수 있기 때문에 현재 범위에서 최신 선언에 해석이 적용됩니다. 재선언은 특히 **typedef** 이름이 컴파일러에 의해 해석되는 방법에 영향을 줄 수 있습니다.

## <a name="see-also"></a>참고 항목

[선언 및 정의](declarations-and-definitions-cpp.md)
