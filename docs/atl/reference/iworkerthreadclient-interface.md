---
title: IWorkerThreadClient 인터페이스
ms.date: 11/04/2016
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
ms.openlocfilehash: 1fa8a5e42d002260076f737d3d33cfa191ff297a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197408"
---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient 인터페이스

`IWorkerThreadClient` 클라이언트에서 구현 된 인터페이스를 [CWorkerThread](../../atl/reference/cworkerthread-class.md) 클래스입니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
__interface IWorkerThreadClient
```

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[CloseHandle](#closehandle)|이 개체와 연결 된 핸들을 종료 하려면이 메서드를 구현 합니다.|
|[Execute](#execute)|이 개체를 사용 하 여 연결 핸들에 신호 하는 경우 코드를 실행 하려면이 메서드를 구현 합니다.|

## <a name="remarks"></a>설명

신호 핸들에 대 한 응답으로 작업자 스레드에서 실행 해야 하는 코드가 있는 경우이 인터페이스를 구현 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** 와 atlutil.h

##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle

이 개체와 연결 된 핸들을 종료 하려면이 메서드를 구현 합니다.

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>매개 변수

*hHandle*<br/>
핸들을 닫아야입니다.

### <a name="return-value"></a>반환 값

성공 또는 실패 시 오류 HRESULT에서 S_OK를 반환 합니다.

### <a name="remarks"></a>설명

호출 하 여이 개체를 사용 하 여 이전에 연결 된이 메서드에 전달 된 핸들이 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.

### <a name="example"></a>예제

다음 코드의 간단한 구현을 보여 줍니다. `IWorkerThreadClient::CloseHandle`합니다.

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

##  <a name="execute"></a>  IWorkerThreadClient::Execute

이 개체를 사용 하 여 연결 핸들에 신호 하는 경우 코드를 실행 하려면이 메서드를 구현 합니다.

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>매개 변수

*dwParam*<br/>
사용자 매개 변수입니다.

*hObject*<br/>
신호에 핸들입니다.

### <a name="return-value"></a>반환 값

성공 또는 실패 시 오류 HRESULT에서 S_OK를 반환 합니다.

### <a name="remarks"></a>설명

호출 하 여이 개체를 사용 하 여 이전에 연관 된 핸들과이 메서드에 전달 되는 DWORD/포인터 [CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)합니다.

### <a name="example"></a>예제

다음 코드의 간단한 구현을 보여 줍니다. `IWorkerThreadClient::Execute`합니다.

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>참고자료

[클래스](../../atl/reference/atl-classes.md)<br/>
[CWorkerThread 클래스](../../atl/reference/cworkerthread-class.md)
