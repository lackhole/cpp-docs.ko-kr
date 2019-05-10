---
title: CSingleDocTemplate 클래스
ms.date: 11/04/2016
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
ms.openlocfilehash: 4d1361734f38d903e2171839b95888863126974a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62324189"
---
# <a name="csingledoctemplate-class"></a>CSingleDocTemplate 클래스

SDI(단일 문서 인터페이스)를 구현하는 문서 템플릿을 정의합니다.

## <a name="syntax"></a>구문

```
class CSingleDocTemplate : public CDocTemplate
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|`CSingleDocTemplate` 개체를 생성합니다.|

## <a name="remarks"></a>설명

SDI 응용 프로그램을 문서에 표시할 주 프레임 창 사용 한 번에 하나의 문서만 열 수 있습니다.

문서 서식 파일을 세 가지 유형의 클래스 간의 관계를 정의 합니다.

- 문서 클래스에서 파생 되는 `CDocument`합니다.

- 위에 나열 된 문서 클래스에서 데이터를 표시 하는 view 클래스입니다. 이 클래스에서 파생 될 수 있습니다 `CView`, `CScrollView`를 `CFormView`, 또는 `CEditView`합니다. (사용할 수도 있습니다 `CEditView` 직접.)

- 프레임 창 클래스-뷰가 포함 합니다. SDI 문서 템플릿의 경우에서이 클래스를 파생할 수 있습니다 `CFrameWnd`경우에 기본 동작을 사용자 지정할 필요가 하지 않으면 프레임 창에서 사용할 수 있습니다 `CFrameWnd` 고유한 클래스를 파생 하지 않고 직접.

SDI 응용 프로그램은 일반적으로 한 가지 유형의 문서를 지원 하므로 하나 뿐 이기 `CSingleDocTemplate` 개체입니다. 한 번에 하나의 문서만 열 수 있습니다.

멤버 함수를 호출할 필요가 없습니다 `CSingleDocTemplate` 생성자를 제외 하 고 있습니다. 프레임 워크 처리 `CSingleDocTemplate` 내부적으로 개체입니다.

사용 하 여 대 한 자세한 내용은 `CSingleDocTemplate`를 참조 하세요 [문서 템플릿 및 문서/뷰 만들기 프로세스](../../mfc/document-templates-and-the-document-view-creation-process.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CSingleDocTemplate`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="csingledoctemplate"></a>  CSingleDocTemplate::CSingleDocTemplate

`CSingleDocTemplate` 개체를 생성합니다.

```
CSingleDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>매개 변수

*nIDResource*<br/>
문서 형식을 사용 하 여 사용 하는 리소스의 ID를 지정 합니다. 이 메뉴, 아이콘, 액셀러레이터 키 테이블 및 문자열 리소스만 포함 될 수 있습니다.

하지만 문자열 리소스를 '\n' 문자로 구분 되는 최대 7 개의 부분으로 구성 됩니다 ('\n' 문자 자리 표시자로 필요한 부분 문자열이 포함 되어 있지 않으면; 후행 '\n' 문자가 필요 하지 않습니다); 이러한 부분 문자열에는 문서 유형에 대해 설명합니다. 부분 문자열에 대 한 정보를 참조 하세요 [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)합니다. 이 문자열 리소스는 응용 프로그램의 리소스 파일에 있습니다. 예를 들어:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"
END
```

문자열 편집기;를 사용 하 여이 문자열을 편집할 수 있습니다. 전체 문자열을 개별 항목 7 아니라 문자열 편집기에서 단일 항목으로 나타납니다.

이러한 리소스 유형에 대 한 자세한 내용은 참조는 [문자열 편집기](../../windows/string-editor.md)합니다.

*pDocClass*<br/>
가리키는 `CRuntimeClass` 문서 클래스의 개체입니다. 이 클래스는를 `CDocument`-문서를 나타내기 위해 정의한 클래스를 파생 합니다.

*pFrameClass*<br/>
가리키는 `CRuntimeClass` 프레임 창 클래스의 개체입니다. 이 클래스 수를 `CFrameWnd`-클래스를 파생 되거나 수 `CFrameWnd` 주 프레임 창에 대 한 기본 동작을 원하는 경우 자체입니다.

*pViewClass*<br/>
가리키는 `CRuntimeClass` 뷰 클래스의 개체입니다. 이 클래스는를 `CView`-문서 표시를 정의 하는 클래스를 파생 합니다.

### <a name="remarks"></a>설명

동적으로 할당을 `CSingleDocTemplate` 개체를 전달할 `CWinApp::AddDocTemplate` 에서 `InitInstance` 응용 프로그램 클래스의 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]

[!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]

## <a name="see-also"></a>참고자료

[MFC 샘플 DOCKTOOL](../../overview/visual-cpp-samples.md)<br/>
[CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[CDocument 클래스](../../mfc/reference/cdocument-class.md)<br/>
[CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)<br/>
[CMultiDocTemplate 클래스](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[CView 클래스](../../mfc/reference/cview-class.md)<br/>
[CWinApp 클래스](../../mfc/reference/cwinapp-class.md)
