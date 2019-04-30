---
title: codecvt_base 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::codecvt_base
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
ms.openlocfilehash: 6f957c39f9c78fd182b7ba2a14bdab7f27db56ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405302"
---
# <a name="codecvtbase-class"></a>codecvt_base 클래스

열거형을 정의 하는 데 사용 되는 codecvt 클래스의 기본 클래스 라고 `result`변환의 결과 나타내기 위해 패싯 멤버 함수에 대 한 반환 형식으로 사용 합니다.

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

## <a name="remarks"></a>설명

이 클래스는 템플릿 클래스 [codecvt](../standard-library/codecvt-class.md)의 모든 특수화에 공통적인 열거형을 설명합니다. 열거형 결과는 다음과 같이 [do_in](../standard-library/codecvt-class.md#do_in) 또는 [do_out](../standard-library/codecvt-class.md#do_out)의 가능한 반환 값을 설명합니다.

- `ok` 내부 및 외부 문자 인코딩 간 변환에 성공 합니다.

- `partial` 대상은 변환이 성공 하기에 충분 되지 않습니다.

- `error` 소스 시퀀스의 형식이 잘못 된 경우 다음을 구성 합니다.

- 함수가 변환을 수행하지 않은 경우 `noconv`

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
