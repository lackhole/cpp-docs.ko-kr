---
title: codecvt_byname 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_byname
helpviewer_keywords:
- codecvt_byname class
ms.assetid: b63b6c04-f60c-47b9-8e30-a933f24a8ffb
ms.openlocfilehash: b48f01126eba7082230fc5e19150d42d1dfad2f3
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688300"
---
# <a name="codecvt_byname-class"></a>codecvt_byname 클래스

지정 된 로캘의 collate 패싯으로 사용 될 수 있는 개체를 설명 하는 파생 클래스 템플릿으로, 변환과 관련 된 문화권 영역과 관련 된 정보를 검색할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType, class Byte, class StateType>
class codecvt_byname: public codecvt<CharType, Byte, StateType> {
public:
    explicit codecvt_byname(
    const char* _Locname,
    size_t _Refs = 0);
```

```cpp
explicit codecvt_byname(
    const string& _Locname,
    size_t _Refs = 0);
```

```cpp
protected:
    virtual ~codecvt_byname();

};
```

### <a name="parameters"></a>매개 변수

*_Locname* \
명명된 로캘입니다.

*참조 (_s)* \
초기 참조 횟수

## <a name="remarks"></a>주의

명명된 로캘이 생성되는 경우 byname 패싯이 자동으로 생성됩니다.

해당 동작은 명명 된 로캘 *_Locname*에 의해 결정 됩니다. 각 생성자는 [codecvt](../standard-library/codecvt-class.md)\<CharType, Byte, StateType>( `_Refs`)를 통해 해당 기본 개체를 초기화합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
