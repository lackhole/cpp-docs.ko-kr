---
title: identity 구조체
ms.date: 11/04/2016
f1_keywords:
- utility/std::identity
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
ms.openlocfilehash: 49b2c1eb3ca03f9bf9199bdbca49348866ff0a7e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246159"
---
# <a name="identity-structure"></a>identity 구조체

형식 정의를 템플릿 매개 변수로 제공하는 구조체입니다.

## <a name="syntax"></a>구문

```cpp
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
};
```

### <a name="parameters"></a>매개 변수

*왼쪽*\
식별할 값입니다.

## <a name="remarks"></a>설명

클래스에는 템플릿 매개 변수 Type과 동일한 public 형식 정의 `type`이 포함되어 있습니다. 템플릿 함수 [forward](../standard-library/utility-functions.md#forward)와 함께 사용되어 함수 매개 변수가 원하는 형식을 갖도록 합니다.

이전 코드와 호환성을 위해 클래스 정의 identity 함수 `operator()` 인수로 반환 *왼쪽*합니다.
