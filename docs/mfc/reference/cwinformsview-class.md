---
title: CWinFormsView 클래스
ms.date: 11/04/2016
f1_keywords:
- CWinFormsView
- AFXWINFORMS/CWinFormsView
- AFXWINFORMS/CWinFormsView::CWinFormsView
- AFXWINFORMS/CWinFormsView::GetControl
helpviewer_keywords:
- CWinFormsView [MFC], CWinFormsView
- CWinFormsView [MFC], GetControl
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
ms.openlocfilehash: f4a5e6b88527dad8606092ccebd4899bba5181f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323309"
---
# <a name="cwinformsview-class"></a>CWinFormsView 클래스

Windows Forms 컨트롤을 MFC 뷰로 호스팅하기 위한 일반 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class CWinFormsView : public CView;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CWinFormsView::CWinFormsView](#cwinformsview)|`CWinFormsView` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CWinFormsView::GetControl](#getcontrol)|Windows Forms 컨트롤에 대 한 포인터를 검색합니다.|

### <a name="public-operators"></a>Public 연산자

|이름||
|----------|-|
|[CWinFormsView::operator 컨트롤 ^](#operator_control)|Windows Forms 컨트롤에 대 한 포인터로 형식을 캐스팅합니다.|

## <a name="remarks"></a>설명

MFC를 사용 하는 `CWinFormsView` 을 MFC 뷰로 내에서.NET Framework Windows Forms 컨트롤을 호스트 하는 클래스입니다. 기본 뷰의 자식 컨트롤과 MFC 뷰로의 전체 클라이언트 영역을 차지 합니다. 결과 비슷합니다는 `CFormView` 보기를 다양 한 폼 기반 보기를 만들 수 있는 런타임 및 Windows Forms 디자이너를 사용할 수 있습니다.

Windows Forms를 사용 하 여 자세한 내용은 [MFC에서 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)입니다.

> [!NOTE]
>  MFC Windows Forms 통합 MFC를 사용 하 여 동적으로 링크 하는 프로젝트 에서만 작동 합니다 (프로젝트의 AFXDLL 정의 되어 있는 경우).

> [!NOTE]
>  CWinFormsView MFC 분할기 창을 지원 하지 않습니다 ( [CSplitterWnd 클래스](../../mfc/reference/csplitterwnd-class.md)). 현재만 Windows Forms 분할자 컨트롤 지원 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxwinforms.h

##  <a name="cwinformsview"></a>  CWinFormsView::CWinFormsView

`CWinFormsView` 개체를 생성합니다.

```
CWinFormsView(System::Type^ pManagedViewType);
```

### <a name="parameters"></a>매개 변수

*pManagedViewType*<br/>
Windows Forms 사용자 정의 컨트롤의 데이터 형식에 대 한 포인터입니다.

### <a name="example"></a>예제

다음 예제에서는 `CUserView` 클래스에서 상속 `CWinFormsView` 유형을 전달 하 고 `UserControl1` 에 `CWinFormsView` 생성자. `UserControl1` ControlLibrary1.dll에서 사용자 지정 컨트롤이입니다.

[!code-cpp[NVC_MFC_Managed#1](../../mfc/reference/codesnippet/cpp/cwinformsview-class_1.h)]

[!code-cpp[NVC_MFC_Managed#2](../../mfc/reference/codesnippet/cpp/cwinformsview-class_2.cpp)]

##  <a name="getcontrol"></a>  CWinFormsView::GetControl

Windows Forms 컨트롤에 대 한 포인터를 검색합니다.

```
System::Windows::Forms::Control^ GetControl() const;
```

### <a name="return-value"></a>반환 값

`System.Windows.Forms.Control` 개체에 대한 포인터입니다.

### <a name="remarks"></a>설명

Windows Forms를 사용 하는 방법의 예제를 참조 하세요 [MFC에서 Windows Form 사용자 정의 컨트롤을 사용 하 여](../../dotnet/using-a-windows-form-user-control-in-mfc.md)입니다.

##  <a name="operator_control"></a>  CWinFormsView::operator Control^

Windows Forms 컨트롤에 대 한 포인터로 형식을 캐스팅합니다.

```
operator System::Windows::Forms::Control^() const;
```

### <a name="remarks"></a>설명

이 연산자를 사용 하면 전달 하는 `CWinFormsView` 뷰 형식의 Windows Forms 컨트롤에 대 한 포인터를 허용 하는 함수를 <xref:System.Windows.Forms.Control>입니다.

### <a name="example"></a>예제

  참조 [CWinFormsView::GetControl](#getcontrol)합니다.

## <a name="see-also"></a>참고자료

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWinFormsControl 클래스](../../mfc/reference/cwinformscontrol-class.md)<br/>
[CWinFormsDialog 클래스](../../mfc/reference/cwinformsdialog-class.md)<br/>
[CFormView 클래스](../../mfc/reference/cformview-class.md)
