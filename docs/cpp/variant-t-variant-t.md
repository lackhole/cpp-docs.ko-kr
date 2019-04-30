---
title: _variant_t::_variant_t
ms.date: 11/04/2016
f1_keywords:
- _variant_t::_variant_t
helpviewer_keywords:
- _variant_t class [C++], constructor
- _variant_t method [C++]
ms.assetid: a50e5b33-d4c6-4a26-8e7e-a0a25fd9895b
ms.openlocfilehash: b3575226199c15c4a9796fb439f65efb5a539225
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403284"
---
# <a name="varianttvariantt"></a>_variant_t::_variant_t

**Microsoft 전용**

`_variant_t` 개체를 생성합니다.

## <a name="syntax"></a>구문

```
_variant_t( ) throw( );

_variant_t(
   const VARIANT& varSrc
);

_variant_t(
   const VARIANT* pVarSrc
);

_variant_t(
   const _variant_t& var_t_Src
);

_variant_t(
   VARIANT& varSrc,
   bool fCopy
);

_variant_t(
   short sSrc,
   VARTYPE vtSrc = VT_I2
);

_variant_t(
   long lSrc,
   VARTYPE vtSrc = VT_I4
);

_variant_t(
   float fltSrc
) throw( );

_variant_t(
   double dblSrc,
   VARTYPE vtSrc = VT_R8
);

_variant_t(
   const CY& cySrc
) throw( );

_variant_t(
   const _bstr_t& bstrSrc
);

_variant_t(
   const wchar_t *wstrSrc
);

_variant_t(
   const char* strSrc
);

_variant_t(
   IDispatch* pDispSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   bool bSrc
) throw( );

_variant_t(
   IUnknown* pIUknownSrc,
   bool fAddRef = true
) throw( );

_variant_t(
   const DECIMAL& decSrc
) throw( );

_variant_t(
   BYTE bSrc
) throw( );

variant_t(
   char cSrc
) throw();

_variant_t(
   unsigned short usSrc
) throw();

_variant_t(
   unsigned long ulSrc
) throw();

_variant_t(
   int iSrc
) throw();

_variant_t(
   unsigned int uiSrc
) throw();

_variant_t(
   __int64 i8Src
) throw();

_variant_t(
   unsigned __int64 ui8Src
) throw();
```

#### <a name="parameters"></a>매개 변수

*varSrc*<br/>
새 `VARIANT` 개체로 복사할 `_variant_t` 개체입니다.

*pVarSrc*<br/>
에 대 한 포인터를 `VARIANT` 복사할 새 개체 `_variant_t` 개체입니다.

*var_t_Src*<br/>
새 `_variant_t` 개체로 복사할 `_variant_t` 개체입니다.

*fCopy*<br/>
하는 경우 **false**에 제공 된 `VARIANT` 새 개체가 추가 되 `_variant_t` 개체에서 새 복사본을 만들지 않고 `VariantCopy`합니다.

*ISrc, sSrc*<br/>
새 `_variant_t` 개체로 복사할 정수 값입니다.

*vtSrc*<br/>
합니다 `VARTYPE` 새 `_variant_t` 개체입니다.

*fltSrc, dblSrc*<br/>
새 `_variant_t` 개체에 복사될 숫자 값입니다.

*cySrc*<br/>
새 `CY` 개체로 복사할 `_variant_t` 개체입니다.

*bstrSrc*<br/>
새 `_bstr_t` 개체로 복사할 `_variant_t` 개체입니다.

*strSrc, wstrSrc*<br/>
새 `_variant_t` 개체로 복사할 문자열입니다.

*bSrc*<br/>
A **bool** 새에 복사할 값 `_variant_t` 개체입니다.

*pIUknownSrc*<br/>
COM 인터페이스 포인터를 새 개체로 캡슐화 될 VT_UNKNOWN 개체를 `_variant_t` 개체입니다.

*pDispSrc*<br/>
COM 인터페이스 포인터를 새 개체로 캡슐화 될 VT_DISPATCH 개체를 `_variant_t` 개체입니다.

*decSrc*<br/>
새 `DECIMAL` 개체로 복사할 `_variant_t` 값입니다.

*bSrc*<br/>
새 `BYTE` 개체로 복사할 `_variant_t` 값입니다.

*cSrc*<br/>
A **char** 새에 복사할 값 `_variant_t` 개체입니다.

*usSrc*<br/>
A **unsigned short** 새에 복사할 값 `_variant_t` 개체입니다.

*ulSrc*<br/>
A **부호 없는 long** 새에 복사할 값 `_variant_t` 개체입니다.

*iSrc*<br/>
**int** 새에 복사할 값 `_variant_t` 개체입니다.

*uiSrc*<br/>
**부호 없는 int** 새에 복사할 값 `_variant_t` 개체입니다.

*i8Src*<br/>
**__int64** 새에 복사할 값 `_variant_t` 개체입니다.

*ui8Src*<br/>
**unsigned __int64** 새에 복사할 값 `_variant_t` 개체입니다.

## <a name="remarks"></a>설명

- **_variant_t ()** 빈 생성 `_variant_t` 개체를 `VT_EMPTY`입니다.

- **_variant_t (VARIANT &***varSrc***)** 생성을 `_variant_t` 의 복사본에서 개체를 `VARIANT` 개체입니다.     변형 형식이 유지됩니다.

- **_variant_t (VARIANT**<strong>\*</strong>*pVarSrc***)** 생성을 `_variant_t` 개체의 복사본에서는 `VARIANT` 개체입니다.     변형 형식이 유지됩니다.

- **_variant_t (_variant_t &***var_t_Src***)** 생성을 `_variant_t` 개체에서 다른 `_variant_t` 개체입니다.     변형 형식이 유지됩니다.

- **_variant_t (VARIANT &***varSrc* **, bool**`fCopy`**)** 생성 된 `_variant_t` 기존 개체 `VARIANT` 개체입니다.       경우 *fCopy* 은 **false**의 **VARIANT** 개체 복사본을 만들지 않고 새 개체에 연결 됩니다.

- **_variant_t (short***sSrc* **, VARTYPE**`vtSrc`**= VT_I2)** 생성을 `_variant_t` 를 에서VT_I2또는VT_BOOL형식의개체**짧은** 정수 값입니다.       다른 `VARTYPE` E_INVALIDARG 오류가 발생 합니다.

- **_variant_t (long** `lSrc` **, VARTYPE**`vtSrc`**= VT_I4)** 생성을 `_variant_t` VT_I4, VT_BOOL, 또는에서 VT_ERROR 형식의 개체는 **long**  정수 값입니다.       다른 `VARTYPE` E_INVALIDARG 오류가 발생 합니다.

- **_variant_t (float**`fltSrc`**)** 생성을 `_variant_t` 에서 VT_R4 형식의 개체를 **float** 숫자 값입니다.    

- **_variant_t (double** `dblSrc` **, VARTYPE**`vtSrc`**= VT_R8)** 생성을 `_variant_t` VT_R8 또는에서 VT_DATE 형식의 개체는 **더블** 숫자 값입니다.       다른 `VARTYPE` E_INVALIDARG 오류가 발생 합니다.

- **_variant_t (CY &**`cySrc`**)** 생성을 `_variant_t` 개체의 입력에서 VT_CY를 `CY` 개체입니다.    

- **_variant_t (_bstr_t &**`bstrSrc`**)** 생성을 `_variant_t` 개체의 입력에서 VT_BSTR를 `_bstr_t` 개체입니다.     새 `BSTR`이 할당됩니다.

- **_variant_t (wchar_t** <strong>\*</strong> *wstrSrc***)** 생성을 `_variant_t` 유니코드 문자열에서 VT_BSTR 형식의 개체입니다.   새 `BSTR`이 할당됩니다.

- **_variant_t (char**<strong>\*</strong>`strSrc`**)** 생성을 `_variant_t` 문자열에서 VT_BSTR 형식의 개체입니다.     새 `BSTR`이 할당됩니다.

- **_variant_t (bool**`bSrc`**)** 생성을 `_variant_t` 개체의 입력에서 VT_BOOL를 **bool** 값입니다.    

- **_variant_t (IUnknown** <strong>\*</strong> `pIUknownSrc` **, bool**`fAddRef`**= true)** 생성을 `_variant_t` 형식의 개체 COM 인터페이스 포인터에서 VT_UNKNOWN 합니다.       경우 `fAddRef` 는 **true**, 다음 `AddRef` 에 대 한 호출에 맞게 제공 된 인터페이스 포인터 라고 `Release` 발생 하는 경우는 `_variant_t` 개체는 소멸 됩니다. 호출 하는 것 `Release` 제공 된 인터페이스 포인터에 대 한 합니다. 하는 경우 `fAddRef` 됩니다 **false**,이 생성자는 제공된 된 인터페이스 포인터의 소유권; 호출 하지 마십시오 `Release` 제공 된 인터페이스 포인터에 대 한 합니다.

- **_variant_t (IDispatch** <strong>\*</strong> `pDispSrc` **, bool**`fAddRef`**= true)** 생성을 `_variant_t` 개체 COM 인터페이스 포인터에서 VT_DISPATCH를 입력 합니다.       경우 `fAddRef` 는 **true**, 다음 `AddRef` 에 대 한 호출에 맞게 제공 된 인터페이스 포인터 라고 `Release` 발생 하는 경우는 `_variant_t` 개체는 소멸 됩니다. 호출 하는 것 `Release` 제공 된 인터페이스 포인터에 대 한 합니다. 하는 경우 `fAddRef` 됩니다 **false**,이 생성자는 제공된 된 인터페이스 포인터의 소유권; 호출 하지 마십시오 `Release` 제공 된 인터페이스 포인터에 대 한 합니다.

- **_variant_t (10 진수 &**`decSrc`**)** 생성을 `_variant_t` 개체의 입력에서 VT_DECIMAL는 `DECIMAL` 값입니다.    

- **_variant_t (바이트**`bSrc`**)** 생성을 `_variant_t` 형식의 개체 `VT_UI1` 에서 `BYTE` 값입니다.    

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_variant_t 클래스](../cpp/variant-t-class.md)