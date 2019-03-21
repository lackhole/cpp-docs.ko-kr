---
title: MFC와 ATL에서 공유 하는 클래스
ms.date: 11/04/2016
helpviewer_keywords:
- shared classes, classes
ms.assetid: ca8b4b6b-744d-430b-b31f-d5b2f17bf210
ms.openlocfilehash: 5376a87aac2b82615cd48f80e0e95208b8132bf0
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750483"
---
# <a name="classes-shared-by-mfc-and-atl"></a>MFC와 ATL에서 공유 하는 클래스

다음 표에서 MFC 및 ATL. 공유할 클래스를 보여 줍니다.

|클래스|설명|헤더 파일|
|-----------|-----------------|-----------------|
|[CFileTime](../../atl-mfc-shared/reference/cfiletime-class.md)|파일과 연결 된 날짜 및 시간 값을 관리 하기 위한 메서드를 제공 합니다.|atltime.h|
|[CFileTimeSpan](../../atl-mfc-shared/reference/cfiletimespan-class.md)|상대 날짜 및 시간 값을 파일에 연결 된 관리 하기 위한 메서드를 제공 합니다.|atltime.h|
|[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)|고정된 문자 버퍼를 사용 하 여 문자열 개체를 나타냅니다.|cstringt.h|
|[CImage](../../atl-mfc-shared/reference/cimage-class.md)|향상 된 비트맵 지원, 로드 및 JPEG, GIF, BMP, 및 PNG 이동식 네트워크 그래픽 () 형식 이미지를 저장 하는 기능을 포함 하 여 제공 합니다.|atlimage.h|
|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)|OLE 자동화에 사용 되는 날짜 데이터 형식을 캡슐화 합니다.|atlcomtime.h|
|[COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)|상대 시간을 시간 범위를 나타냅니다.|atlcomtime.h|
|[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)|클래스는 Windows 비슷합니다 [지점](/windows/desktop/api/windef/ns-windef-tagpoint) 도 조작 하는 멤버 함수를 포함 하는 구조 `CPoint` 및 `POINT` 구조입니다.|atltypes.h|
|[CRect](../../atl-mfc-shared/reference/crect-class.md)|클래스는 Windows 비슷합니다 [RECT](/windows/desktop/api/windef/ns-windef-tagrect) 도 조작 하는 멤버 함수를 포함 하는 구조 `CRect` 개체 및 Windows `RECT` 구조입니다.|atltypes.h|
|[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)|나타냅니다는 `CSimpleStringT` 개체입니다.|atlsimpstr.h|
|[CSize](../../atl-mfc-shared/reference/csize-class.md)|클래스는 Windows 비슷합니다 [크기](/windows/desktop/api/windef/ns-windef-tagsize) 상대 좌표 또는 위치를 구현 하는 구조입니다.|atltypes.h|
|[CStrBufT](../../atl-mfc-shared/reference/cstrbuft-class.md)|자동 리소스 정리를 제공 `GetBuffer` 하 고 `ReleaseBuffer` 호출을 기존 `CStringT` 개체입니다.|atlsimpstr.h|
|[CStringData](../../atl-mfc-shared/reference/cstringdata-class.md)|문자열 개체의 데이터를 나타냅니다.|atlsimpstr.h|
|[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)|나타냅니다는 `CStringT` 개체입니다.|(MFC 종속) cstringt.h atlstr.h (MFC 독립적)|
|[CTime](../../atl-mfc-shared/reference/ctime-class.md)|절대 시간 및 날짜를 나타냅니다.|atltime.h|
|[CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)|되는 시간 기간 시간 (초)의 숫자와 내부적으로 저장 됩니다.|atltime.h|
|[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)|인터페이스를 나타내는 `CStringT` 메모리 관리자입니다.|atlsimpstr.h|

## <a name="see-also"></a>참고자료

[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)
