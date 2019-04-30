---
title: CDaoIndexInfo 구조체
ms.date: 06/25/2018
f1_keywords:
- CDaoIndexInfo
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure [MFC]
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
ms.openlocfilehash: 55f64fcebc308bd0e63643cfb5447608c4e2e37c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399774"
---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo 구조체

`CDaoIndexInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 인덱스 개체에 대 한 정보가 들어 있습니다.

## <a name="syntax"></a>구문

```cpp
struct CDaoIndexInfo {
    CDaoIndexInfo();                    // Constructor
    CString m_strName;                  // Primary
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary
    short m_nFields;                    // Primary
    BOOL m_bPrimary;                    // Secondary
    BOOL m_bUnique;                     // Secondary
    BOOL m_bClustered;                  // Secondary
    BOOL m_bIgnoreNulls;                // Secondary
    BOOL m_bRequired;                   // Secondary
    BOOL m_bForeign;                    // Secondary
    long m_lDistinctCount;              // All

    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

### <a name="parameters"></a>매개 변수

*m_strName*<br/>
필드 개체의 고유 이름을 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.

*m_pFieldInfos*<br/>
배열에 대 한 포인터 [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) 테이블 정의 또는 레코드 집합 필드는 인덱스의 키 필드를 나타내는 개체입니다. 각 개체는 인덱스의 필드 하나를 식별합니다. 기본 인덱스 순서는 오름차순입니다. 인덱스 개체에는 각 레코드에 대 한 인덱스 키를 나타내는 하나 이상의 필드가 있을 수 있습니다. 이러한 수 수 오름차순, 내림차순 또는 조합 합니다.

*m_nFields*<br/>
필드에 저장 된 수가 `m_pFieldInfos`합니다.

*m_bPrimary*<br/>
기본 속성이 TRUE 이면 인덱스 개체는 기본 인덱스를 나타냅니다. 기본 인덱스를 고유 하 게 미리 정의 된 순서에 따라 테이블의 모든 레코드를 식별 하는 하나 이상의 필드로 구성 됩니다. 인덱스 필드는 고유 해야, 하므로 인덱스 개체의 고유 속성은 또한 DAO에서 TRUE로 설정 됩니다. 기본 인덱스 개 필드로 구성 된 경우 각 필드에 중복 값이 포함 될 수 있습니다 하지만 각 인덱싱된 모든 필드에서 값 조합이 고유 해야 합니다. 기본 인덱스를 테이블에 대 한 키 구성 되며 일반적으로 기본 키와 동일한 필드가 포함 되어 있습니다.

테이블에 대 한 기본 키를 설정 하면 기본 키 테이블에 대 한 기본 인덱스와 자동으로 정의 됩니다. 자세한 내용은 "기본" 속성과 "고유 속성" DAO 도움말의 항목을 참조 합니다.

> [!NOTE]
> 있을 수 있습니다, 최대, 테이블에 대 한 기본 인덱스.

*m_bUnique*<br/>
인덱스 개체를 테이블에 대 한 고유 인덱스를 나타내는지 여부를 나타냅니다. 이 속성이 TRUE 인 경우 인덱스 개체를 고유 인덱스를 나타냅니다. 고유 인덱스를 논리적으로 고유 하 고 미리 정의 된 순서에 따라 테이블의 모든 레코드를 정렬 하는 하나 이상의 필드로 구성 됩니다. 인덱스 하나 필드로 구성 된 경우 해당 필드의 값이 전체 테이블에 대해 고유 해야 합니다. 인덱스 개 필드로 구성 된 경우 각 필드에 중복 값이 포함 될 수 있습니다 하지만 각 인덱싱된 모든 필드에서 값 조합이 고유 해야 합니다.

인덱스 개체의 고유 및 기본 속성을 TRUE로 설정 하는 경우 인덱스가 unique 및 primary: 미리 정의 된, 논리적 순서에 따라 테이블의 모든 레코드를 고유 하 게 식별합니다. 기본 속성은 FALSE로 설정 하는 경우 인덱스는 보조 인덱스가입니다. (키 및 키가 아닌) 보조 인덱스는 테이블의 레코드에 대 한 식별자로 처리 하지 않고 미리 정의 된 순서로 레코드를 논리적으로 정렬 합니다.

자세한 내용은 "기본" 속성과 "고유 속성" DAO 도움말의 항목을 참조 합니다.

*m_bClustered*<br/>
인덱스 개체를 테이블에 대 한 클러스터형된 인덱스를 나타내는지 여부를 나타냅니다. Index 개체 클러스터형된 인덱스를 나타내는이 속성이 TRUE 인 경우 그렇지 않은 경우 포함 되지 않습니다. 클러스터형된 인덱스를 하나로 구성 하거나 이러한 필드는 자세한 집합적, 전체적으로 볼 때, 미리 정의 된 순서에 따라 테이블의 모든 레코드를 정렬 합니다. 클러스터형된 인덱스와 클러스터형된 인덱스에 의해 지정 된 순서로 테이블의 데이터를 문자 그대로 저장 됩니다. 클러스터형된 인덱스를 테이블의 레코드를 효율적으로 액세스할 수 있습니다. 자세한 내용은 DAO 도움말에서 "클러스터형 속성" 항목을 참조 하세요.

> [!NOTE]
> Clustered 속성은 Jet 데이터베이스 엔진은 클러스터형된 인덱스를 지원 하지 않으므로 Microsoft Jet 데이터베이스 엔진을 사용 하는 데이터베이스에 대 한 무시 됩니다.

*m_bIgnoreNulls*<br/>
인덱스 필드에 Null 값이 있는 레코드에 대 한 인덱스 항목이 있는지 여부를 나타냅니다. 이 속성이 TRUE 이면 Null 값을 가진 필드 인덱스 항목이 없습니다. 레코드 필드를 사용 하 여 더 빨리 검색 하려면 필드에 대 한 인덱스를 정의할 수 있습니다. 인덱싱된 필드에 Null 항목을 허용 하 고 다양 한 항목을 Null로 예상 IgnoreNulls 속성 인덱스 개체에 대 한 인덱스를 사용 하는 저장소 공간의 크기를 줄이기 위해 TRUE로 설정할 수 있습니다. IgnoreNulls 속성 설정 및 필수 속성 설정 함께 Null 인덱스 값을 사용 하 여 레코드를 다음 표와 같이 인덱스 항목에 있는지 여부를 결정 합니다.

|IgnoreNulls|필수|인덱스 필드에 null|
|-----------------|--------------|-------------------------|
|True|False|Null 값 허용 인덱스 항목이 추가 되었습니다.|
|False|False|Null 값 허용 인덱스 항목을 추가 했습니다.|
|True 또는 False|True|Null 값 허용 되지 않습니다. 인덱스 항목이 추가 되었습니다.|

자세한 내용은 DAO 도움말의 "IgnoreNulls 속성" 항목을 참조 하세요.

*m_bRequired*<br/>
DAO 인덱스 개체를 Null이 아닌 값을 필요한 지 여부를 나타냅니다. 이 속성이 TRUE 인 경우 인덱스 개체에는 Null 값을 허용 하지 않습니다. 자세한 내용은 DAO 도움말의 "필수 속성" 항목을 참조 하세요.

> [!TIP]
> DAO 인덱스 개체 또는 field 개체 (테이블 정의 레코드 집합 또는 쿼리 정의 개체 포함)에 대 한이 속성을 설정 하면 필드 개체에 대 한 설정입니다. 필드 개체의 속성 설정의 유효성은 인덱스 개체의 하기 전에 확인 됩니다.

*m_bForeign*<br/>
인덱스 개체를 테이블의 외래 키를 나타내는지 여부를 나타냅니다. 이 속성이 TRUE 인 경우 인덱스는 테이블의 외래 키를 나타냅니다. 외래 키 기본 테이블의 행을 고유 하 게 식별 하는 외래 테이블의 하나 이상의 필드로 구성 됩니다. Microsoft Jet 데이터베이스 엔진 외래 테이블에 대 한 인덱스 개체를 만들고 참조 무결성을 적용 하는 관계를 만들 때 외래 속성을 설정 합니다. 자세한 내용은 DAO 도움말의 "외래 속성" 항목을 참조 하세요.

*m_lDistinctCount*<br/>
연결된 된 테이블에 포함 된 인덱스 개체에 대 한 고유한 값의 수를 나타냅니다. 인덱스의 키 또는 고유 값 수를 확인 하려면 DistinctCount 속성을 확인 합니다. 아무 키나 인덱스에 중복 값을 허용 하는 경우 해당 값의 여러 번 나타날 경우에 한 번만 계산 됩니다. 이 정보는 인덱스 정보를 평가 하 여 데이터 액세스를 최적화 하려고 하는 응용 프로그램에서 유용 합니다. 고유 값 수는 인덱스 개체의 카디널리티 라고도 합니다. DistinctCount 속성이 반영 되지 않습니다 항상 실제 키 수를 특정 시간. 예를 들어 트랜잭션 롤백은 인해 변경 DistinctCount 속성에 즉시 반영 되지 않습니다. 자세한 내용은 DAO 도움말의 "DistinctCount 속성" 항목을 참조 하세요.

## <a name="remarks"></a>설명

기본, 보조 및 위의 모든에 대 한 참조 정보에서 반환 되는 방법을 나타내는 합니다 `GetIndexInfo` 클래스의 멤버 함수 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) 및 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)합니다.

인덱스 개체는 MFC 클래스에 의해 표시 되지 않습니다. DAO 클래스의 기본 MFC 개체를 개체 대신 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 하거나 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 인덱스 컬렉션 이라고 하는 인덱스 개체의 컬렉션을 포함 합니다. 이러한 클래스의 인덱스 정보를 개별 항목에 액세스 하는 멤버 함수를 제공 하거나 사용 하 여 한 번에 모두 액세스할 수 있습니다는 `CDaoIndexInfo` 를 호출 하 여 개체를 `GetIndexInfo` 포함 하는 개체의 멤버 함수입니다.

`CDaoIndexInfo` 생성자 및 소멸자를 올바르게 할당 하 고에 인덱스 필드 정보를 할당을 취소 하기 위해 `m_pFieldInfos`합니다.

검색 되는 정보는 `GetIndexInfo` 테이블 정의 개체의 멤버 함수에 저장 되는 `CDaoIndexInfo` 구조입니다. 호출 된 `GetIndexInfo` 포함 하는 인덱스 개체 저장 된 인덱스 컬렉션에 포함 된 테이블 정의 개체의 멤버 함수입니다. `CDaoIndexInfo` 또한 정의 `Dump` 디버그 멤버 함수를 만듭니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 데는 `CDaoIndexInfo` 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고자료

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)
