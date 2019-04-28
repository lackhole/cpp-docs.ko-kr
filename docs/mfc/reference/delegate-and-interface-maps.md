---
title: 대리자 및 인터페이스 맵 매크로 (MFC)
ms.date: 03/30/2017
helpviewer_keywords:
- delegate map macros [MFC]
- event map macros [MFC]
- interface map macros [MFC]
ms.assetid: 3840e642-ff7d-4bdc-998b-c7d8fc50890e
ms.openlocfilehash: 8f48b916f7130551fc8d4da5bb2ebc75d8d728d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62322984"
---
# <a name="delegate-and-interface-map-macros"></a>대리자 및 인터페이스 맵 매크로

MFC는 대리자 및 인터페이스 맵에 대 한 이러한 매크로 지원합니다.

|||
|-|-|
|[BEGIN_DELEGATE_MAP](#begin_delegate_map)|대리자 맵에 시작합니다.|
|[BEGIN_INTERFACE_MAP](#begin_interface_map)|인터페이스 맵 정의 시작 합니다.|
|[CommandHandler 대리자](#commandhandler)|명령 소스를 사용 하 여 콜백 메서드를 등록합니다.  |
|[END_DELEGATE_MAP](#end_delegate_map)|대리자 맵에 종료합니다.|
|[END_INTERFACE_MAP](#end_interface_map)|인터페이스 맵을 구현 파일에서 종료 됩니다. |
|[EVENT_DELEGATE_ENTRY](#event_delegate_entry)|대리자 맵에 항목을 만듭니다.|
|[INTERFACE_PART](#interface_part)|개체에서 지원할 각 인터페이스에 대 한 BEGIN_INTERFACE_MAP 매크로 및 END_INTERFACE_MAP 매크로 간에 사용 됩니다.|
|[MAKE_DELEGATE](#make_delegate)|관리 되는 컨트롤에 이벤트 처리기를 연결합니다.|

## <a name="begin_delegate_map"></a> BEGIN_DELEGATE_MAP

대리자 맵에 시작합니다.

### <a name="syntax"></a>구문

```
BEGIN_DELEGATE_MAP(  CLASS );
```

### <a name="parameters"></a>매개 변수

*CLASS*<br/>
관리 되는 컨트롤 호스트 되는 클래스입니다.

### <a name="remarks"></a>설명

이 매크로 대리자 지도 작성 하는 대리자 항목 목록의 시작 부분을 표시 합니다. 이 매크로 사용 하는 방법의 예제를 참조 하세요 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** msclr\event.h

##  <a name="begin_interface_map"></a>BEGIN_INTERFACE_MAP

구현 파일에서 사용 하는 경우 인터페이스 맵의 정의 시작 합니다.

### <a name="syntax"></a>구문

```
BEGIN_INTERFACE_MAP( theClass, baseClass )
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
인터페이스 맵을 정의할 클래스

*baseClass*<br/>
클래스 *theClass* 에서 파생 됩니다.

### <a name="remarks"></a>설명

구현 되는 각 인터페이스에 대해 하나 이상의 INTERFACE_PART 매크로 호출이 있습니다. 클래스를 사용 하는 각 집계에 대 한 하나의 INTERFACE_AGGREGATE 매크로 호출이 있습니다.

인터페이스 맵에 대 한 자세한 내용은 참조 하세요. [기술 참고 38](../tn038-mfc-ole-iunknown-implementation.md)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="commandhandler"></a>CommandHandler 대리자

명령 소스를 사용 하 여 콜백 메서드를 등록합니다.

### <a name="syntax"></a>구문

```
delegate void CommandHandler(  UINT^ cmdID  );
```

### <a name="parameters"></a>매개 변수

*cmdID*<br/>
명령 ID입니다.

### <a name="remarks"></a>설명

이 대리자 명령 소스를 사용 하 여 콜백 메서드를 등록합니다. 명령 소스 개체에 대리자를 추가 하는 경우 콜백 메서드는 지정 된 원본에서 가져온 명령에 대 한 처리기를 됩니다.

자세한 내용은 [방법: 추가 명령 라우팅에 Windows Forms 컨트롤](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)합니다.

Windows Forms를 사용 하 여 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h (atlmfc\lib\mfcmifc80.dll 어셈블리에에서 정의 됨)

##  <a name="commanduihandler"></a>CommandUIHandler

사용자 인터페이스 업데이트 명령 메시지를 사용 하 여 콜백 메서드를 등록합니다.

### <a name="syntax"></a>구문

```
delegate void CommandUIHandler(  unsigned int cmdID, ICommandUI^ cmdUI);
```

### <a name="parameters"></a>매개 변수

*cmdID*<br/>
명령 ID입니다.

*cmdUI*<br/>
명령 메시지 id입니다.

### <a name="remarks"></a>설명

이 대리자는 사용자 인터페이스 업데이트 명령 메시지를 사용 하 여 콜백 메서드를 등록합니다. `CommandUIHandler` 비슷합니다 [CommandHandler](#commandhandler) 제외 하 고이 대리자는 사용자 인터페이스 개체 업데이트 명령을 사용 하 여 사용 합니다. 사용자 인터페이스 업데이트 명령 매핑해야 일대일 메시지 처리기 메서드를 사용 하 여 합니다.

Windows Forms를 사용 하 여 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)입니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h (atlmfc\lib\mfcmifc80.dll 어셈블리에에서 정의 됨)

##  <a name="end_delegate_map"></a>END_DELEGATE_MAP

대리자 맵에 종료합니다.

### <a name="syntax"></a>구문

```
END_DELEGATE_MAP();
```

### <a name="remarks"></a>설명

이 매크로 대리자 지도 작성 하는 대리자 항목 목록의 끝을 표시 합니다. 이 매크로 사용 하는 방법의 예제를 참조 하세요 [EVENT_DELEGATE_ENTRY](#event_delegate_entry)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** msclr\event.h

##  <a name="end_interface_map"></a>END_INTERFACE_MAP

인터페이스 맵을 구현 파일에서 종료 됩니다.

### <a name="syntax"></a>구문

```
END_INTERFACE_MAP( )
```

### <a name="remarks"></a>설명

인터페이스 맵에 대 한 자세한 내용은 참조 하세요. [기술 참고 38](../tn038-mfc-ole-iunknown-implementation.md)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="event_delegate_entry"></a>EVENT_DELEGATE_ENTRY

대리자 맵에 항목을 만듭니다.

### <a name="syntax"></a>구문

```
EVENT_DELEGATE_ENTRY(MEMBER, ARG0, ARG1);
```

### <a name="parameters"></a>매개 변수

*MEMBER*<br/>
컨트롤에 연결할 이벤트 처리기 메서드입니다.

*ARG0*<br/>
관리 되는 이벤트 처리기 메서드의 첫 번째 인수 같은 `Object^`합니다.

*ARG1*<br/>
관리 되는 이벤트 처리기 메서드의 두 번째 인수 같은 `EventArgs^`합니다.

### <a name="remarks"></a>설명

만든 관리 되는 이벤트 처리기 대리자에 해당 하는 각 항목 대리자 맵에 [MAKE_DELEGATE](#make_delegate)합니다.

### <a name="example"></a>예제

다음 코드 예제에 대 한 대리자 맵에 항목을 만들려면 EVENT_DELEGATE_ENTRY를 사용 하는 방법을 보여 줍니다는 `OnClick` 이벤트 처리기; MAKE_DELEGATE의 코드 예제를 참조 하십시오. 자세한 내용은 [방법: 네이티브에서 Windows Forms 이벤트 싱크 C++ 클래스](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)합니다.

```cpp
BEGIN_DELEGATE_MAP(CMyView)
   EVENT_DELEGATE_ENTRY(OnClick, System::Object^, System::EventArgs^)
END_DELEGATE_MAP()
```

### <a name="requirements"></a>요구 사항

**헤더:** msclr\event.h

##  <a name="interface_part"></a>INTERFACE_PART

개체에서 지원할 각 인터페이스에 대 한 BEGIN_INTERFACE_MAP 매크로 및 END_INTERFACE_MAP 매크로 간에 사용 됩니다.

### <a name="syntax"></a>구문

```
INTERFACE_PART( theClass, iid, localClass)
```

### <a name="parameters"></a>매개 변수

*theClass*<br/>
인터페이스 맵을 포함하는 클래스의 이름
*iid*<br/>
포함된 된 클래스에 매핑될 수 있는 IID입니다.
*localClass*<br/>
로컬 클래스의 이름입니다.

### <a name="remarks"></a>설명

에 의해 표시 되는 클래스의 멤버에 IID를 매핑할 수 있습니다 *theClass* 하 고 *localClass*합니다.

인터페이스 맵에 대 한 자세한 내용은 참조 하세요. [기술 참고 38](../tn038-mfc-ole-iunknown-implementation.md)합니다.

### <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="make_delegate"></a>MAKE_DELEGATE

관리 되는 컨트롤에 이벤트 처리기를 연결합니다.

### <a name="syntax"></a>구문

```
MAKE_DELEGATE( DELEGATE,  MEMBER) ;
```

### <a name="parameters"></a>매개 변수

*DELEGATE*<br/>
관리 되는 이벤트 처리기의 형식 같은 대리자 [EventHandler](assetId:///T:System.EventHandler?qualifyHint=False&autoUpgrade=True)합니다.

*MEMBER*<br/>
컨트롤에 연결할 이벤트 처리기 메서드의 이름입니다.

### <a name="remarks"></a>설명

이 매크로 형식의 관리 되는 이벤트 처리기 대리자를 만듭니다 *위임할* 및 이름의 *멤버*합니다. 관리 되는 이벤트 처리기 대리자는 관리 되는 이벤트를 처리 하는 기본 클래스를 허용 합니다.

### <a name="example"></a>예제

다음 코드 예제를 호출 하는 방법을 보여 줍니다 `MAKE_DELEGATE` 연결 하는 `OnClick` MFC 컨트롤에 이벤트 처리기 `MyControl`합니다. 이 매크로 MFC 응용 프로그램에서 작동 하는 방식에 대 한 광범위 한 설명과 참조 하세요. [방법: 네이티브에서 Windows Forms 이벤트 싱크 C++ 클래스](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)합니다.

```cpp
// CMyView derives from CWinFormsView.
void CMyView::OnInitialUpdate()
{
   CWinFormsView::OnInitialUpdate();

   GetControl()->Click += MAKE_DELEGATE(System::EventHandler, OnClick);
}
```

### <a name="requirements"></a>요구 사항

**헤더:** msclr\event.h

## <a name="see-also"></a>참고자료

[방법: 네이티브 C++ 클래스에서 Windows Forms 이벤트 싱크](../../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)<br/>
[방법: Windows Forms 컨트롤에 명령 라우팅 추가](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[매크로 및 전역](mfc-macros-and-globals.md)<br/>
