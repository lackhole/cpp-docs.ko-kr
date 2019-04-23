---
title: CMFCImageEditorDialog 클래스
ms.date: 11/19/2018
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
helpviewer_keywords:
- CMFCImageEditorDialog [MFC], CMFCImageEditorDialog
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
ms.openlocfilehash: 97f16fa00b2e90fd9c43bf9b6792b4eafe7d7b88
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58780447"
---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorDialog 클래스

`CMFCImageEditorDialog` 클래스는 이미지 편집기 대화 상자를 지원 합니다.

## <a name="syntax"></a>구문

```
class CMFCImageEditorDialog : public CDialogEx
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|`CMFCImageEditorDialog` 개체를 생성합니다.|

## <a name="remarks"></a>설명

`CMFCImageEditorDialog` 클래스를 포함 하는 대화 상자를 제공 합니다.

- 그림 영역을 사용 하면 개별 픽셀 이미지를 수정입니다.

- 그리기 도구를 그림 영역에서 픽셀을 수정 합니다.

- 그리기 도구에서 사용 되는 색을 지정할 색상표입니다.

- 편집의 영향을 표시 하는 미리 보기 영역입니다.

다음 그림에서는 이미지 편집기 대화 상자를 보여 줍니다.

![CMFCImageEditorDialog 대화 상자](../../mfc/reference/media/imageedit.png "CMFCImageEditorDialog 대화 상자")

사용 하는 한 가지 방법은 `CMFCImageEditorDialog` 개체가 전달는 `CBitmap` 이미지를 편집할 수 있습니다. 영역 편집 이미지 크기가 제한 논리 픽셀 크기 영역에 맞게 조정 됩니다 때문 큰 이미지를 만들지 마십시오. 호출 된 `DoModal` 모달 대화 상자를 시작 하는 방법입니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afximageeditordialog.h

##  <a name="cmfcimageeditordialog"></a>  CMFCImageEditorDialog::CMFCImageEditorDialog

`CMFCImageEditorDialog` 개체를 생성합니다.

```
CMFCImageEditorDialog(
    CBitmap* pBitmap,
    CWnd* pParent=NULL,
    int nBitsPixel=-1);
```

### <a name="parameters"></a>매개 변수

*pBitmap*<br/>
이미지에 대 한 포인터입니다.

*pParent*<br/>
현재 이미지 편집기 대화 상자의 부모 창에 대 한 포인터입니다.

*nBitsPixel*<br/>
색 농도 라고도 하는 단일 픽셀의 색을 나타내는 데 사용 되는 비트 수입니다.  경우는 *nBitsPixel* 매개 변수가-1 이면 색 농도 지정 된 이미지에서 파생 되는 *pBitmap* 매개 변수입니다. 기본값은 -1입니다.

### <a name="return-value"></a>반환 값

이미지를 수정 하려면에 대 한 이미지 포인터를 전달 합니다 `CMFCImageEditorDialog` 생성자입니다. 다음 호출을 `DoModal` 을 모달 대화 상자를 엽니다. 경우는 `DoModal` 새 이미지를 포함 하는 비트맵 메서드가 반환 합니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

다음 예제에서는의 개체를 생성 하는 방법에 설명 합니다 `CMFCImageEditorDialog` 클래스입니다. 이 예제는의 일부를 [새 컨트롤 샘플](../../overview/visual-cpp-samples.md)합니다.

[!code-cpp[NVC_MFC_NewControls#8](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]
[!code-cpp[NVC_MFC_NewControls#40](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar 클래스](../../mfc/reference/cmfctoolbar-class.md)
