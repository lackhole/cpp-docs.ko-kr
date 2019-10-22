---
title: ctype_byname 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype_byname
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
ms.openlocfilehash: dcaaff45fb33155710f788af4ceb657eff97464e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689740"
---
# <a name="ctype_byname-class"></a>ctype_byname 클래스

파생 된 클래스 템플릿은 지정 된 로캘의 ctype 패싯으로 사용할 수 있는 개체에 대해 설명 하 고, 대/소문자와 네이티브 및 로캘 지정 문자 집합 간 문자 변환 및 문자 분류를 사용 하도록 설정 합니다.

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

## <a name="remarks"></a>주의

해당 동작은 명명된 로캘 `_Locname`에 따라 결정됩니다. 각 생성자는 [ctype](../standard-library/ctype-class.md)\<CharType>(`_Refs`)의 기본 개체 또는 기본 클래스 `ctype<char>`와 동등한 개체를 초기화합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
