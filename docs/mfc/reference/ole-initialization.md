---
title: OLE 초기화
ms.date: 11/04/2016
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
ms.openlocfilehash: 3d49b37ffc2561fa9a51463a893ec2ba4f4fb725
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310278"
---
# <a name="ole-initialization"></a>OLE 초기화

응용 프로그램에서 OLE 시스템 서비스를 사용 하려면 먼저 OLE 시스템 Dll을 초기화 하 고 Dll을 올바른 버전 인지 확인 합니다. `AfxOleInit` 함수 OLE 시스템 Dll을 초기화 합니다.

### <a name="ole-initialization"></a>OLE 초기화

|||
|-|-|
|[AfxOleInit](#afxoleinit)|OLE 라이브러리를 초기화합니다.|
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|응용 프로그램 개체에서이 함수를 호출 `InitInstance` 함수 OLE 컨트롤의 포함에 대 한 지원을 사용 하도록 설정 합니다.|

## <a name="afxenablecontrolcontainer"></a> AfxEnableControlContainer

응용 프로그램 개체에서이 함수를 호출 `InitInstance` 함수 OLE 컨트롤의 포함에 대 한 지원을 사용 하도록 설정 합니다.

### <a name="syntax"></a>구문

```
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>설명

OLE 컨트롤 (이제 ActiveX 컨트롤 이라고 함)에 대 한 자세한 내용은 참조 하세요. [ActiveX 컨트롤 항목](../mfc-activex-controls.md)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

##  <a name="afxoleinit"></a>  AfxOleInit

OLE 지원 응용 프로그램을 초기화합니다.

```
BOOL AFXAPI AfxOleInit();
```

### <a name="return-value"></a>반환 값

성공 하면 0이 아닌 값 0 초기화에 실패 하면 가능한 경우 잘못 된 버전의 OLE 시스템 Dll 설치 되기 때문입니다.

### <a name="remarks"></a>설명

MFC 응용 프로그램에 대 한 OLE 지원 초기화 하려면이 함수를 호출 합니다. 이 함수를 호출 하는 경우에 다음 작업이 수행 됩니다.

- 호출 응용 프로그램의 현재 아파트에서 COM 라이브러리를 초기화합니다. 자세한 내용은 [OleInitialize](/windows/desktop/api/ole2/nf-ole2-oleinitialize)합니다.

- 메시지 필터 개체를 구현 합니다 [IMessageFilter](/windows/desktop/api/objidl/nn-objidl-imessagefilter) 인터페이스입니다. 이 메시지 필터에 대 한 호출을 사용 하 여 액세스할 수 있습니다 [AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)합니다.

> [!NOTE]
>  하는 경우 **AfxOleInit** 라고는 MFC DLL에서 호출이 실패 합니다. 오류 함수는 DLL에서 호출 되는 경우 OLE 시스템 이전에 초기화 된 호출 응용 프로그램에서 가정 하기 때문에 발생 합니다.

> [!NOTE]
>  MFC 응용 프로그램은 단일 스레드 아파트 (STA)로 초기화 되어야 합니다. 호출 하는 경우 [CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) 에서 프로그램 `InitInstance` 재정의 COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED 아님)를 지정 합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxdisp.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
