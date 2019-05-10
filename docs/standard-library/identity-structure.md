---
title: identity 구조체
ms.date: 11/04/2016
f1_keywords:
- utility/std::identity
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
ms.openlocfilehash: 722eb9c0579d0c07765434127d0a7c43718fbc37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405003"
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

|매개 변수|설명|
|---------------|-----------------|
|*left*|식별할 값입니다.|

## <a name="remarks"></a>설명

클래스에는 템플릿 매개 변수 Type과 동일한 public 형식 정의 `type`이 포함되어 있습니다. 템플릿 함수 [forward](../standard-library/utility-functions.md#forward)와 함께 사용되어 함수 매개 변수가 원하는 형식을 갖도록 합니다.

이전 코드와 호환성을 위해 클래스 정의 identity 함수 `operator()` 인수로 반환 *왼쪽*합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<utility>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[\<utility>](../standard-library/utility.md)<br/>
