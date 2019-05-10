---
title: CDaoWorkspaceInfo 구조체
ms.date: 11/04/2016
f1_keywords:
- CDaoWorkspaceInfo
helpviewer_keywords:
- CDaoWorkspaceInfo structure [MFC]
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
ms.openlocfilehash: afbc73c079a6deec3f3e1b7455f9f2dbface5025
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62253637"
---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo 구조체

`CDaoWorkspaceInfo` 구조 데이터 액세스 개체 (DAO) 데이터베이스 액세스에 대해 정의 된 작업 영역에 대 한 정보가 들어 있습니다.

## <a name="syntax"></a>구문

```
struct CDaoWorkspaceInfo
{
    CString m_strName;           // Primary
    CString m_strUserName;       // Secondary
    BOOL m_bIsolateODBCTrans;    // All
};
```

#### <a name="parameters"></a>매개 변수

*m_strName*<br/>
작업 영역 개체의 고유 이름을 지정 합니다. 이 속성의 값을 직접 검색 하려면 쿼리 정의 개체의 호출 [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) 멤버 함수입니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.

*m_strUserName*<br/>
작업 영역 개체의 소유자를 나타내는 값입니다. 관련된 내용은 DAO 도움말의 "사용자 이름 속성" 항목을 참조 합니다.

*m_bIsolateODBCTrans*<br/>
동일한 ODBC 데이터베이스와 관련 된 여러 트랜잭션을 격리 되는지 여부를 나타내는 값입니다. 자세한 내용은 [CDaoWorkspace::SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans)합니다. 관련된 내용은 DAO 도움말의 "IsolateODBCTrans Property" 항목을 참조 합니다.

## <a name="remarks"></a>설명

작업 영역 클래스의 개체인 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)합니다. 기본, 보조 및 위의 모든에 대 한 참조 정보에서 반환 되는 방법을 나타내는 합니다 [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) 클래스 멤버 함수 `CDaoWorkspace`합니다.

검색 되는 정보는 [CDaoWorkspace::GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) 멤버 함수에 저장 되는 `CDaoWorkspaceInfo` 구조입니다. `CDaoWorkspaceInfo` 또한 정의 `Dump` 디버그 멤버 함수를 만듭니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 데는 `CDaoWorkspaceInfo` 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고자료

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoWorkspace 클래스](../../mfc/reference/cdaoworkspace-class.md)
