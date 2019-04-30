---
title: CDaoRelationInfo 구조체
ms.date: 06/25/2018
f1_keywords:
- CDaoRelationInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure [MFC]
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
ms.openlocfilehash: 7d1c86732966d8222582dc6d4527af89963a5cdc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152828"
---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo 구조체

합니다 `CDaoRelationInfo` 필드의 두 테이블 간에 정의 된 관계에 대 한 정보를 포함 하는 구조를 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 개체입니다.

## <a name="syntax"></a>구문

```cpp
struct CDaoRelationInfo
{
    CDaoRelationInfo();                     // Constructor
    CString m_strName;                      // Primary
    CString m_strTable;                     // Primary
    CString m_strForeignTable;              // Primary
    long m_lAttributes;                     // Secondary
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary
    short m_nFields;                        // Secondary
    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

#### <a name="parameters"></a>매개 변수

*m_strName*<br/>
관계 개체의 고유 이름을 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.

*m_strTable*<br/>
관계의 기본 테이블을 이름을 지정 합니다.

*m_strForeignTable*<br/>
관계의 외래 테이블을 이름을 지정 합니다. 에 있는 외래 테이블에 외래 키를 포함 하는 데 테이블이입니다. 에 있는 외래 테이블을 사용 하 여 설정 하거나 참조 무결성을 적용 하는 일반적으로 합니다. 외래 테이블에 일 대 다 관계의 다 쪽 일반적으로 켜져 있습니다. 외래 테이블의 예로 미국 또는 캐나다의 주 고객 주문에 대 한 코드를 포함 하는 테이블입니다.

*m_lAttributes*<br/>
관계 형식에 대 한 정보를 포함합니다. 이 멤버의 값 중 하나일 수 있습니다.

- `dbRelationUnique` 관계가 한 일입니다.

- `dbRelationDontEnforce` 관계 없는 (참조 무결성)를 적용 합니다.

- `dbRelationInherited` 관계는 두 개의 연결 된 테이블을 포함 하는 현재 데이터베이스에 존재 합니다.

- `dbRelationLeft` 왼쪽된 조인입니다. 첫 번째에서 레코드의 모든 왼쪽된 외부 조인을 포함 (왼쪽) 두 테이블의 두 번째 (오른쪽) 테이블의 레코드에 대 한 일치 하는 값이 없는 경우에 합니다.

- `dbRelationRight` 오른쪽 조인입니다. 오른쪽 우선 외부 조인은 두 번째에서 레코드를 모두 포함 되어 있습니다 (오른쪽) 두 테이블의 첫 번째 (왼쪽) 테이블의 레코드에 대 한 일치 하는 값이 없는 경우에 합니다.

- `dbRelationUpdateCascade` 업데이트도 함께 복사 합니다.

- `dbRelationDeleteCascade` 삭제가 계단식으로 배열 됩니다.

*m_pFieldInfos*<br/>
배열에 대 한 포인터 [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) 구조입니다. 배열 관계의 각 필드에 대 한 개체를 포함합니다. `m_nFields` 배열 요소의 수를 제공 하는 데이터 멤버입니다.

*m_nFields*<br/>
수가 `CDaoRelationFieldInfo` 개체는 `m_pFieldInfos` 데이터 멤버입니다.

## <a name="remarks"></a>설명

기본 및 보조 위의에 대 한 참조 정보에서 반환 되는 방법을 나타내는 합니다 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) 클래스 멤버 함수 `CDaoDatabase`합니다.

관계 개체는 MFC 클래스에 의해 표시 되지 않습니다. 대신, MFC 개체를 내부 DAO 개체는 `CDaoDatabase` 관계 개체의 컬렉션을 유지 하는 클래스: `CDaoDatabase` 관계 내용은의 일부 개별 항목에 액세스 하려면 제공 멤버 함수 를사용하여한번에모두액세스할수있습니다`CDaoRelationInfo` 를 호출 하 여 개체를 `GetRelationInfo` 포함 하는 데이터베이스 개체의 멤버 함수입니다.

검색 되는 정보는 [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) 멤버 함수에 저장 되는 `CDaoRelationInfo` 구조입니다. `CDaoRelationInfo` 또한 정의 `Dump` 디버그 멤버 함수를 만듭니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 데는 `CDaoRelationInfo` 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고자료

[CDaoRelationFieldInfo 구조체](../../mfc/reference/cdaorelationfieldinfo-structure.md)
