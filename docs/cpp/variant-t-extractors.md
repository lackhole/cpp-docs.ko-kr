---
title: _variant_t Extractors
ms.date: 11/04/2016
f1_keywords:
- _variant_t.operatordouble
- operatorlong
- _variant_t::operator_bstr_t
- operatordouble
- _variant_t.operatorCY
- operatorCY
- _variant_t::operatorCY
- _variant_t::operatordouble
- operatorfloat
- operatorBYTE
- _variant_t.operatorDECIMAL
- _variant_t::operatorlong
- operatorIDispatch
- _variant_t.operatorBYTE
- operatorDECIMAL
- _variant_t.operator_bstr_t
- _variant_t::operatorDECIMAL
- _variant_t.operatorIUnknown
- _variant_t.operatorlong
- _variant_t::operatorIDispatch
- _variant_t::operatorIUnknown
- operatorIUnknown
- _variant_t.operatorbool
- _variant_t::operatorBYTE
- _variant_t.operatorfloat
- operator_bstr_t
- _variant_t::operatorbool
- operatorshort
- _variant_t::operatorshort
- _variant_t::operatorfloat
- _variant_t.operatorIDispatch
- _variant_t.operatorshort
helpviewer_keywords:
- extractors, _variant_t class
- operator CY
- operator IDispatch
- operator SHORT
- operator double
- operator long
- operator _bstr_t
- operator DECIMAL
- operator float
- operator bool
- operator BYTE
- operator IUnknown
ms.assetid: 33c1782f-045a-4673-9619-1d750efc83a9
ms.openlocfilehash: ab97238cf13accf3db593b5c4a81550297a53d6d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403336"
---
# <a name="variantt-extractors"></a>_variant_t Extractors

**Microsoft 전용**

캡슐화 된 데이터를 추출 `VARIANT` 개체입니다.

## <a name="syntax"></a>구문

```
operator short( ) const;
operator long( ) const;
operator float( ) const;
operator double( ) const;
operator CY( ) const;
operator _bstr_t( ) const;
operator IDispatch*( ) const;
operator bool( ) const;
operator IUnknown*( ) const;
operator DECIMAL( ) const;
operator BYTE( ) const;
operator VARIANT() const throw();
operator char() const;
operator unsigned short() const;
operator unsigned long() const;
operator int() const;
operator unsigned int() const;
operator __int64() const;
operator unsigned __int64() const;
```

## <a name="remarks"></a>설명

캡슐화 된 원시 데이터를 추출 `VARIANT`합니다. 경우는 `VARIANT` 가 이미 올바른 형식이 아닌 `VariantChangeType` 변환을 시도 하는 데 사용 되 고 실패 시 오류가 생성 됩니다:

- **연산자 short ()** 추출 된 **짧은** 정수 값입니다.

- **연산자 long ()** 추출 된 **긴** 정수 값입니다.

- **연산자 float ()** 추출 된 **float** 숫자 값입니다.

- **연산자 double ()** 추출 된 **double** 정수 값입니다.

- **연산자 CY ()** 추출 된 `CY` 개체입니다.

- **연산자 bool ()** 추출 된 **bool** 값입니다.

- **연산자 DECIMAL ()** 추출 된 `DECIMAL` 값입니다.

- **연산자 BYTE ()** 추출 된 `BYTE` 값입니다.

- **연산자 _bstr_t ()** 에서 캡슐화 된 문자열을 추출 된 `_bstr_t` 개체입니다.

- **연산자 IDispatch\*()** 캡슐화 된에서 dispinterface 포인터를 추출 `VARIANT`합니다. `AddRef` 호출 하는 이므로 결과 포인터 라고 `Release` 메모리를 해제 해야 합니다.

- **연산자 IUnknown\*()** 캡슐화 된에서 COM 인터페이스 포인터를 추출 `VARIANT`합니다. `AddRef` 호출 하는 이므로 결과 포인터 라고 `Release` 메모리를 해제 해야 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_variant_t 클래스](../cpp/variant-t-class.md)