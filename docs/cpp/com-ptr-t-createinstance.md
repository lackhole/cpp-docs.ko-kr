---
title: _com_ptr_t::CreateInstance
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::CreateInstance
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
ms.openlocfilehash: c4f6cd54b90ab5fab69f91df67a8bf60b0b658f8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399371"
---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance

**Microsoft 전용**

지정 된 개체의 새 인스턴스를 만듭니다는 `CLSID` 또는 `ProgID`합니다.

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
`CLSID` 개체입니다.

*clsidString*<br/>
중 하나를 포함 하는 유니코드 문자열을 `CLSID` (시작 "**{**") 또는 `ProgID`합니다.

*clsidStringA*<br/>
멀티 바이트 문자열을 보유 하는 ANSI 코드 페이지를 사용 하는 `CLSID` (시작 "**{**") 또는 `ProgID`합니다.

*dwClsContext*<br/>
실행 코드를 실행하는 컨텍스트입니다.

*pOuter*<br/>
에 대 한 알 수 없는 외부 [집계](../atl/aggregation.md)합니다.

## <a name="remarks"></a>설명

이러한 멤버 함수는 새로운 COM 개체를 만들고 이 스마트 포인터의 인터페이스 형식을 쿼리하기 위해 `CoCreateInstance`를 호출합니다. 그러면 결과 포인터는 이 `_com_ptr_t` 개체 안에 캡슐화됩니다. `Release` 이전에 캡슐화 된 포인터에 대 한 참조 횟수를 감소 시키기 위해 호출 됩니다. 이 루틴은 성공 또는 실패를 나타내는 HRESULT를 반환 합니다.

- **CreateInstance (***rclsid* **하십시오***dwClsContext***)** 는지정된개체의새실행인스턴스만들기`CLSID`.

- **CreateInstance (***clsidString* **하십시오***dwClsContext***)** 지정 된 개체의 새 실행 인스턴스 만들기를 보유 하는 유니코드 문자열을 `CLSID` (시작 "**{**") 또는 `ProgID`합니다.

- **CreateInstance (***clsidStringA* **하십시오***dwClsContext***)** 지정 된 개체의 새 실행 인스턴스 만들기를 중 하나를 포함 하는 멀티 바이트 문자열을 `CLSID` (시작 "**{**") 또는 `ProgID`합니다. 호출 [MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar), OEM 코드 페이지가 아닌 ANSI 코드 페이지에서 해당 문자열은 가정 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)