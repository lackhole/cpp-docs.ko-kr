---
title: codecvt_base 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_base
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
ms.openlocfilehash: 6fca9b2130407b165a7a7bfb1fb2a9ec81774e20
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689882"
---
# <a name="codecvt_base-class"></a>codecvt_base 클래스

변환 결과를 나타내기 위해 패싯 멤버 함수에 대 한 반환 형식으로 사용 되는 `result` 이라고 하는 열거형 형식을 정의 하는 데 사용 되는 codecvt 클래스에 대 한 기본 클래스입니다.

## <a name="syntax"></a>구문

```cpp
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
    bool always_noconv() const;
    int max_length() const;
    int encoding() const;
    ~codecvt_base()

protected:
    virtual bool do_always_noconv() const;
    virtual int do_max_length() const;
    virtual int do_encoding() const;
};
```

## <a name="remarks"></a>주의

클래스는 클래스 템플릿 [codecvt](../standard-library/codecvt-class.md)의 모든 특수화에 공통적인 열거형을 설명 합니다. 열거형 결과는 다음과 같이 [do_in](../standard-library/codecvt-class.md#do_in) 또는 [do_out](../standard-library/codecvt-class.md#do_out)의 가능한 반환 값을 설명합니다.

- 내부 및 외부 문자 인코딩 간의 변환이 성공 하면 `ok` 합니다.

- 변환이 성공 하기에는 대상이 충분히 크지 않은 경우 `partial` 합니다.

- 소스 시퀀스의 형식이 잘못 된 경우 `error` 합니다.

- 함수가 변환을 수행하지 않은 경우 `noconv`

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
