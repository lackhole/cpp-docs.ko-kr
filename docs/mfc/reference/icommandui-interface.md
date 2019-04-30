---
title: ICommandUI 인터페이스
ms.date: 11/04/2016
f1_keywords:
- ICommandUI
- AFXWINFORMS/ICommandUI
- AFXWINFORMS/icommandui__Check
- AFXWINFORMS/ICommandUI::ContinueRouting
- AFXWINFORMS/ICommandUI::Enabled
- AFXWINFORMS/ICommandUI::ID
- AFXWINFORMS/ICommandUI::Index
- AFXWINFORMS/ICommandUI::Radio
- AFXWINFORMS/ICommandUI::Text
helpviewer_keywords:
- ICommandUI interface [MFC]
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
ms.openlocfilehash: 31157ba2445a432af274650011b839fb3df9b3c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322058"
---
# <a name="icommandui-interface"></a>ICommandUI 인터페이스

사용자 인터페이스 명령을 관리합니다.

## <a name="syntax"></a>구문

```
interface class ICommandUI
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[icommandui__Check](#check)|적절 한 선택 상태를이 명령에 대 한 사용자 인터페이스 항목을 설정합니다.|
|[ICommandUI::ContinueRouting](#continuerouting)|처리기 체인에서 현재 메시지를 라우팅하기 계속 하려면 명령 라우팅 메커니즘에 알려줍니다.|
|[ICommandUI::Enabled](#enabled)|사용 하거나이 명령에 대 한 사용자 인터페이스 항목을 사용 하지 않도록 설정 합니다.|
|[ICommandUI::ID](#id)|가 나타내는 사용자 인터페이스 개체의 ID를 가져옵니다는 `ICommandUI` 개체입니다.|
|[ICommandUI::Index](#index)|가 나타내는 사용자 인터페이스 개체의 인덱스를 가져옵니다는 `ICommandUI` 개체입니다.|
|[ICommandUI::Radio](#radio)|적절 한 선택 상태를이 명령에 대 한 사용자 인터페이스 항목을 설정합니다.|
|[ICommandUI::Text](#text)|이 명령에 대 한 사용자 인터페이스 항목의 텍스트를 설정합니다.|

## <a name="remarks"></a>설명

이 인터페이스는 사용자 인터페이스 명령을 관리 하는 속성과 메서드를 제공 합니다. `ICommandUI` 비슷합니다 [CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)점을 제외 하 고 `ICommandUI` .NET 구성 요소와 상호 운용 되는 MFC 응용 프로그램에 사용 됩니다.

`ICommandUI` ON_UPDATE_COMMAND_UI 처리기 내에서 사용 되는 [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)-클래스를 파생 합니다. (선택 또는 클릭)을 활성화 하는 응용 프로그램의 사용자 사용 하도록 설정한 각 메뉴 항목 메뉴가 표시 됩니다 또는 사용 하지 않도록 설정 합니다. ON_UPDATE_COMMAND_UI 처리기를 구현 하 여이 정보를 제공 하는 각 메뉴 명령 대상입니다. 각 응용 프로그램에서 명령 사용자 인터페이스 개체에 대 한 속성 창을 메시지 맵 항목을 만들고 각 처리기에 대 한 함수 프로토타입을 사용 합니다.

방법에 대 한 자세한 내용은 `ICommandUI` 명령 라우팅의 인터페이스를 사용 하는 내용은 [방법: 추가 명령 라우팅에 Windows Forms 컨트롤](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)합니다.

Windows Forms를 사용 하 여 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)입니다.

MFC의 사용자 인터페이스 명령을 관리 하는 방법에 대 한 자세한 내용은 참조 하세요. [CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)합니다.

## <a name="check"></a> ICommandUI::Check

적절 한 선택 상태를이 명령에 대 한 사용자 인터페이스 항목을 설정합니다.
```
property UICheckState Check;
```

## <a name="remarks"></a>설명

이 속성을 적절 한 확인 상태로이 명령에 대 한 사용자 인터페이스 항목을 설정합니다. 다음 값을 확인을 설정 합니다.
- 0 선택 취소
- 1
- 2 설정 비활성화

## <a name="continuerouting"></a> ICommandUI::ContinueRouting

처리기 체인에서 현재 메시지를 라우팅하기 계속 하려면 명령 라우팅 메커니즘에 알려줍니다.
```
void ContinueRouting();
```

## <a name="remarks"></a>설명

이 FALSE를 반환 하는 ON_COMMAND_EX 처리기와 함께에서 사용 해야 하는 고급 멤버 함수입니다. 자세한 내용은 기술 참고 TN006를 참조 하세요. 메시지 맵입니다.

## <a name="enabled"></a> ICommandUI::Enabled

사용 하거나이 명령에 대 한 사용자 인터페이스 항목을 사용 하지 않도록 설정 합니다.
```
property bool Enabled;
```

## <a name="remarks"></a>설명

이 속성을 사용 하도록 설정 하거나이 명령에 대 한 사용자 인터페이스 항목을 사용 하지 않도록 설정 합니다. 사용 설정 항목을 사용 하지 않도록 하려면 FALSE true로 설정 합니다.

## <a name="id"></a> ICommandUI::ID

ICommandUI 개체가 나타내는 사용자 인터페이스 개체의 ID를 가져옵니다.
```
property unsigned int ID;
```

## <a name="remarks"></a>설명

이 속성 메뉴 항목, 도구 모음 단추 또는 ICommandUI 개체에 의해 표시 되는 다른 사용자 인터페이스 개체의 ID를 (핸들)를 가져옵니다.

## <a name="index"></a> ICommandUI::Index

ICommandUI 개체가 나타내는 사용자 인터페이스 개체의 인덱스를 가져옵니다.
```
property unsigned int Index;
```

## <a name="remarks"></a>설명

이 속성 메뉴 항목, 도구 모음 단추 또는 ICommandUI 개체에 의해 표시 되는 다른 사용자 인터페이스 개체의 인덱스를 (핸들)를 가져옵니다.

## <a name="radio"></a> ICommandUI::Radio

적절 한 선택 상태를이 명령에 대 한 사용자 인터페이스 항목을 설정합니다.
```
property bool Radio;
```

## <a name="remarks"></a>설명

이 속성을 적절 한 확인 상태로이 명령에 대 한 사용자 인터페이스 항목을 설정합니다. 항목이 사용 하도록 설정 하려면 true로 설정 하는 라디오를 설정합니다 그렇지 않으면 FALSE입니다.

## <a name="text"></a> ICommandUI::Text

이 명령에 대 한 사용자 인터페이스 항목의 텍스트를 설정합니다.
```
property String^ Text;
```

## <a name="remarks"></a>설명

이 속성에는이 명령에 대 한 사용자 인터페이스 항목의 텍스트를 설정합니다. 텍스트 문자열 핸들에 텍스트를 설정 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h (atlmfc\lib\mfcmifc80.dll 어셈블리에에서 정의 됨)

## <a name="see-also"></a>참고자료

[CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)
