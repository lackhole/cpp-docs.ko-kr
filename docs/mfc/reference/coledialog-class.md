---
title: COleDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
ms.openlocfilehash: 353e2ed312fa7dbb9ef7bdfabc2b174abf8e1e1d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375719"
---
# <a name="coledialog-class"></a>COleDialog 클래스

OLE 대화 상자에 공통적인 기능을 제공합니다.

## <a name="syntax"></a>구문

```
class COleDialog : public CCommonDialog
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[COleDialog::GetLastError](#getlasterror)|대화 상자에서 반환 된 오류 코드를 가져옵니다.|

## <a name="remarks"></a>설명

파생 된 여러 클래스를 제공 하는 Microsoft Foundation Class 라이브러리를 `COleDialog`:

- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)

- [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)

- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)

- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)

- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)

- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)

- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)

- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)

OLE 관련 대화 상자에 대 한 자세한 내용은 문서 참조 [OLE의 대화 상자](../../mfc/dialog-boxes-in-ole.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`COleDialog`

## <a name="requirements"></a>요구 사항

**헤더:** afxodlgs.h

##  <a name="getlasterror"></a>  COleDialog::GetLastError

호출을 `GetLastError` 멤버 함수 추가 오류 정보를 가져올 때 `DoModal` IDABORT를 반환 합니다.

```
UINT GetLastError() const;
```

### <a name="return-value"></a>반환 값

반환 된 오류 코드 `GetLastError` 표시 되는 특정 대화 상자에 따라 달라 집니다.

### <a name="remarks"></a>설명

참조 된 `DoModal` 특정 오류 메시지에 대 한 정보에 대 한 파생된 클래스에서 멤버 함수입니다.

## <a name="see-also"></a>참고자료

[CCommonDialog 클래스](../../mfc/reference/ccommondialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
