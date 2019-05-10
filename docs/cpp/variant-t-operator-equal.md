---
title: _variant_t::operator =
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator=
helpviewer_keywords:
- operator= [C++], variant
- operator = [C++], variant
- = operator [C++], with specific Visual C++ objects
ms.assetid: 77622723-6e49-4dec-9e0f-fa74028f1a3c
ms.openlocfilehash: 6a8f31e8db6f5ca5a680dd47b5d5391c84ce5025
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403321"
---
# <a name="varianttoperator-"></a>_variant_t::operator =

**Microsoft 전용**

## <a name="syntax"></a>구문

```
_variant_t& operator=(
   const VARIANT& varSrc
);

_variant_t& operator=(
   const VARIANT* pVarSrc
);

_variant_t& operator=(
   const _variant_t& var_t_Src
);

_variant_t& operator=(
   short sSrc
);

_variant_t& operator=(
   long lSrc
);

_variant_t& operator=(
   float fltSrc
);

_variant_t& operator=(
   double dblSrc
);

_variant_t& operator=(
   const CY& cySrc
);

_variant_t& operator=(
   const _bstr_t& bstrSrc
);

_variant_t& operator=(
   const wchar_t* wstrSrc
);

_variant_t& operator=(
   const char* strSrc
);

_variant_t& operator=(
   IDispatch* pDispSrc
);

_variant_t& operator=(
   bool bSrc
);

_variant_t& operator=(
   IUnknown* pSrc
);

_variant_t& operator=(
   const DECIMAL& decSrc
);

_variant_t& operator=(
   BYTE bSrc
);

_variant_t& operator=(
   char cSrc
);

_variant_t& operator=(
   unsigned short usSrc
);

_variant_t& operator=(
   unsigned long ulSrc
);

_variant_t& operator=(
   int iSrc
);

_variant_t& operator=(
   unsigned int uiSrc
);

_variant_t& operator=(
   __int64 i8Src
);

_variant_t& operator=(
   unsigned __int64 ui8Src
);
```

## <a name="remarks"></a>설명

다음 연산자는 `_variant_t` 개체에 새 값을 할당합니다.

- **operator = (***varSrc***)** 기존 할당 `VARIANT` 에 `_variant_t` 개체입니다.

- **operator = (***pVarSrc***)** 기존 할당 `VARIANT` 에 `_variant_t` 개체입니다.

- **operator = (***var_t_Src***)** 기존 할당 `_variant_t` 개체를 `_variant_t` 개체입니다.    

- **연산자 = (***sSrc***)** 할당 된 **짧은** 정수 값을 `_variant_t` 개체입니다.

- **연산자 = (**`lSrc`**)** 할당 한 **긴** 정수 값을 `_variant_t` 개체입니다.

- **연산자 = (***fltSrc***)** 할당 된 **float** 숫자 값을 `_variant_t` 개체입니다.

- **operator=(**  *dblSrc*  **)** Assigns a **double** numerical value to a `_variant_t` object.

- **operator = (***cySrc***)** 할당을 `CY` 개체를 `_variant_t` 개체.

- **operator=(**  *bstrSrc*  **)** Assigns a `BSTR` object to a `_variant_t` object.

- **operator = (***wstrSrc***)** 유니코드 문자열을 할당을 `_variant_t` 개체입니다.

- **operator = (**`strSrc`**)** 멀티 바이트 문자열을 할당을 `_variant_t` 개체입니다.

- **연산자 = (** `bSrc` **)** 할당 한 **bool** 값을 `_variant_t` 개체입니다.

- **operator = (***pDispSrc***)** 할당을 `VT_DISPATCH` 개체를 `_variant_t` 개체.

- **operator = (***pIUnknownSrc***)** 할당을 `VT_UNKNOWN` 개체를 `_variant_t` 개체.

- **operator=(**  *decSrc*  **)** Assigns a `DECIMAL` value to a `_variant_t` object.

- **연산자 = (** `bSrc` **)** 할당 한 `BYTE` 값을 `_variant_t` 개체입니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_variant_t 클래스](../cpp/variant-t-class.md)