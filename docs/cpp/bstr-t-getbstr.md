---
title: _bstr_t::GetBSTR
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
ms.openlocfilehash: cea3404e0732cb0e16b3fa9199ce95e3dfcc23f5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386150"
---
# <a name="bstrtgetbstr"></a>_bstr_t::GetBSTR

**Microsoft 전용**

`BSTR`에 의해 래핑되는 `_bstr_t`의 시작 부분을 가리킵니다.

## <a name="syntax"></a>구문

```
BSTR& GetBSTR( );
```

## <a name="return-value"></a>반환 값

`BSTR`에 의해 래핑되는 `_bstr_t`의 시작 부분입니다.

## <a name="remarks"></a>설명

**GetBSTR** 모두에 영향을 줍니다 `_bstr_t` 공유 하는 개체는 `BSTR`합니다. 둘 이상의 `_bstr_t` 공유할 수는 `BSTR` 복사 생성자를 사용 하 여 및 **연산자 =** 합니다.

## <a name="example"></a>예제

참조 [_bstr_t:: assign](../cpp/bstr-t-assign.md) 사용 하는 예제 **GetBSTR**합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_bstr_t 클래스](../cpp/bstr-t-class.md)