---
title: IView 인터페이스
ms.date: 11/04/2016
f1_keywords:
- IView
- AFXWINFORMS/IView
- AFXWINFORMS/IView::OnActivateView
- AFXWINFORMS/IView::OnInitialUpdate
- AFXWINFORMS/IView::OnUpdate
helpviewer_keywords:
- views [MFC]
- IView class [MFC]
- views [MFC], classes
ms.assetid: 9321f299-486e-4551-bee9-d2c4a7b91548
ms.openlocfilehash: 22e08a70ff4cc742406a1489899c0ba1df7eb664
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321951"
---
# <a name="iview-interface"></a>IView 인터페이스

몇 가지 메서드를 구현 하는 [CWinFormsView](../../mfc/reference/cwinformsview-class.md) 사용 하 여 관리 되는 컨트롤에 알림을 보냅니다.

## <a name="syntax"></a>구문

```
interface class IView
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[IView::OnActivateView](#onactivateview)|보기 활성화 또는 비활성화 하는 경우 MFC에서 호출 됩니다.|
|[IView::OnInitialUpdate](#oninitialupdate)|전에 호출 됩니다 프레임 워크에서 뷰를 먼저 문서에 연결한 후 뷰 처음에 표시 됩니다.|
|[IView::OnUpdate](#onupdate)|문서 보기의; 수정한 후에 MFC를 호출한 이 함수는 수정 내용을 반영 하도록 해당 디스플레이를 업데이트 보기를 허용 합니다.|

## <a name="remarks"></a>설명

`IView` 몇 가지 메서드를 구현 하는 `CWinFormsView` 일반적인 뷰 알림을 관리 되는 호스트 된 컨트롤에 전달할를 사용 하 여 합니다. 이들은 [OnInitialUpdate](#oninitialupdate)를 [OnUpdate](#onupdate) 하 고 [OnActivateView](#onactivateview)합니다.

`IView` 비슷합니다 [CView](../../mfc/reference/cview-class.md), 있지만 관리 되는 보기와 컨트롤에만 사용 됩니다.

Windows Forms를 사용 하 여 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)입니다.

## <a name="requirements"></a>요구 사항

헤더: afxwinforms.h (atlmfc\lib\mfcmifc80.dll 어셈블리에에서 정의 됨)

## <a name="onactivateview"></a> IView::OnActivateView

보기 활성화 또는 비활성화 하는 경우 MFC에서 호출 됩니다.
```
void OnActivateView(bool activate);
```

## <a name="parameters"></a>매개 변수

*activate*<br/>
보기를 새로 여부를 나타내는 활성화 또는 비활성화 합니다.

## <a name="oninitialupdate"></a> IView::OnInitialUpdate

전에 호출 됩니다 프레임 워크에서 뷰를 먼저 문서에 연결한 후 뷰 처음에 표시 됩니다.
```
void OnInitialUpdate();
```

## <a name="onupdate"></a> IView::OnUpdate

문서 보기의 수정 된 후 MFC에서 호출 됩니다.
```
void OnUpdate();
```

## <a name="remarks"></a>설명

이 함수는 수정 내용을 반영 하도록 해당 디스플레이를 업데이트 보기를 허용 합니다.

## <a name="see-also"></a>참고자료

[CWinFormsView 클래스](../../mfc/reference/cwinformsview-class.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)
