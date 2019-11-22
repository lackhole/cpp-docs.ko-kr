---
title: CDaoParameterInfo 구조체
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 9f96cba8ea43db7e24e834b1de4ffb593b2c6e0d
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303482"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo 구조체

`CDaoParameterInfo` 구조에는 DAO (data access objects)에 대해 정의 된 매개 변수 개체에 대 한 정보가 포함 되어 있습니다. DAO 3.6은 최종 버전이 며 사용 되지 않는 것으로 간주 됩니다.

## <a name="syntax"></a>구문

```
struct CDaoParameterInfo
{
    CString m_strName;       // Primary
    short m_nType;           // Primary
    ColeVariant m_varValue;  // Secondary
};
```

#### <a name="parameters"></a>매개 변수

*m_strName*<br/>
매개 변수 개체의 이름을 고유 하 게 합니다. 자세한 내용은 DAO 도움말의 "이름 속성" 항목을 참조 하십시오.

*m_nType*<br/>
매개 변수 개체의 데이터 형식을 나타내는 값입니다. 가능한 값 목록은 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조체의 *m_nType* 멤버를 참조 하십시오. 자세한 내용은 DAO 도움말의 "형식 속성" 항목을 참조 하십시오.

*m_varValue*<br/>
[COleVariant](../../mfc/reference/colevariant-class.md) 개체에 저장 된 매개 변수의 값입니다.

## <a name="remarks"></a>설명

위의 주 및 보조에 대 한 참조는 `CDaoQueryDef`클래스의 [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) 멤버 함수가 정보를 반환 하는 방법을 표시 합니다.

MFC는 클래스의 DAO 매개 변수 개체를 캡슐화 하지 않습니다. DAO querydef 개체 기본 MFC `CDaoQueryDef` 개체는 매개 변수 컬렉션에 매개 변수를 저장 합니다. [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 개체의 매개 변수 개체에 액세스 하려면 특정 매개 변수 이름 또는 인덱스에 대 한 querydef 개체의 `GetParameterInfo` 멤버 함수를 Parameters 컬렉션에 호출 합니다. [CDaoQueryDef:: GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) 멤버 함수를 `GetParameterInfo`와 함께 사용 하 여 Parameters 컬렉션을 반복할 수 있습니다.

[CDaoQueryDef:: GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) 멤버 함수에서 검색 된 정보는 `CDaoParameterInfo` 구조에 저장 됩니다. 매개 변수 컬렉션에서 매개 변수 개체를 저장 하는 쿼리 정의 개체에 대 한 `GetParameterInfo`를 호출 합니다.

> [!NOTE]
>  매개 변수의 값만 가져오거나 설정 하려는 경우 `CDaoRecordset`클래스의 [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) 및 [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) 멤버 함수를 사용 합니다.

또한 `CDaoParameterInfo`는 디버그 빌드에서 `Dump` 멤버 함수를 정의 합니다. `Dump`를 사용 하 여 `CDaoParameterInfo` 개체의 콘텐츠를 덤프할 수 있습니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고 항목

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)
