---
title: FtmBase 클래스
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase
- ftm/Microsoft::WRL::FtmBaseCreateGlobalInterfaceTable
- ftm/Microsoft::WRL::FtmBase::DisconnectObject
- ftm/Microsoft::WRL::FtmBase::FtmBase
- ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
- ftm/Microsoft::WRL::FtmBase::marshaller_
- ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
helpviewer_keywords:
- Microsoft::WRL::FtmBase class
- Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable method
- Microsoft::WRL::FtmBase::DisconnectObject method
- Microsoft::WRL::FtmBase::FtmBase, constructor
- Microsoft::WRL::FtmBase::GetMarshalSizeMax method
- Microsoft::WRL::FtmBase::GetUnmarshalClass method
- Microsoft::WRL::FtmBase::MarshalInterface method
- Microsoft::WRL::FtmBase::marshaller_ data member
- Microsoft::WRL::FtmBase::ReleaseMarshalData method
- Microsoft::WRL::FtmBase::UnmarshalInterface method
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
ms.openlocfilehash: fb7f103d8ea647f554d9bbf26c2e218d34f6b1ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398448"
---
# <a name="ftmbase-class"></a>FtmBase 클래스

자유 스레드된 마샬러 개체를 나타냅니다.

## <a name="syntax"></a>구문

```cpp
class FtmBase :
    public Microsoft::WRL::Implements<
        Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,
        Microsoft::WRL::CloakedIid<IMarshal>
    >;
```

## <a name="remarks"></a>설명

자세한 내용은 [RuntimeClass 클래스](runtimeclass-class.md)합니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

| 이름                         | 설명                                        |
| ---------------------------- | -------------------------------------------------- |
| [FtmBase::FtmBase](#ftmbase) | `FtmBase` 클래스의 새 인스턴스를 초기화합니다. |

### <a name="public-methods"></a>Public 메서드

| 이름                                                               | 설명                                                                                                                                                          |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [FtmBase::CreateGlobalInterfaceTable](#createglobalinterfacetable) | (GIT) 전역 인터페이스 테이블을 만듭니다.                                                                                                                              |
| [FtmBase::DisconnectObject](#disconnectobject)                     | 개체에 모든 외부 연결을 강제로 해제합니다. 개체의 서버 개체의 구현의 종료 하기 전에이 메서드를 호출 합니다.                |
| [FtmBase::GetMarshalSizeMax](#getmarshalsizemax)                   | 지정된 된 개체의 지정 된 인터페이스 포인터를 마샬링하는 데 필요한 바이트 수에 상한값을 가져옵니다.                                                |
| [FtmBase::GetUnmarshalClass](#getunmarshalclass)                   | COM 해당 프록시에 대 한 코드를 포함 하는 DLL을 찾기 위해 사용 하 여 CLSID를 가져옵니다. COM 프록시 초기화 되지 않은 인스턴스를 만들려면이 DLL을 로드 합니다. |
| [FtmBase::MarshalInterface](#marshalinterface)                     | 일부 클라이언트 프로세스에서 프록시 개체를 초기화 하는 데 필요한 데이터를 스트림으로 씁니다.                                                                          |
| [FtmBase::ReleaseMarshalData](#releasemarshaldata)                 | 마샬링된 데이터 패킷을 삭제합니다.                                                                                                                                    |
| [FtmBase::UnmarshalInterface](#unmarshalinterface)                 | 새로 만든된 프록시를 초기화 하 고 해당 프록시에 인터페이스 포인터를 반환 합니다.                                                                                    |

### <a name="public-data-members"></a>공용 데이터 멤버

| 이름                                | 설명                                       |
| ----------------------------------- | ------------------------------------------------- |
| [FtmBase::marshaller_](#marshaller) | 자유 스레드된 마샬러에 대 한 참조를 보유합니다. |

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`FtmBase`

## <a name="requirements"></a>요구 사항

**헤더:** ftm.h

**네임스페이스:** Microsoft::WRL

## <a name="createglobalinterfacetable"></a>FtmBase::CreateGlobalInterfaceTable

(GIT) 전역 인터페이스 테이블을 만듭니다.

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>매개 변수

*git*<br/>
이 작업이 완료 될 때 전역 인터페이스 테이블에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

### <a name="remarks"></a>설명

자세한 내용은 참조 하세요.는 `IGlobalInterfaceTable` 항목에는 `COM Interfaces` 의 하위를 `COM Reference` MSDN 라이브러리의 항목입니다.

## <a name="disconnectobject"></a>FtmBase::DisconnectObject

개체에 모든 외부 연결을 강제로 해제합니다. 개체의 서버 개체의 구현의 종료 하기 전에이 메서드를 호출 합니다.

```cpp
STDMETHODIMP DisconnectObject(
   __in DWORD dwReserved
) override;
```

### <a name="parameters"></a>매개 변수

*dwReserved*<br/>
나중에 사용하도록 예약되어 있습니다. 0이어야 합니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="ftmbase"></a>FtmBase::FtmBase

`FtmBase` 클래스의 새 인스턴스를 초기화합니다.

```cpp
FtmBase();
```

## <a name="getmarshalsizemax"></a>FtmBase::GetMarshalSizeMax

지정된 된 개체의 지정 된 인터페이스 포인터를 마샬링하는 데 필요한 바이트 수에 상한값을 가져옵니다.

```cpp
STDMETHODIMP GetMarshalSizeMax(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out DWORD *pSize
) override;
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
마샬링될 인터페이스의 식별자에 대 한 참조입니다.

*pv*<br/>
인터페이스 포인터를 마샬링할 수 있습니다. NULL 일 수 있습니다.

*dwDestContext*<br/>
대상 위치 지정된 된 인터페이스를 컨텍스트 마샬링해야 합니다.

하나 이상의 MSHCTX 열거형 값을 지정 합니다.

현재 역마샬링 발생할 수 있습니다 (MSHCTX_INPROC) 현재 프로세스의 다른 아파트 또는 현재 프로세스 (MSHCTX_LOCAL)와 동일한 컴퓨터에서 다른 프로세스에서.

*pvDestContext*<br/>
사용 하도록 예약 됩니다. NULL 이어야 합니다.

*mshlflags*<br/>
클라이언트 프로세스에 다시 전송할 데이터를 마샬링할 수 인지 여부를 나타내는 플래그-일반적인 사례-여러 클라이언트에서 검색할 수 있는 전역 테이블에 기록 합니다. 하나 이상의 MSHLFLAGS 열거형 값을 지정 합니다.

*pSize*<br/>
이 작업이 완료 될 때 마샬링 스트림에 쓸 데이터의 양에 상한을에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 이 고, 그렇지 E_FAIL 또는 E_NOINTERFACE

## <a name="getunmarshalclass"></a>FtmBase::GetUnmarshalClass

COM 해당 프록시에 대 한 코드를 포함 하는 DLL을 찾기 위해 사용 하 여 CLSID를 가져옵니다. COM 프록시 초기화 되지 않은 인스턴스를 만들려면이 DLL을 로드 합니다.

```cpp
STDMETHODIMP GetUnmarshalClass(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out CLSID *pCid
) override;
```

### <a name="parameters"></a>매개 변수

*riid*<br/>
마샬링될 인터페이스의 식별자에 대 한 참조입니다.

*pv*<br/>
마샬링될; 인터페이스에 대 한 포인터 호출자가 원하는 인터페이스에 대 한 포인터 없는 경우 NULL 일 수 있습니다.

*dwDestContext*<br/>
대상 위치 지정된 된 인터페이스를 컨텍스트 마샬링해야 합니다.

하나 이상의 MSHCTX 열거형 값을 지정 합니다.

역마샬링 하거나 현재 프로세스 (MSHCTX_INPROC)의 다른 아파트에서 현재 프로세스 (MSHCTX_LOCAL)와 동일한 컴퓨터에서 다른 프로세스에서 발생할 수 있습니다.

*pvDestContext*<br/>
사용 하도록 예약 됩니다. NULL 이어야 합니다.

*mshlflags*<br/>
이 작업이 완료 될 때 클라이언트 프로세스에서 프록시를 만드는 데 사용할 CLSID에 대 한 포인터입니다.

*pCid*

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 그렇지 않으면 S_FALSE입니다.

## <a name="marshalinterface"></a>FtmBase::MarshalInterface

일부 클라이언트 프로세스에서 프록시 개체를 초기화 하는 데 필요한 데이터를 스트림으로 씁니다.

```cpp
STDMETHODIMP MarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags
) override;
```

### <a name="parameters"></a>매개 변수

*pStm*<br/>
마샬링 중 사용할 스트림에 대 한 포인터입니다.

*riid*<br/>
마샬링될 인터페이스의 식별자에 대 한 참조입니다. 이 인터페이스에서 파생 되어야 합니다는 `IUnknown` 인터페이스입니다.

*pv*<br/>
마샬링될; 인터페이스 포인터에 대 한 포인터 호출자가 원하는 인터페이스에 대 한 포인터 없는 경우 NULL 일 수 있습니다.

*dwDestContext*<br/>
대상 위치 지정된 된 인터페이스를 컨텍스트 마샬링해야 합니다.

하나 이상의 MSHCTX 열거형 값을 지정 합니다.

역마샬링 현재 프로세스 (MSHCTX_LOCAL)와 동일한 컴퓨터에서 다른 프로세스 또는 현재 프로세스 (MSHCTX_INPROC)의 다른 아파트에서 발생할 수 있습니다.

*pvDestContext*<br/>
나중에 사용하도록 예약되어 있습니다. 0이어야 합니다.

*mshlflags*<br/>
클라이언트 프로세스에 다시 전송할 데이터를 마샬링할 수 인지 여부를 지정-일반적인 사례-여러 클라이언트에서 검색할 수 있는 전역 테이블에 기록 합니다.

### <a name="return-value"></a>반환 값

인터페이스 포인터를 성공적으로 마샬링될 S_OK입니다.

지정된 된 인터페이스 E_NOINTERFACE 지원 되지 않습니다.

스트림을 STG_E_MEDIUMFULL 꽉 찼습니다.

E_FAIL 작업에 실패 했습니다.

## <a name="marshaller"></a>FtmBase::marshaller_

자유 스레드된 마샬러에 대 한 참조를 보유합니다.

```cpp
Microsoft::WRL::ComPtr<IMarshal> marshaller_; ;
```

## <a name="releasemarshaldata"></a>FtmBase::ReleaseMarshalData

마샬링된 데이터 패킷을 삭제합니다.

```cpp
STDMETHODIMP ReleaseMarshalData(
   __in IStream *pStm
) override;
```

### <a name="parameters"></a>매개 변수

*pStm*<br/>
제거할 데이터 패킷을 포함 하는 스트림에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.

## <a name="unmarshalinterface"></a>FtmBase::UnmarshalInterface

새로 만든된 프록시를 초기화 하 고 해당 프록시에 인터페이스 포인터를 반환 합니다.

```cpp
STDMETHODIMP UnmarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __deref_out void **ppv
) override;
```

### <a name="parameters"></a>매개 변수

*pStm*<br/>
인터페이스 포인터를 역 마샬링해야 하는 스트림에 대 한 포인터입니다.

*riid*<br/>
역 마샬링해야 하는 인터페이스의 식별자에 대 한 참조입니다.

*ppv*<br/>
이 작업이 완료 되 면에서 요청 된 인터페이스 포인터를 받는 포인터 변수의 주소 *riid*합니다. 이 작업에 성공 하면 **ppv* 마샬링해야 하는 인터페이스의 요청 된 인터페이스 포인터를 포함 합니다.

### <a name="return-value"></a>반환 값

성공 하면 s_ok이 고 이 고, 그렇지 E_NOINTERFACE 또는 E_FAIL입니다.
