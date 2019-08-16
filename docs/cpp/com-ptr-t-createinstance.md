---
title: _com_ptr_t::CreateInstance
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::CreateInstance
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
ms.openlocfilehash: 82b180b3f40683495ed2cfa284bdae8e1afaef9e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498659"
---
# <a name="_com_ptr_tcreateinstance"></a>_com_ptr_t::CreateInstance

**Microsoft 전용**

`CLSID` 또는`ProgID`를 지정 하 여 개체의 새 인스턴스를 만듭니다.

## <a name="syntax"></a>구문

```
HRESULT CreateInstance(
   const CLSID& rclsid,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCWSTR clsidString,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCSTR clsidStringA,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
```

#### <a name="parameters"></a>매개 변수

*rclsid*<br/>
개체 `CLSID` 의입니다.

*clsidString*<br/>
(" **{** "로 시작) 또는을 `ProgID`포함 하는 유니코드 문자열입니다. `CLSID`

*clsidStringA*<br/>
(" **{** "로 시작) 또는을 `ProgID`포함 하는 ANSI 코드 페이지를 사용 하는 멀티 바이트 문자열입니다. `CLSID`

*dwClsContext*<br/>
실행 코드를 실행하는 컨텍스트입니다.

*pOuter*<br/>
[집계](../atl/aggregation.md)에 대해 알 수 없는 외부입니다.

## <a name="remarks"></a>설명

이러한 멤버 함수는 새로운 COM 개체를 만들고 이 스마트 포인터의 인터페이스 형식을 쿼리하기 위해 `CoCreateInstance`를 호출합니다. 그러면 결과 포인터는 이 `_com_ptr_t` 개체 안에 캡슐화됩니다. `Release`이전에 캡슐화 된 포인터에 대 한 참조 횟수를 감소 하기 위해가 호출 됩니다. 이 루틴은 성공 또는 실패를 나타내는 HRESULT를 반환 합니다.

- **CreateInstance (** *rclsid* **,** *dwclscontext* **)** 을 지정 하 여 `CLSID`개체의 새 실행 인스턴스를 만듭니다.

- **CreateInstance (** *clsidstring* **,** *dwclscontext* **)** (" **{** "로 시작) 또는을 `ProgID`포함 하는 유니코드 문자열이 지정 된 개체의 실행 중인 새 인스턴스를 만듭니다. `CLSID`

- **CreateInstance (** *clsidstringa* **,** *dwclscontext* **)** (" **{** "로 시작) 또는을 `ProgID`포함 하는 멀티 바이트 문자열을 지정 하 여 개체의 새 실행 인스턴스를 만듭니다. `CLSID` 는 OEM 코드 페이지가 아니라 ANSI 코드 페이지에 문자열이 있는 것으로 가정 하는 [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)를 호출 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)