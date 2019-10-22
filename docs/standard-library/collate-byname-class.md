---
title: collate_byname 클래스
ms.date: 11/04/2016
f1_keywords:
- locale/std::collate_byname
helpviewer_keywords:
- collate_byname class
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
ms.openlocfilehash: 3e9a256ac7bdb5f6d077746fe2a08990ed41e931
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688264"
---
# <a name="collate_byname-class"></a>collate_byname 클래스

지정 된 로캘의 collate 패싯으로 사용할 수 있는 개체를 설명 하는 파생 된 클래스 템플릿으로, 문자열 정렬 규칙에 대 한 문화권 영역과 관련 된 정보를 검색할 수 있도록 합니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType>
class collate_byname : public collate<CharType> {
public:
    explicit collate_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit collate_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~collate_byname();

};
```

### <a name="parameters"></a>매개 변수

*_Locname* \
명명된 로캘입니다.

*참조 (_s)* \
초기 참조 횟수

## <a name="remarks"></a>주의

클래스 템플릿은 > \<CharType [collate](../standard-library/collate-class.md#collate) 형식의 [로캘 패싯](../standard-library/locale-class.md#facet_class) 으로 사용할 수 있는 개체를 설명 합니다. 해당 동작은 [명명](../standard-library/locale-class.md#name) 된 로캘 *_locname*에 의해 결정 됩니다. 각 생성자는 [collate](../standard-library/collate-class.md#collate)\<CharType>( `_Refs`)를 통해 해당 기본 개체를 초기화합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
