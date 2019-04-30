---
title: ctype_base 클래스
ms.date: 11/04/2016
f1_keywords:
- locale/std::ctype_base
helpviewer_keywords:
- ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
ms.openlocfilehash: 83ef35f9fac438cfa217decf222abd365ff84269
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394184"
---
# <a name="ctypebase-class"></a>ctype_base 클래스

이 클래스는 템플릿 클래스 [ctype](../standard-library/ctype-class.md)의 패싯에 대한 기본 클래스로 사용됩니다. 개별적으로 또는 전체 범위 내에서 특성을 분류 또는 테스트하는 데 사용하는 열거형을 정의하는 데 사용하는 ctype 클래스의 기본 클래스입니다.

## <a name="syntax"></a>구문

```cpp
struct ctype_base : public locale::facet
{
    enum
    {
        alnum,
        alpha,
        cntrl,
        digit,
        graph,
        lower,
        print,
        punct,
        space,
        upper,
        xdigit
    };
    typedef short mask;

    ctype_base( size_t _Refs = 0 );
    ~ctype_base();
};
```

## <a name="remarks"></a>설명

열거형 마스크를 정의합니다. 각 열거형 상수는 \<ctype.h> 헤더에 선언된 비슷한 이름의 함수에 정의된 것처럼 문자를 분류하는 다양한 방법의 특징을 지정합니다. 상수는 다음과 같습니다.

- **space**([isspace](../standard-library/locale-functions.md#isspace) 함수)

- **print**([isprint](../standard-library/locale-functions.md#isprint) 함수)

- **cntrl**([iscntrl](../standard-library/locale-functions.md#iscntrl) 함수)

- **upper**(함수 [isupper](../standard-library/locale-functions.md#isupper))

- **lower**([islower](../standard-library/locale-functions.md#islower) 함수)

- **digit**([isdigit](../standard-library/locale-functions.md#isdigit) 함수)

- **punct**([ispunct](../standard-library/locale-functions.md#ispunct) 함수)

- **xdigit**([isxdigit](../standard-library/locale-functions.md#isxdigit) 함수)

- **alpha**([isalpha](../standard-library/locale-functions.md#isalpha) 함수)

- **alnum**([isalnum](../standard-library/locale-functions.md#isalnum) 함수)

- **graph**([isgraph](../standard-library/locale-functions.md#isgraph) 함수)

이러한 상수를 OR 연산하여 분류의 조합을 특징지을 수 있습니다. 특히,이 항상 true입니다 **alnum** = = ( **알파** &#124; **자리** \) 하 고 **그래프** \= \= \( **alnum** &#124; **punct**).

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
