---
title: CWordArray 클래스
ms.date: 09/07/2019
f1_keywords:
- CWordArray
- AFXCOLL/CWordArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
ms.openlocfilehash: c136bbb14e0d7cffc604813731b6f87ba18063cf
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907908"
---
# <a name="cwordarray-class"></a>CWordArray 클래스

16비트 단어 배열을 지원합니다.

## <a name="syntax"></a>구문

```
class CWordArray : public CObject
```

## <a name="members"></a>멤버

의 `CWordArray` 멤버 함수는 [CObArray](../../mfc/reference/cobarray-class.md)클래스의 멤버 함수와 비슷합니다. 이처럼 두 함수가 비슷하므로 `CObArray` 참조 설명서에서 멤버 함수 관련 사항을 확인할 수 있습니다. [CObject](../../mfc/reference/cobject-class.md) 포인터가 함수 매개 변수 또는 반환 값으로 표시 되는 경우에는 단어를 대체 합니다.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

예를 들어 위의 코드는

`WORD CWordArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Public 생성자

|이름|Description|
|----------|-----------------|
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|빈 배열을 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|Description|
|----------|-----------------|
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|배열 끝에 요소를 추가하고 필요하면 배열을 확장합니다.|
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|배열에 다른 배열을 추가하고 필요하면 배열을 확장합니다.|
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|배열에 다른 배열을 복사하고 필요하면 배열을 확장합니다.|
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|배열 내의 요소 포인터에 대한 임시 참조를 반환합니다.|
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|현재 상한을 초과하며 사용되지 않는 모든 메모리를 해제합니다.|
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|지정된 인덱스의 값을 반환합니다.|
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|이 배열에 있는 요소의 수를 가져옵니다.|
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|배열의 요소에 대한 액세스를 허용합니다. NULL 일 수 있습니다.|
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|이 배열에 있는 요소의 수를 가져옵니다.|
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|유효한 최대 인덱스를 반환합니다.|
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|지정한 인덱스에 요소 하나 또는 다른 배열의 모든 요소를 삽입합니다.|
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|배열이 비어 있는지를 확인합니다.|
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|이 배열의 모든 요소를 반환합니다.|
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|특정 인덱스의 요소를 제거합니다.|
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|지정된 인덱스의 값을 설정합니다. 배열은 확장할 수 없습니다.|
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|지정된 인덱스의 값을 설정합니다. 필요한 경우 배열을 확장합니다.|
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|이 배열에 포함된 요소의 수를 설정합니다.|

### <a name="public-operators"></a>Public 연산자

|이름|Description|
|----------|-----------------|
|[CObArray:: operator&#91;&#93;](../../mfc/reference/cobarray-class.md#operator_at)|지정한 인덱스에 있는 요소를 설정하거나 가져옵니다.|

## <a name="remarks"></a>설명

`CWordArray`[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 매크로를 통합 하 여 요소의 serialization 및 덤프를 지원 합니다. 오버 로드 된 삽입 연산자나 [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) 멤버 함수를 사용 하 여 단어의 배열을 보관 파일에 저장 한 경우에는 각 요소가 차례로 serialize 됩니다.

> [!NOTE]
>  배열을 사용하기 전에 `SetSize`를 사용하여 배열 크기를 설정하고 배열에 대해 메모리를 할당합니다. `SetSize`를 사용하지 않는 경우 배열에 요소를 추가하면 배열이 자주 다시 할당되고 복사됩니다. 이처럼 다시 할당 및 복사가 자주 수행되면 효율성이 떨어지며 메모리가 조각화될 수 있습니다.

배열의 개별 요소에 대 한 덤프가 필요한 경우 덤프 컨텍스트의 깊이를 1 이상으로 설정 해야 합니다.

사용 `CWordArray`에 대 한 자세한 내용은 [컬렉션](../../mfc/collections.md)문서를 참조 하세요.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CWordArray`

## <a name="requirements"></a>요구 사항

**헤더:** afxcoll.h

##  <a name="icommandsource_interface"></a>ICommandSource 인터페이스

명령 소스 개체에서 사용자 컨트롤로 전송 된 명령을 관리 합니다.

```
interface class ICommandSource
```

### <a name="remarks"></a>설명

MFC 뷰에서 사용자 정의 컨트롤을 호스트 하는 경우 [CWinFormsView 클래스](../../mfc/reference/cwinformsview-class.md) 는 명령을 라우팅하고 사용자 정의 컨트롤에 명령 UI 메시지를 업데이트 하 여 mfc 명령을 처리할 수 있도록 합니다 (예: 프레임 메뉴 항목 및 도구 모음 단추). 을 구현 하 여 사용자 정의 컨트롤에 `ICommandSource` 개체에 대 한 참조를 제공 합니다.

[방법: 를 사용](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) `ICommandTarget`하는 방법에 대 한 예제를 보려면 Windows Forms 컨트롤에 명령 라우팅을 추가 합니다.

Windows Forms 사용에 대 한 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../../dotnet/using-a-windows-form-user-control-in-mfc.md)을 참조 하세요.

##  <a name="addcommandhandler"></a>  ICommandSource::AddCommandHandler

명령 소스 개체에 명령 처리기를 추가 합니다.

```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>매개 변수

*cmdID*<br/>
명령 ID입니다.

*cmdHandler*<br/>
명령 처리기 메서드에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 명령 처리기 *Cmdhandler* 를 명령 소스 개체에 추가 하 고이 처리기를 *cmdID*에 매핑합니다.

[방법: 를 사용](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) `AddCommandHandler`하는 방법에 대 한 예제를 보려면 Windows Forms 컨트롤에 명령 라우팅을 추가 합니다.

##  <a name="addcommandrangehandler"></a>  ICommandSource::AddCommandRangeHandler

명령 처리기 그룹을 명령 소스 개체에 추가 합니다.

```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>매개 변수

*cmdIDMin*<br/>
명령 ID 범위의 시작 인덱스입니다.

*cmdIDMax*<br/>
명령 ID 범위의 끝 인덱스입니다.

*cmdHandler*<br/>
명령이 매핑되는 메시지 처리기 메서드에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 인접 한 명령 Id 범위를 단일 메시지 처리기에 매핑하고 명령 소스 개체에 추가 합니다. 이는 한 가지 방법을 사용 하 여 관련 단추 그룹을 처리 하는 데 사용 됩니다.

##  <a name="addcommandrangeuihandler"></a>  ICommandSource::AddCommandRangeUIHandler

사용자 인터페이스 명령 메시지 처리기 그룹을 명령 소스 개체에 추가 합니다.

```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>매개 변수

*cmdIDMin*<br/>
명령 ID 범위의 시작 인덱스입니다.

*cmdIDMax*<br/>
명령 ID 범위의 끝 인덱스입니다.

*cmdHandler*<br/>
명령이 매핑되는 메시지 처리기 메서드에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 인접 한 명령 Id 범위를 단일 사용자 인터페이스 명령 메시지 처리기에 매핑하고 명령 소스 개체에 추가 합니다. 이는 한 가지 방법을 사용 하 여 관련 단추 그룹을 처리 하는 데 사용 됩니다.

##  <a name="addcommanduihandler"></a>  ICommandSource::AddCommandUIHandler

명령 소스 개체에 사용자 인터페이스 명령 메시지 처리기를 추가 합니다.

```
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>매개 변수

*cmdID*<br/>
명령 ID입니다.

*cmdUIHandler*<br/>
사용자 인터페이스 명령 메시지 처리기 메서드에 대 한 핸들입니다.

### <a name="remarks"></a>설명

이 메서드는 사용자 인터페이스 명령 메시지 처리기 *Cmdhandler* 를 명령 소스 개체에 추가 하 고이 처리기를 *cmdID*에 매핑합니다.

##  <a name="postcommand"></a>  ICommandSource::PostCommand

메시지 처리를 기다리지 않고 메시지를 게시 합니다.

```
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>매개 변수

*command*<br/>
게시할 메시지의 명령 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 *명령*에 지정 된 ID에 매핑된 메시지를 비동기적으로 게시 합니다. 그러면 [CWnd::P Oststststststststststststststststststststststststststststststststststststststs](../../mfc/reference/cwnd-class.md#postmessage)

##  <a name="removecommandhandler"></a>  ICommandSource::RemoveCommandHandler

명령 소스 개체에서 명령 처리기를 제거 합니다.

```
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>매개 변수

*cmdID*<br/>
명령 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 명령 소스 개체에서 *cmdID* 에 매핑된 명령 처리기를 제거 합니다.

##  <a name="removecommandrangehandler"></a>  ICommandSource::RemoveCommandRangeHandler

명령 소스 개체에서 명령 처리기 그룹을 제거 합니다.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>매개 변수

*cmdIDMin*<br/>
명령 ID 범위의 시작 인덱스입니다.

*cmdIDMax*<br/>
명령 ID 범위의 끝 인덱스입니다.

### <a name="remarks"></a>설명

이 메서드는 명령 원본 개체에서 *cmdIDMin* 및 *cmdIDMax*로 지정 된 명령 id에 매핑된 메시지 처리기 그룹을 제거 합니다.

##  <a name="removecommandrangeuihandler"></a>  ICommandSource::RemoveCommandRangeUIHandler

명령 원본 개체에서 사용자 인터페이스 명령 메시지 처리기 그룹을 제거 합니다.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>매개 변수

*cmdIDMin*<br/>
명령 ID 범위의 시작 인덱스입니다.

*cmdIDMax*<br/>
명령 ID 범위의 끝 인덱스입니다.

### <a name="remarks"></a>설명

이 메서드는 명령 원본 개체에서 *cmdIDMin* 및 *cmdIDMax*로 지정 된 명령 id에 매핑된 사용자 인터페이스 명령 메시지 처리기 그룹을 제거 합니다.

##  <a name="removecommanduihandler"></a>  ICommandSource::RemoveCommandUIHandler

명령 소스 개체에서 사용자 인터페이스 명령 메시지 처리기를 제거 합니다.

```
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>매개 변수

*cmdID*<br/>
명령 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 명령 소스 개체에서 *cmdID* 에 매핑된 사용자 인터페이스 명령 메시지 처리기를 제거 합니다.

##  <a name="sendcommand"></a>  ICommandSource::SendCommand

메시지를 전송 하 고가 반환 되기 전에 처리 될 때까지 기다립니다.

```
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>매개 변수

*command*<br/>
보낼 메시지의 명령 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 *명령*에 지정 된 ID에 매핑된 메시지를 동기적으로 보냅니다. [CWnd:: SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) 를 호출 하 여 창의 메시지 큐에 메시지를 저장 하 고 해당 창 프로시저에서 반환 하기 전에 메시지를 처리할 때까지 대기 합니다.

##  <a name="icommandtarget_interface"></a>ICommandTarget 인터페이스

명령 소스 개체에서 명령을 수신 하는 인터페이스를 사용 하 여 사용자 정의 컨트롤을 제공 합니다.

```
interface class ICommandTarget
```

### <a name="remarks"></a>설명

MFC 뷰에서 사용자 정의 컨트롤을 호스트 하는 경우 [CWinFormsView](../../mfc/reference/cwinformsview-class.md) 는 명령을 라우팅하고 사용자 정의 컨트롤에 명령 UI 메시지를 업데이트 하 여 mfc 명령을 처리할 수 있도록 합니다 (예: 프레임 메뉴 항목 및 도구 모음 단추). 을 구현 `ICommandTarget`하 여 사용자 정의 컨트롤에 개체에 대 한 참조를 제공 합니다.

[방법: 를 사용](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) `ICommandTarget`하는 방법에 대 한 예제를 보려면 Windows Forms 컨트롤에 명령 라우팅을 추가 합니다.

Windows Forms 사용에 대 한 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../../dotnet/using-a-windows-form-user-control-in-mfc.md)을 참조 하세요.

##  <a name="initialize"></a>  ICommandTarget::Initialize

명령 대상 개체를 초기화 합니다.

```
void Initialize(ICommandSource^ cmdSource);
```

### <a name="parameters"></a>매개 변수

*cmdSource*<br/>
명령 소스 개체에 대 한 핸들입니다.

### <a name="remarks"></a>설명

MFC 뷰에서 사용자 정의 컨트롤을 호스트 하는 경우 [CWinFormsView](../../mfc/reference/cwinformsview-class.md) 는 명령을 라우팅하고 사용자 정의 컨트롤에 명령 UI 메시지를 업데이트 하 여 mfc 명령을 처리할 수 있게 합니다.

이 메서드는 명령 대상 개체를 초기화 하 고이를 지정 된 명령 소스 개체 *Cmdsource*에 연결 합니다. 사용자 정의 컨트롤 클래스 구현에서 호출 해야 합니다. 초기화 시에는 `Initialize` 구현에서 [ICommandSource:: addcommandhandler](../../mfc/reference/icommandsource-interface.md) 를 호출 하 여 명령 소스 개체에 명령 처리기를 등록 해야 합니다. [방법: 을 사용](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) `Initialize` 하 여이 작업을 수행 하는 방법에 대 한 예제를 보려면 Windows Forms 컨트롤에 명령 라우팅을 추가 합니다.

##  <a name="icommandui_interface"></a>ICommandUI 인터페이스

사용자 인터페이스 명령을 관리 합니다.

```
interface class ICommandUI
```

### <a name="remarks"></a>설명

이 인터페이스는 사용자 인터페이스 명령을 관리 하는 메서드와 속성을 제공 합니다. `ICommandUI`는 .net 구성 요소와 상호 운용 되 `ICommandUI` 는 MFC 응용 프로그램에 사용 된다는 점을 제외 하 고는 [CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)와 유사 합니다.

`ICommandUI`는 파생 클래스의 `ON_UPDATE_COMMAND_UI` 처리기 내에서 사용 됩니다. 응용 프로그램의 사용자가 메뉴를 활성화 (선택 또는 클릭) 하면 각 메뉴 항목이 사용 또는 사용 안 함으로 표시 됩니다. 각 메뉴 명령의 대상은 처리기를 `ON_UPDATE_COMMAND_UI` 구현 하 여이 정보를 제공 합니다. 응용 프로그램의 각 명령 사용자 인터페이스 개체에 대해 [클래스 마법사](mfc-class-wizard.md) 또는 **속성** 창 ( **클래스 뷰**)을 사용 하 여 각 처리기에 대 한 메시지 맵 항목 및 함수 프로토타입을 만듭니다.

`ICommandUI` 인터페이스를 명령 라우팅 [에 사용 하는 방법에 대 한 자세한 내용은 방법: Windows Forms 컨트롤](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)에 명령 라우팅을 추가 합니다.

Windows Forms 사용에 대 한 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../../dotnet/using-a-windows-form-user-control-in-mfc.md)을 참조 하세요.

MFC에서 사용자 인터페이스 명령을 관리 하는 방법에 대 한 자세한 내용은 [CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)를 참조 하세요.

##  <a name="check"></a>ICommandUI:: Check

이 명령에 대 한 사용자 인터페이스 항목을 적절 한 검사 상태로 설정 합니다.

```
property UICheckState Check;
```

### <a name="remarks"></a>설명

이 속성은이 명령에 대 한 사용자 인터페이스 항목을 적절 한 검사 상태로 설정 합니다. 다음 `Check` 값으로 설정 합니다.

|용어|정의|
|----------|----------------|
|0|체크 해제|
|1|확인|
|2|비활성화 설정|

##  <a name="continuerouting"></a>  ICommandUI::ContinueRouting

현재 메시지를 처리기 체인으로 계속 라우팅하는 명령 라우팅 메커니즘에 지시 합니다.

```
void ContinueRouting();
```

### <a name="remarks"></a>설명

FALSE를 반환 하는 [ON_COMMAND_EX](message-map-macros-mfc.md#on_command_ex) 처리기와 함께 사용 해야 하는 고급 멤버 함수입니다. 자세한 내용은 기술 참고 [TN006를 참조 하세요. 메시지 맵](../../mfc/tn006-message-maps.md).

##  <a name="enabled"></a>ICommandUI:: Enabled

이 명령에 대 한 사용자 인터페이스 항목을 사용 하거나 사용 하지 않도록 설정 합니다.

```
property bool Enabled;
```

### <a name="remarks"></a>설명

이 속성은이 명령에 대 한 사용자 인터페이스 항목을 사용 하거나 사용 하지 않도록 설정 합니다. 항목 `Enabled` 을 사용 하도록 설정 하려면 TRUE로 설정 하 고, 그렇지 않으면 FALSE로 설정 합니다.

##  <a name="id"></a>  ICommandUI::ID

`ICommandUI` 개체가 나타내는 사용자 인터페이스 개체의 ID를 가져옵니다.

```
property unsigned int ID;
```

### <a name="remarks"></a>설명

이 속성은 메뉴 항목의 ID (핸들), 도구 모음 단추 또는 `ICommandUI` 개체가 나타내는 기타 사용자 인터페이스 개체를 가져옵니다.

##  <a name="index"></a>  ICommandUI::Index

`ICommandUI` 개체가 나타내는 사용자 인터페이스 개체의 인덱스를 가져옵니다.

```
property unsigned int Index;
```

### <a name="remarks"></a>설명

이 속성은 메뉴 항목의 인덱스 (핸들), 도구 모음 단추 또는 `ICommandUI` 개체가 나타내는 기타 사용자 인터페이스 개체를 가져옵니다.

##  <a name="radio"></a>  ICommandUI::Radio

이 명령에 대 한 사용자 인터페이스 항목을 적절 한 검사 상태로 설정 합니다.

```
property bool Radio;
```

### <a name="remarks"></a>설명

이 속성은이 명령에 대 한 사용자 인터페이스 항목을 적절 한 검사 상태로 설정 합니다. 항목 `Radio` 을 사용 하려면 TRUE로 설정 하 고 그렇지 않으면 FALSE로 설정 합니다.

##  <a name="text"></a>  ICommandUI::Text

이 명령에 대 한 사용자 인터페이스 항목의 텍스트를 설정 합니다.

```
property String^ Text;
```

### <a name="remarks"></a>설명

이 속성은이 명령에 대 한 사용자 인터페이스 항목의 텍스트를 설정 합니다. 텍스트 `Text` 문자열 핸들로 설정 합니다.

##  <a name="iview_interface"></a>IView 인터페이스

[CWinFormsView](../../mfc/reference/cwinformsview-class.md) 에서 관리 되는 컨트롤에 뷰 알림을 보내는 데 사용 하는 여러 메서드를 구현 합니다.

```
interface class IView
```

### <a name="remarks"></a>설명

`IView`는를 사용 하 `CWinFormsView` 여 호스트 된 관리 되는 컨트롤에 일반적인 뷰 알림을 전달 하는 여러 메서드를 구현 합니다. 이는 [Oninitialupdate](../../mfc/reference/iview-interface.md), [OnUpdate](../../mfc/reference/iview-interface.md) 및 [oninitialupdate](../../mfc/reference/iview-interface.md)입니다.

`IView`는 [CView](../../mfc/reference/cview-class.md)와 유사 하지만 관리 되는 뷰 및 컨트롤 에서만 사용 됩니다.

Windows Forms 사용에 대 한 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤 사용](../../dotnet/using-a-windows-form-user-control-in-mfc.md)을 참조 하세요.

##  <a name="onactivateview"></a>  IView::OnActivateView

뷰가 활성화 또는 비활성화 될 때 MFC에서 호출 됩니다.

```
void OnActivateView(bool activate);
```

### <a name="parameters"></a>매개 변수

*activate*<br/>
뷰가 활성화 또는 비활성화 되는지 여부를 나타냅니다.

##  <a name="oninitialupdate"></a>  IView::OnInitialUpdate

뷰가 문서에 처음 연결 된 후 뷰가 처음 표시 되기 전에 프레임 워크에서 호출 됩니다.

```
void OnInitialUpdate();
```

##  <a name="onupdate"></a>  IView::OnUpdate

뷰의 문서가 수정 된 후에 MFC에서 호출 됩니다.

```
void OnUpdate();
```

### <a name="remarks"></a>설명

이 함수를 사용 하면 뷰가 수정을 반영 하도록 표시를 업데이트할 수 있습니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 수집](../../overview/visual-cpp-samples.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
