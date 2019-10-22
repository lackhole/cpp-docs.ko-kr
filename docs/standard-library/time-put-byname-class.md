---
title: time_put_byname 클래스
ms.date: 11/04/2016
f1_keywords:
- xloctime/std::time_put_byname
helpviewer_keywords:
- time_put_byname class
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
ms.openlocfilehash: 4471c0df352a4d40d863ac36f0245cf8194f588c
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685461"
---
# <a name="time_put_byname-class"></a>time_put_byname 클래스

파생 된 클래스 템플릿은 \< CharType, OutputIterator > `time_put` 형식의 로캘 패싯으로 사용할 수 있는 개체를 설명 합니다.

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

*_Locname* \
로캘 이름

*참조 (_s)* \
초기 참조 횟수

## <a name="remarks"></a>주의

해당 동작은 [명명](../standard-library/locale-class.md#name) 된 로캘 *_locname*에 의해 결정 됩니다. 각 생성자는 [time_put](../standard-library/time-put-class.md#time_put) \<CharType, outputiterator > (`_Refs`)를 사용 하 여 해당 기준 개체를 초기화 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
