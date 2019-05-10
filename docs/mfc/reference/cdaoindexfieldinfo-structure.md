---
title: CDaoIndexFieldInfo 구조체
ms.date: 11/04/2016
f1_keywords:
- CDaoIndexFieldInfo
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
ms.openlocfilehash: d03a6f6eadd4cf6ccb5279edf18675605d0b1485
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399761"
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo 구조체

`CDaoIndexFieldInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 되는 인덱스 필드 개체에 대 한 정보가 들어 있습니다.

## <a name="syntax"></a>구문

```
struct CDaoIndexFieldInfo
{
    CString m_strName;          // Primary
    BOOL m_bDescending;         // Primary
};
```

#### <a name="parameters"></a>매개 변수

*m_strName*<br/>
인덱스 필드 개체의 고유 이름을 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.

*m_bDescending*<br/>
인덱스 개체에서 정의한 인덱스 순서를 나타냅니다. 순서는 내림차순 면 TRUE입니다.

## <a name="remarks"></a>설명

인덱스 개체 필드를 테이블 정의 (또는 테이블을 기반으로 레코드 집합)에 인덱싱된 필드를 나타내는 수가 있습니다. 위의 기본에 대 한 참조 정보에서 반환 되는 방법을 나타내는 합니다 `m_pFieldInfos` 의 멤버를 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 호출 하 여 가져올 개체를 `GetIndexInfo` 클래스의 멤버 함수 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) 나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)합니다.

인덱스 개체와 인덱스 필드는 MFC 클래스에 의해 표시 되지 않습니다. DAO 클래스의 기본 MFC 개체를 개체 대신 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 인덱스 컬렉션 이라고 하는 인덱스 개체의 컬렉션을 포함 합니다. 각 인덱스 개체 필드 개체의 컬렉션을 포함합니다. 이러한 클래스의 인덱스 정보를 개별 항목에 액세스 하는 멤버 함수를 제공 하거나 사용 하 여 한 번에 모두 액세스할 수 있습니다는 `CDaoIndexInfo` 를 호출 하 여 개체를 `GetIndexInfo` 포함 하는 개체의 멤버 함수입니다. `CDaoIndexInfo` 개체를 포함 된 데이터 멤버를 차례로 `m_pFieldInfos`, 배열을 가리키는 `CDaoIndexFieldInfo` 개체입니다.

호출 된 `GetIndexInfo` 컬렉션의 인덱스를 포함 하는 테이블 정의 또는 레코드 집합 개체의 멤버 함수는 관심 인덱스 개체를 저장 합니다. 그런 합니다 `m_pFieldInfos` 의 멤버는 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 개체입니다. 길이 `m_pFieldInfos` 배열에 저장 된 `m_nFields`합니다. `CDaoIndexFieldInfo` 또한 정의 `Dump` 디버그 멤버 함수를 만듭니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 데는 `CDaoIndexFieldInfo` 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고자료

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)<br/>
[CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)
