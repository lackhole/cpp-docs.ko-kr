---
title: ICommandTarget 인터페이스
ms.date: 11/04/2016
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
helpviewer_keywords:
- ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
ms.openlocfilehash: a224b868ea1923bb4f84b0d682c71fadb63da572
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322071"
---
# <a name="icommandtarget-interface"></a>ICommandTarget 인터페이스

명령 소스 개체에서 명령을 수신에 대 한 인터페이스를 사용 하 여 사용자 정의 컨트롤을 제공 합니다.

## <a name="syntax"></a>구문

```
interface class ICommandTarget
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[ICommandTarget::Initialize](#initialize)|명령 대상 개체를 초기화합니다.|

## <a name="remarks"></a>설명

MFC 보기에서 사용자 정의 컨트롤을 호스트 하는 경우 [CWinFormsView](../../mfc/reference/cwinformsview-class.md) 경로 명령과 업데이트 명령 UI 메시지를 사용자 정의 컨트롤에 기록 MFC 명령 (예: 프레임 메뉴 항목 및 도구 모음 단추)를 처리할 수 있도록 합니다. 구현 하 여 `ICommandTarget`, 사용자 정의 컨트롤에 대 한 참조를 제공 합니다 [ICommandSource](../../mfc/reference/icommandsource-interface.md) 개체입니다.

[방법: Windows Forms 컨트롤을 추가할 명령 라우팅](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) 사용 하는 방법의 예 `ICommandTarget`합니다.

Windows Forms를 사용 하 여 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)입니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h (atlmfc\lib\mfcmifc80.dll 어셈블리에에서 정의 됨)

##  <a name="initialize"></a> ICommandTarget::Initialize

명령 대상 개체를 초기화합니다.

```
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>매개 변수

*cmdSource*<br/>
명령 소스 개체에 대 한 핸들입니다.

### <a name="remarks"></a>설명

MFC 뷰에서 사용자 정의 컨트롤을 호스트 하는 경우 cwinformsview 명령과 업데이트 명령 UI 메시지를 사용자 컨트롤에 MFC 명령을 처리할 수 있도록 합니다.

이 메서드는 명령 대상 개체를 초기화 하 고 지정 된 명령 소스 개체 cmdSource 연결. 사용자 컨트롤 클래스 구현에서 호출 해야 합니다. 초기화 시 초기화 구현에서 호출 ICommandSource::AddCommandHandler 여 명령 원본 개체를 사용 하 여 명령 처리기를 등록 해야 합니다. 참조 하는 방법. 초기화를 사용 하 여이 작업을 수행 하는 방법의 예제에 대 한 Windows Forms 컨트롤에 명령 라우팅를 추가 합니다.

## <a name="see-also"></a>참고자료

[방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandSource 인터페이스](../../mfc/reference/icommandsource-interface.md)
