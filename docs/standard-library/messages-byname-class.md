---
title: messages_byname 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_byname
helpviewer_keywords:
- messages_byname class
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
ms.openlocfilehash: 56d8931cb404d9c0f3f5113f8b2ca0f1158209f2
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689336"
---
# <a name="messages_byname-class"></a>messages_byname 클래스

파생 된 클래스 템플릿은 지정 된 로캘의 메시지 패싯으로 사용 하 여 지역화 된 메시지를 검색할 수 있도록 하는 개체를 설명 합니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType>
class messages_byname : public messages<CharType> {
public:
    explicit messages_byname(
    const char *_Locname,
    size_t _Refs = 0);

    explicit messages_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~messages_byname();

};
```

### <a name="parameters"></a>매개 변수

*_Locname* \
명명된 로캘입니다.

*참조 (_s)* \
초기 참조 횟수

## <a name="remarks"></a>주의

해당 동작은 명명 된 로캘 *_Locname*에 의해 결정 됩니다. 각 생성자는 [messages](../standard-library/messages-class.md#messages)\<CharType>( `_Refs`)를 통해 기본 개체를 초기화합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
