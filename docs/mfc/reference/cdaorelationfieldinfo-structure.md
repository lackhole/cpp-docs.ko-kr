---
title: CDaoRelationFieldInfo 구조체
ms.date: 11/04/2016
f1_keywords:
- CDaoRelationFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
ms.openlocfilehash: 85dd853a9aae41a87bbe7ef5c69e22846678cf8a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62206110"
---
# <a name="cdaorelationfieldinfo-structure"></a>CDaoRelationFieldInfo 구조체

`CDaoRelationFieldInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 관계에 있는 필드에 대 한 정보가 들어 있습니다.

## <a name="syntax"></a>구문

```
struct CDaoRelationFieldInfo
{
    CString m_strName;           // Primary
    CString m_strForeignName;    // Primary
};
```

#### <a name="parameters"></a>매개 변수

*m_strName*<br/>
관계의 기본 테이블에 있는 필드의 이름입니다.

*m_strForeignName*<br/>
관계의 외래 테이블의 필드 이름입니다.

## <a name="remarks"></a>설명

DAO 관계 개체를 기본 테이블 및 관계를 정의 하는 필드에 있는 외래 테이블의 필드를 지정 합니다. 위의 구조 정의에서 기본에 대 한 참조 정보에서 반환 되는 방법을 나타내는 합니다 `m_pFieldInfos` 의 멤버를 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 호출 하 여 가져올 개체를 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)클래스의 멤버 함수 `CDaoDatabase`합니다.

관계 개체 및 관계 필드 개체는 MFC 클래스에 의해 표시 되지 않습니다. DAO 클래스의 기본 MFC 개체를 개체 대신 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 관계 컬렉션 이라고 하는 관계 개체의 컬렉션을 포함 합니다. 각 관계 개체 관계 필드 개체의 컬렉션을 포함합니다. 각 관계 필드 개체 외래 테이블의 필드를 사용 하 여 기본 테이블의 필드를 상호 연결합니다. 전체적으로 볼 때, 관계 필드 개체 정의 필드 그룹을 각 테이블에 함께 관계를 정의 하는 합니다. `CDaoDatabase` 관계 개체에 액세스할 수 있습니다는 `CDaoRelationInfo` 를 호출 하 여 개체를 `GetRelationInfo` 멤버 함수입니다. `CDaoRelationInfo` 개체를 포함 된 데이터 멤버를 차례로 `m_pFieldInfos`, 배열을 가리키는 `CDaoRelationFieldInfo` 개체입니다.

호출을 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) 포함 하는 멤버 함수 `CDaoDatabase` 개체 관계 컬렉션은 해당 관계 개체에 관심이 저장 합니다. 그런 합니다 `m_pFieldInfos` 의 멤버는 [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 개체입니다. `CDaoRelationFieldInfo` 또한 정의 `Dump` 디버그 멤버 함수를 만듭니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 데는 `CDaoRelationFieldInfo` 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고자료

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoRelationInfo 구조체](../../mfc/reference/cdaorelationinfo-structure.md)
