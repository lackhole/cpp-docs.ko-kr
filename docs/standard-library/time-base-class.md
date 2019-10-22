---
title: time_base 클래스
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: ddaf9905e859c062031940d35adfa2a3393dbb5a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685783"
---
# <a name="time_base-class"></a>time_base 클래스

이 클래스는 time_get 클래스의 패싯에 대 한 기본 클래스로 사용 되며, 열거 된 형식 `dateorder`와이 형식의 여러 상수만 정의 합니다.

## <a name="syntax"></a>구문

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {
        no_order,
        dmy,
        mdy,
        ymd,
        ydm
    };
    time_base(size_t _Refs = 0)
    ~time_base();
};
```

## <a name="remarks"></a>주의

각 상수는 날짜의 구성 요소 순서를 지정하는 다른 방식을 지정합니다. 상수는 다음과 같습니다.

- `no_order`는 특정 순서를 지정 하지 않습니다.

- `dmy`는 12 월 1979 일을 기준으로 주문 일, 월, 연도를 지정 합니다.

- `mdy`는 12 월 1979 2 일부 터와 같이 주문 월, 일, 연도를 지정 합니다.

- `ymd`은 1979/12/2에서와 같이 order 년, 월, 일을 지정 합니다.

- `ydm`는 1979 년 12 월 2 일과 같이 order year, day, month를 지정 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
