---
title: time_put_byname 클래스
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put_byname
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
ms.openlocfilehash: ffe7aa276e9380b6544a78c1c1735ab57765507a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411970"
---
# <a name="timeputbyname-class"></a>time_put_byname 클래스

`time_put`\< CharType, OutputIterator > 형식의 로캘 패싯으로 사용할 수 있는 개체에 대해 설명하는 파생된 템플릿 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType, class OutIt = ostreambuf_iterator<CharType, char_traits<CharType>>>
class time_put_byname : public time_put<CharType, OutputIterator>
{
public:
    explicit time_put_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit time_put_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~time_put_byname();

};
```

### <a name="parameters"></a>매개 변수

*_Locname*<br/>
로캘 이름

*_Refs*<br/>
초기 참조 개수입니다.

## <a name="remarks"></a>설명

해당 동작은에 의해 결정 됩니다 합니다 [라는](../standard-library/locale-class.md#name) 로캘 *_Locname*합니다. 각 생성자를 통해 해당 기준 개체를 초기화 [time_put](../standard-library/time-put-class.md#time_put)\<CharType, OutputIterator > (`_Refs`).

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
