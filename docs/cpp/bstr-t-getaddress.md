---
title: _bstr_t::GetAddress
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
ms.openlocfilehash: 4d51539d2afbb2fbcc860b6c4d821df119aca418
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393898"
---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress

**Microsoft 전용**

기존 문자열을 해제하고 새로 할당된 문자열의 주소를 반환합니다.

## <a name="syntax"></a>구문

```
BSTR* GetAddress( );
```

## <a name="return-value"></a>반환 값

`BSTR`로 래핑되는 `_bstr_t`에 대한 포인터입니다.

## <a name="remarks"></a>설명

**GetAddress** 모두에 영향을 줍니다 `_bstr_t` 공유 하는 개체는 `BSTR`합니다. 둘 이상의 `_bstr_t` 공유할 수는 `BSTR` 복사 생성자를 사용 하 여 및 **연산자 =** 합니다.

## <a name="example"></a>예제

참조 [_bstr_t:: assign](../cpp/bstr-t-assign.md) 사용 하는 예제 **GetAddress**합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_bstr_t 클래스](../cpp/bstr-t-class.md)