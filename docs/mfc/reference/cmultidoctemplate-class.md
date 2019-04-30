---
title: CMultiDocTemplate 클래스
ms.date: 11/04/2016
f1_keywords:
- CMultiDocTemplate
- AFXWIN/CMultiDocTemplate
- AFXWIN/CMultiDocTemplate::CMultiDocTemplate
helpviewer_keywords:
- CMultiDocTemplate [MFC], CMultiDocTemplate
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
ms.openlocfilehash: 5fefe91fa2067831c0263146ff3b2cd143b9c647
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366942"
---
# <a name="cmultidoctemplate-class"></a>CMultiDocTemplate 클래스

MDI(다중 문서 인터페이스)를 구현하는 문서 템플릿을 정의합니다.

## <a name="syntax"></a>구문

```
class CMultiDocTemplate : public CDocTemplate
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CMultiDocTemplate::CMultiDocTemplate](#cmultidoctemplate)|`CMultiDocTemplate` 개체를 생성합니다.|

## <a name="remarks"></a>설명

MDI 응용 프로그램으로 문서를 표시 하는 각 작업 영역 사용자는 0 개 이상의 문서 프레임 창에서 열 수 주 프레임 창을 사용 합니다. 에 대 한 자세한 설명은 MDI 참조 하세요 *소프트웨어 디자인에 대 한 Windows 인터페이스 지침*합니다.

문서 서식 파일을 세 가지 유형의 클래스 간의 관계를 정의합니다.

- 문서 클래스에서 파생 되는 [CDocument](../../mfc/reference/cdocument-class.md)합니다.

- 위에 나열 된 문서 클래스에서 데이터를 표시 하는 view 클래스입니다. 이 클래스에서 파생 될 수 있습니다 [CView](../../mfc/reference/cview-class.md)를 `CScrollView`합니다 `CFormView`, 또는 `CEditView`합니다. (사용할 수도 있습니다 `CEditView` 직접.)

- 프레임 창 클래스-뷰가 포함 합니다. MDI 문서 템플릿의 경우에서이 클래스를 파생할 수 있습니다 `CMDIChildWnd`, 또는 문서 프레임 창 동작을 사용자 지정할 필요가 있는 경우 사용할 수 있습니다 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 고유한 클래스를 파생 하지 않고 직접.

MDI 응용 프로그램에 둘 이상의 유형의 문서를 지원할 수 있습니다 하 고 다른 형식의 문서를 동시에 열 수 있습니다. 응용 프로그램에 지원 되는 각 문서 유형에 대 한 하나 만듭니다. 예를 들어 MDI 응용 프로그램에서 스프레드시트 및 텍스트 문서를 지 원하는 경우 응용 프로그램에는 두 개의 `CMultiDocTemplate` 개체입니다.

응용 프로그램에서는 사용자가 새 문서를 만들면 문서 템플릿을 사용 합니다. 응용 프로그램에서 둘 이상의 형식의 문서를 지 원하는 경우 프레임 워크 문서 템플릿에서 지원 되는 문서 형식 이름을 가져옵니다 및 새 파일 대화 상자에 있는 목록에 표시 합니다. 사용자가 문서 유형을 선택 하 고, 응용 프로그램 문서 클래스 개체, 프레임 창 개체를 뷰 개체를 만들고 후 서로 연결 합니다.

멤버 함수를 호출할 필요가 없습니다 `CMultiDocTemplate` 생성자를 제외 하 고 있습니다. 프레임 워크 처리 `CMultiDocTemplate` 내부적으로 개체입니다.

에 대 한 자세한 `CMultiDocTemplate`를 참조 하세요 [문서 템플릿 및 문서/뷰 만들기 프로세스](../../mfc/document-templates-and-the-document-view-creation-process.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CMultiDocTemplate`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

##  <a name="cmultidoctemplate"></a>  CMultiDocTemplate::CMultiDocTemplate

`CMultiDocTemplate` 개체를 생성합니다.

```
CMultiDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>매개 변수

*nIDResource*<br/>
문서 형식을 사용 하 여 사용 하는 리소스의 ID를 지정 합니다. 이 메뉴, 아이콘, 액셀러레이터 키 테이블 및 문자열 리소스만 포함 될 수 있습니다.

하지만 문자열 리소스를 '\n' 문자로 구분 되는 최대 7 개의 부분으로 구성 됩니다 ('\n' 문자 자리 표시자로 필요한 부분 문자열이 포함 되어 있지 않으면; 후행 '\n' 문자가 필요 하지 않습니다); 이러한 부분 문자열에는 문서 유형에 대해 설명합니다. 부분 문자열에 대 한 내용은 참조 하세요 [CDocTemplate::GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)합니다. 이 문자열 리소스는 응용 프로그램의 리소스 파일에 있습니다. 예를 들어:

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

문자열 '\n' 문자로 시작 하는 참고 왜냐하면 첫 번째 부분 MDI 응용 프로그램에 대 한 사용 되지 않으며 따라서 포함 되지 않습니다. 문자열 편집기;를 사용 하 여이 문자열을 편집할 수 있습니다. 전체 문자열을 개별 항목 7 아니라 문자열 편집기에서 단일 항목으로 나타납니다.

이러한 리소스 유형에 대 한 자세한 내용은 참조 하세요. [리소스 편집기](../../windows/resource-editors.md)합니다.

*pDocClass*<br/>
가리키는 `CRuntimeClass` 문서 클래스의 개체입니다. 이 클래스는를 `CDocument`-문서를 나타내기 위해 정의한 클래스를 파생 합니다.

*pFrameClass*<br/>
가리키는 `CRuntimeClass` 프레임 창 클래스의 개체입니다. 이 클래스 수를 `CMDIChildWnd`-클래스를 파생 되거나 수 `CMDIChildWnd` 문서 프레임 창에 대해 기본 동작을 원하는 경우 자체입니다.

*pViewClass*<br/>
가리키는 `CRuntimeClass` 뷰 클래스의 개체입니다. 이 클래스는를 `CView`-문서 표시를 정의 하는 클래스를 파생 합니다.

### <a name="remarks"></a>설명

동적으로 하나를 할당 `CMultiDocTemplate` 응용 프로그램을 지원 하 고 각 전달 각 문서 유형에 대 한 개체 `CWinApp::AddDocTemplate` 에서 `InitInstance` 응용 프로그램 클래스의 멤버 함수입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#92](../../mfc/codesnippet/cpp/cmultidoctemplate-class_1.cpp)]

두 번째 예는 다음과 같습니다.

[!code-cpp[NVC_MFCDocView#93](../../mfc/codesnippet/cpp/cmultidoctemplate-class_2.cpp)]

## <a name="see-also"></a>참고자료

[CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)<br/>
[CSingleDocTemplate 클래스](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CWinApp 클래스](../../mfc/reference/cwinapp-class.md)
