---
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: f13a42878392f63096cdfcb405f3f91cc0efe451
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498890"
---
# <a name="_com_ptr_tgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Microsoft 전용**

`CLSID` 또는`ProgID`가 지정 된 개체의 기존 인스턴스에 연결 합니다.

## <a name="syntax"></a>구문

```
HRESULT GetActiveObject(
   const CLSID& rclsid
) throw( );
HRESULT GetActiveObject(
   LPCWSTR clsidString
) throw( );
HRESULT GetActiveObject(
   LPCSTR clsidStringA
) throw( );
```

#### <a name="parameters"></a>매개 변수

*rclsid*<br/>
개체 `CLSID` 의입니다.

*clsidString*<br/>
(" **{** "로 시작) 또는을 `ProgID`포함 하는 유니코드 문자열입니다. `CLSID`

*clsidStringA*<br/>
(" **{** "로 시작) 또는을 `ProgID`포함 하는 ANSI 코드 페이지를 사용 하는 멀티 바이트 문자열입니다. `CLSID`

## <a name="remarks"></a>설명

이러한 멤버 함수는 **Getactiveobject** 를 호출 하 여 OLE에 등록 된 실행 중인 개체에 대 한 포인터를 검색 한 다음이 스마트 포인터의 인터페이스 형식에 대 한 쿼리를 실행 합니다. 그러면 결과 포인터는 이 `_com_ptr_t` 개체 안에 캡슐화됩니다. `Release`이전에 캡슐화 된 포인터에 대 한 참조 횟수를 감소 하기 위해가 호출 됩니다. 이 루틴은 성공 또는 실패를 나타내는 HRESULT를 반환 합니다.

- **Getactiveobject (** `rclsid` **)** 는가 `CLSID`지정 된 개체의 기존 인스턴스에 연결 합니다.

- **Getactiveobject (** `clsidString` **)** 는 `CLSID` (" **{** "로 시작) 또는을 `ProgID`포함 하는 유니코드 문자열이 지정 된 개체의 기존 인스턴스에 연결 합니다.

- **Getactiveobject (** `clsidStringA` **)** 는 `CLSID` (" **{** "로 시작) 또는을 `ProgID`포함 하는 멀티 바이트 문자열을 지정 하 여 개체의 기존 인스턴스에 연결 합니다. 는 OEM 코드 페이지가 아니라 ANSI 코드 페이지에 문자열이 있는 것으로 가정 하는 [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)를 호출 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)