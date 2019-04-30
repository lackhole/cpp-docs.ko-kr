---
title: ctype_byname 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype_byname
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
ms.openlocfilehash: d998747045ece765269ddb013b525b8c06fcdf8b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394171"
---
# <a name="ctypebyname-class"></a>ctype_byname 클래스

이 파생 템플릿 클래스는 지정된 로캘의 ctype 패싯으로 사용할 수 있는 개체를 설명합니다. 이 클래스를 사용하여 문자를 분류하고 대/소문자와 네이티브 및 로캘 지정 문자 집합 사이에서 문자를 변환할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```

## <a name="remarks"></a>설명

해당 동작은 명명된 로캘 `_Locname`에 따라 결정됩니다. 각 생성자는 [ctype](../standard-library/ctype-class.md)\<CharType>(`_Refs`)의 기본 개체 또는 기본 클래스 `ctype<char>`와 동등한 개체를 초기화합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
