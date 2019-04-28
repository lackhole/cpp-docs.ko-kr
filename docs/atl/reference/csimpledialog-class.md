---
title: CSimpleDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
ms.openlocfilehash: b0790d9c29b50b1ac454815cd2189e0efb31b9ef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278061"
---
# <a name="csimpledialog-class"></a>CSimpleDialog 클래스

이 클래스는 기본 모달 대화 상자를 구현합니다.

## <a name="syntax"></a>구문

```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>
class CSimpleDialog : public CDialogImplBase
```

#### <a name="parameters"></a>매개 변수

*t_wDlgTemplateID*

대화 상자 템플릿 리소스의 리소스 ID입니다.

*t_bCenter*<br/>
대화 상자 개체에서 소유자 창의 가운데에 맞춰야 하는 경우 TRUE 그렇지 않으면 FALSE입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CSimpleDialog::DoModal](#domodal)|모달 대화 상자를 만듭니다.|

## <a name="remarks"></a>설명

기본 기능을 사용 하 여 모달 대화 상자를 구현합니다. `CSimpleDialog` Windows 공용 컨트롤만 지원을 제공합니다. 를 만들고 모달 대화 상자를 표시 하려면 대화 상자에 대 한 기존 리소스 템플릿의 이름을 제공 하는이 클래스의 인스턴스를 만듭니다. 미리 정의 된 값 (예: IDOK 또는 IDCANCEL)를 사용 하 여 모든 컨트롤을 마우스 오른쪽 단추로 클릭할 때 대화 상자 개체를 닫습니다.

`CSimpleDialog` 모달 대화 상자만 만들 수 있습니다. `CSimpleDialog` 기본 메시지 맵을 사용해 메시지를 해당 처리기를 직접을 대화 상자 프로시저를 제공 합니다.

참조 [대화 상자 구현](../../atl/implementing-a-dialog-box.md) 자세한 내용은 합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CDialogImplBase`

`CSimpleDialog`

## <a name="requirements"></a>요구 사항

**헤더:** atlwin.h

##  <a name="domodal"></a>  CSimpleDialog::DoModal

모달 대화 상자를 호출 하 고 수행 하는 경우 대화 상자 결과 반환 합니다.

```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```

### <a name="parameters"></a>매개 변수

*hWndParent*<br/>
대화 상자의 부모 핸들입니다. 없는 값을 제공 하는 경우 부모는 현재 활성 창으로 설정 됩니다.

### <a name="return-value"></a>반환 값

성공 하면 반환 값은 대화 상자를 해제 하는 컨트롤의 리소스 ID입니다.

함수가 실패 한 경우 반환 값은-1입니다. 확장 오류 정보를 가져오려면 `GetLastError`를 호출합니다.

### <a name="remarks"></a>설명

이 메서드는 대화 상자가 활성화 되는 동안 모든 사용자 상호 작용을 처리 합니다. 이 대화 상자 모달; 사용 즉, 사용자가 대화 상자를 닫을 때까지 다른 windows 상호 작용할 수 없습니다.

## <a name="see-also"></a>참고자료

[클래스 개요](../../atl/atl-class-overview.md)
