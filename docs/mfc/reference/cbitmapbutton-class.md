---
title: CBitmapButton 클래스
ms.date: 11/04/2016
f1_keywords:
- CBitmapButton
- AFXEXT/CBitmapButton
- AFXEXT/CBitmapButton::CBitmapButton
- AFXEXT/CBitmapButton::AutoLoad
- AFXEXT/CBitmapButton::LoadBitmaps
- AFXEXT/CBitmapButton::SizeToContent
helpviewer_keywords:
- CBitmapButton [MFC], CBitmapButton
- CBitmapButton [MFC], AutoLoad
- CBitmapButton [MFC], LoadBitmaps
- CBitmapButton [MFC], SizeToContent
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
ms.openlocfilehash: 45e0214cafb80c3e00a7e888a3170040f46113f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388464"
---
# <a name="cbitmapbutton-class"></a>CBitmapButton 클래스

텍스트가 아닌 비트맵 이미지로 레이블이 표시된 누름 단추 컨트롤을 만듭니다.

## <a name="syntax"></a>구문

```
class CBitmapButton : public CButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|`CBitmapButton` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CBitmapButton::AutoLoad](#autoload)|개체를 사용 하 여 대화 상자에서 단추를 연결 합니다 `CBitmapButton` 클래스 이름으로는 bitmap(s)를 로드 하 고 비트맵에 맞게 단추 크기를 조정 합니다.|
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|응용 프로그램의 리소스 파일에서 하나 이상의 명명 된 비트맵 리소스를 로드 하 고 비트맵 개체에 연결 하 여 개체를 초기화 합니다.|
|[CBitmapButton::SizeToContent](#sizetocontent)|비트맵에 맞게 단추 크기를 조정 합니다.|

## <a name="remarks"></a>설명

`CBitmapButton` 개체 단추 가정할 수 여러 상태에 대 한 이미지를 포함 하는 최대 4 개의 비트맵 포함: 최신 (또는 일반) 아래쪽 (또는 선택한) 치중 하 고 사용 하지 않도록 설정 합니다. 첫 번째 비트맵에만 필수 사항입니다. 나머지는 선택 사항입니다.

비트맵 단추 이미지는 이미지 자체 뿐만 아니라 이미지 주위에 테두리가 포함 됩니다. 테두리는 일반적으로 단추의 상태를 보여 주는 파트를 재생 합니다. 예를 들어 포커스가 있는 상태에 대 한 비트맵은 일반적으로 같은 테두리 또는 있는 굵은 실선 테두리에는 파선된 사각형 inset 했지만 최신 상태입니다. 비트맵은 비활성화 된 일반적으로 상태에 대 한 유사 하나에 대 한 최신 상태 이지만 (예: 흐리게 또는 회색으로 표시 메뉴 선택) 낮은 대비 합니다.

이러한 비트맵 임의 크기 일 수 있지만 동일한 크기의 비트맵 최신 상태에 대 한 것 처럼 처리 됩니다 모든.

다양 한 응용 프로그램은 비트맵 이미지의 다양 한 조합을 요구 합니다.

|위로|아래로|포커스 있음|사용 안 함|애플리케이션|
|--------|----------|-------------|--------------|-----------------|
|×||||Bitmap|
|×|×|||WS_TABSTOP 스타일 없이 단추|
|×|×|×|×|모든 상태를 사용 하 여 대화 상자 단추|
|×|×|×||WS_TABSTOP 스타일으로 대화 상자 단추|

비트맵 단추 컨트롤을 만들 때 소유자가 그린 단추를 지정 하려면 BS_OWNERDRAW 스타일을 설정 합니다. 이렇게 하면 단추의; WM_MEASUREITEM 및 WM_DRAWITEM 메시지를 보내는 Windows 프레임 워크는 이러한 메시지를 처리 하 고를 단추의 모양을 관리 합니다.

### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>창의 클라이언트 영역에서 비트맵 단추 컨트롤을 만들려면

1. 단추에 대해 1 ~ 4 개의 비트맵 이미지를 만듭니다.

1. 생성 된 [CBitmapButton](#cbitmapbutton) 개체입니다.

1. 호출 된 [만들기](../../mfc/reference/cbutton-class.md#create) Windows 단추 컨트롤을 만들고 연결 하는 함수는 `CBitmapButton` 개체입니다.

1. 호출 된 [LoadBitmaps](#loadbitmaps) 멤버 함수는 비트맵 단추 생성 된 후 비트맵 리소스를 로드할 수 있습니다.

### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>대화 상자에서 비트맵 단추 컨트롤을 포함 하려면

1. 단추에 대해 1 ~ 4 개의 비트맵 이미지를 만듭니다.

1. 소유자 그리기 단추 비트맵 단추 원하는 위치를 사용 하 여 대화 상자 템플릿을 만듭니다. 템플릿에서 단추의 크기 중요 하지 않습니다.

1. 단추의 캡션은 "MYIMAGE"와 같은 값으로 설정 하 고 IDC_MYIMAGE 같은 단추에 대 한 기호를 정의 합니다.

1. 응용 프로그램의 리소스 스크립트에 특정 문자 "U", "D", "F"를 추가 하 여 생성 된 ID를 단추에 대해 생성 된 이미지의 각 또는 "X" (예, 아래로 치중 하 고 사용 하지 않도록 설정)에 단추 캡션에 사용 되는 문자열을 3 단계. 단추 캡션을 "MYIMAGE"에 대 한 예를 들어, Id 것 "MYIMAGEU", "MYIMAGED", "MYIMAGEF," 및 "MYIMAGEX." 있습니다 **해야** 큰따옴표 안의 비트맵의 ID를 지정 합니다. 그렇지 않은 경우 리소스 편집기에서 리소스를 정수를 할당 하 고 이미지를 로드할 때 MFC 실패 합니다.

1. 응용 프로그램의 대화 상자 클래스에서 (에서 파생 된 `CDialog`), 추가 `CBitmapButton` 멤버 개체입니다.

1. 에 `CDialog` 개체의 [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog) 루틴을 호출 합니다 `CBitmapButton` 개체의 [AutoLoad](#autoload) 함수를 단추의 컨트롤 ID를 매개 변수로 사용 하 여 및 `CDialog` 개체의 **이** 포인터입니다.

BN_CLICKED, 예: Windows 알림 메시지를 처리 하려는 경우 부모 비트맵 단추 컨트롤에서 보냅니다 (일반적으로 클래스에서 파생 `CDialog`)를 추가할는 `CDialog`-파생 된 개체는 메시지 맵 항목 및 메시지 처리기 멤버 각 메시지에 대 한 함수입니다. 보낸 알림의 `CBitmapButton` 개체에서 보낸 것과 동일를 [CButton](../../mfc/reference/cbutton-class.md) 개체입니다.

클래스 [CToolBar](../../mfc/reference/ctoolbar-class.md) 비트맵 단추는 다른 방식을 사용 합니다.

에 대 한 자세한 `CBitmapButton`를 참조 하세요 [컨트롤](../../mfc/controls-mfc.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CBitmapButton`

## <a name="requirements"></a>요구 사항

**헤더:** afxext.h

##  <a name="autoload"></a>  CBitmapButton::AutoLoad

개체를 사용 하 여 대화 상자에서 단추를 연결 합니다 `CBitmapButton` 클래스 이름으로는 bitmap(s)를 로드 하 고 비트맵에 맞게 단추 크기를 조정 합니다.

```
BOOL AutoLoad(
    UINT nID,
    CWnd* pParent);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
단추의 컨트롤 id입니다.

*pParent*<br/>
단추를 소유 하는 개체에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

사용 된 `AutoLoad` 비트맵 단추와 대화 상자에서 소유자 그리기 단추를 초기화 하는 함수입니다. 이 함수를 사용 하는 지침에 대 한 설명에는 `CBitmapButton` 클래스입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]

##  <a name="cbitmapbutton"></a>  CBitmapButton::CBitmapButton

`CBitmapButton` 개체를 만듭니다.

```
CBitmapButton();
```

### <a name="remarks"></a>설명

만든 후는 C++ `CBitmapButton` 개체, 호출 [CButton::Create](../../mfc/reference/cbutton-class.md#create) Windows 단추 컨트롤을 만들고 연결 하는 `CBitmapButton` 개체입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]

##  <a name="loadbitmaps"></a>  CBitmapButton::LoadBitmaps

사용할 수 없는 경우 또는 리소스 이름 또는 ID 번호로 식별 하는 비트맵 이미지를 로드 하려는 경우이 함수를 사용 합니다 `AutoLoad` 예를 들어 대화 상자의 포함 되지 않은 비트맵 단추 만들어지기 때문에 작동 합니다.

```
BOOL LoadBitmaps(
    LPCTSTR lpszBitmapResource,
    LPCTSTR lpszBitmapResourceSel = NULL,
    LPCTSTR lpszBitmapResourceFocus = NULL,
    LPCTSTR lpszBitmapResourceDisabled = NULL);

BOOL LoadBitmaps(
    UINT nIDBitmapResource,
    UINT nIDBitmapResourceSel = 0,
    UINT nIDBitmapResourceFocus = 0,
    UINT nIDBitmapResourceDisabled = 0);
```

### <a name="parameters"></a>매개 변수

*lpszBitmapResource*<br/>
비트맵 단추의 normal 또는 "up" 상태 비트맵의 이름이 포함 된 null로 끝나는 문자열을 가리킵니다. 필수.

*lpszBitmapResourceSel*<br/>
비트맵 단추의 선택에 대 한 비트맵의 이름을 포함 하는 null로 끝나는 문자열 또는 "down" 상태를 가리킵니다. NULL 일 수 있습니다.

*lpszBitmapResourceFocus*<br/>
상태를 집중 하는 비트맵 단추에 대 한 비트맵의 이름이 포함 된 null로 끝나는 문자열을 가리킵니다. NULL 일 수 있습니다.

*lpszBitmapResourceDisabled*<br/>
비트맵 단추의 사용 안 함된 상태에 대 한 비트맵의 이름이 포함 된 null로 끝나는 문자열을 가리킵니다. NULL 일 수 있습니다.

*nIDBitmapResource*<br/>
비트맵 단추의 normal 또는 "up" 상태에서 비트맵 리소스의 리소스 ID 번호를 지정합니다. 필수.

*nIDBitmapResourceSel*<br/>
비트맵 단추를 선택 하거나 "중단" 상태로 비트맵 리소스의 리소스 ID 번호를 지정 합니다. 0 일 수 있습니다.

*nIDBitmapResourceFocus*<br/>
비트맵 단추의 포커스가 있는 상태에 대 한 비트맵 리소스의 리소스 ID 번호를 지정 합니다. 0 일 수 있습니다.

*nIDBitmapResourceDisabled*<br/>
비트맵 단추의 사용 안 함된 상태에 대 한 비트맵 리소스의 리소스 ID 번호를 지정 합니다. 0 일 수 있습니다.

### <a name="return-value"></a>반환 값

성공하면 0이 아니고, 그렇지 않으면 0입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]

##  <a name="sizetocontent"></a>  CBitmapButton::SizeToContent

비트맵의 크기는 비트맵 단추 크기를 조정 하려면이 함수를 호출 합니다.

```
void SizeToContent();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[CButton 클래스](../../mfc/reference/cbutton-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
