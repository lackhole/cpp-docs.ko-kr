---
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: 84e43de9c40baa3c596c68ed7739471c059cbac7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154853"
---
# <a name="comptrtgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Microsoft 전용**

지정 된 개체의 기존 인스턴스에 연결 된 `CLSID` 또는 `ProgID`합니다.

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
`CLSID` 개체입니다.

*clsidString*<br/>
중 하나를 포함 하는 유니코드 문자열을 `CLSID` (시작 "**{**") 또는 `ProgID`합니다.

*clsidStringA*<br/>
멀티 바이트 문자열을 보유 하는 ANSI 코드 페이지를 사용 하는 `CLSID` (시작 "**{**") 또는 `ProgID`합니다.

## <a name="remarks"></a>설명

이러한 멤버 함수 호출 **GetActiveObject** OLE를 사용 하 여 등록 된 실행 개체에 대 한 포인터를 검색 하려면 다음이 스마트 포인터에 대 한 쿼리 인터페이스 형식 및 합니다. 그러면 결과 포인터는 이 `_com_ptr_t` 개체 안에 캡슐화됩니다. `Release` 이전에 캡슐화 된 포인터에 대 한 참조 횟수를 감소 시키기 위해 호출 됩니다. 이 루틴은 성공 또는 실패를 나타내는 HRESULT를 반환 합니다.

- **GetActiveObject (**`rclsid`**)** 지정 된 개체의 기존 인스턴스에 연결 된 `CLSID`합니다.

- **GetActiveObject (**`clsidString`**)** 중 하나를 포함 하는 유니코드 문자열을 지정 된 개체의 기존 인스턴스에 연결을 `CLSID` (부터는 "**{**") 또는 `ProgID`.

- **GetActiveObject (**`clsidStringA`**)** 보유 하는 멀티 바이트 문자열을 지정 된 개체의 기존 인스턴스에 연결 된 `CLSID` (부터는 "**{**") 또는 `ProgID`. 호출 [MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar), OEM 코드 페이지가 아닌 ANSI 코드 페이지에서 해당 문자열은 가정 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)