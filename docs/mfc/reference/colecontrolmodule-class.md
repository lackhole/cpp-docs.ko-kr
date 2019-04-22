---
title: COleControlModule 클래스
ms.date: 11/04/2016
f1_keywords:
- OleControlModule
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
ms.openlocfilehash: f6d486c7bacb897d70d85414ac3d0bd0d13e447b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58780290"
---
# <a name="colecontrolmodule-class"></a>COleControlModule 클래스

OLE 컨트롤 모듈 개체를 파생하는 기본 클래스입니다.

## <a name="syntax"></a>구문

```
class COleControlModule : public CWinApp
```

## <a name="remarks"></a>설명

이 클래스는 제어 모듈을 초기화 하는 것에 대 한 멤버 함수를 제공 합니다. Microsoft Foundation 클래스를 사용 하는 각 OLE 컨트롤 모듈에서 파생 된 개체를 포함할 수 있습니다만 `COleControlModule`합니다. 이 개체가 생성 될 때 다른 C++ 전역 개체 생성 됩니다. 파생 된 선언 `COleControlModule` 전역 수준 개체입니다.

사용 하 여 대 한 자세한 내용은 합니다 `COleControlModule` 클래스를 참조 하십시오는 [CWinApp](../../mfc/reference/cwinapp-class.md) 클래스 및 문서 [ActiveX 컨트롤](../../mfc/mfc-activex-controls.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

[CWinApp](../../mfc/reference/cwinapp-class.md)

`COleControlModule`

## <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="see-also"></a>참고자료

[MFC 샘플 TESTHELP](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)
