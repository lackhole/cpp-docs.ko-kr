---
title: CFolderPickerDialog 클래스
ms.date: 03/27/2019
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
ms.openlocfilehash: 435c91082fa901f0bc9726316f0358fc5a669b29
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565011"
---
# <a name="cfolderpickerdialog-class"></a>CFolderPickerDialog 클래스

CFolderPickerDialog 클래스 폴더 선택 모드에서 CFileDialog를 구현합니다.

## <a name="syntax"></a>구문

```
class CFolderPickerDialog : public CFileDialog;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CFolderPickerDialog::~CFolderPickerDialog](#_dtorcfolderpickerdialog)|소멸자|
|[CFolderPickerDialog::CFolderPickerDialog](#cfolderpickerdialog)|생성자입니다.|

## <a name="remarks"></a>설명

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

[CFileDialog](../../mfc/reference/cfiledialog-class.md)

`CFolderPickerDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxdlgs.h

##  <a name="cfolderpickerdialog"></a>  CFolderPickerDialog::CFolderPickerDialog

생성자입니다.

```
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL,
    DWORD dwSize = 0);
```

### <a name="parameters"></a>매개 변수

*lpszFolder*<br/>
초기 폴더입니다.

*dwFlags*<br/>
대화 상자를 사용자 지정할 수 있도록 하는 하나 이상의 플래그의 조합입니다.

*pParentWnd*<br/>
대화 상자 개체의 부모 또는 소유자 창에 대 한 포인터입니다.

*dwSize*<br/>
OPENFILENAME 구조체의 크기입니다.

### <a name="remarks"></a>설명

##  <a name="_dtorcfolderpickerdialog"></a>  CFolderPickerDialog::~CFolderPickerDialog

소멸자

```
virtual ~CFolderPickerDialog();
```

### <a name="remarks"></a>설명

## <a name="see-also"></a>참고자료

[클래스](../../mfc/reference/mfc-classes.md)
