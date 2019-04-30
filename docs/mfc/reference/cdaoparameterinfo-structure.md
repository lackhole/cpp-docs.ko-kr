---
title: CDaoParameterInfo 구조체
ms.date: 11/04/2016
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 62addd44f8aa8fceafef6a27244994a2ec6b766b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399787"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo 구조체

`CDaoParameterInfo` 구조 데이터 액세스 개체 (DAO)에 대해 정의 된 매개 변수 개체에 대 한 정보가 들어 있습니다.

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
매개 변수 개체의 고유 이름을 지정 합니다. 자세한 내용은 DAO 도움말의 "Name 속성" 항목을 참조 합니다.

*m_nType*<br/>
매개 변수 개체의 데이터 형식을 나타내는 값입니다. 가능한 값 목록을 참조 하세요. 합니다 *m_nType* 의 멤버는 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) 구조입니다. 자세한 내용은 DAO 도움말의 "형식 속성" 항목을 참조 하세요.

*m_varValue*<br/>
에 저장 된 매개 변수의 값을 [COleVariant](../../mfc/reference/colevariant-class.md) 개체입니다.

## <a name="remarks"></a>설명

기본 및 보조 위의에 대 한 참조 정보에서 반환 되는 방법을 나타내는 합니다 [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) 클래스 멤버 함수 `CDaoQueryDef`합니다.

MFC는 클래스에서 DAO 매개 변수 개체를 캡슐화 하지 않습니다. 쿼리 정의 DAO MFC 기본 개체 `CDaoQueryDef` 개체는 해당 매개 변수 컬렉션에서 매개 변수를 저장 합니다. 매개 변수 개체에 액세스 하는 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 개체, 쿼리 정의 개체의 호출 `GetParameterInfo` 특정 매개 변수 이름 또는 매개 변수 컬렉션에 대 한 인덱스에 대 한 멤버 함수입니다. 사용할 수는 [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) 멤버 함수를 함께 `GetParameterInfo` 매개 변수 컬렉션을 반복 합니다.

검색 되는 정보는 [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) 멤버 함수에 저장 되는 `CDaoParameterInfo` 구조입니다. 호출 `GetParameterInfo` 해당 매개 변수 컬렉션 매개 변수 개체에 저장 된 쿼리 정의 개체에 대 한 합니다.

> [!NOTE]
>  가져오기 또는 설정 매개 변수의 값만, 사용 하려는 경우는 [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) 하 고 [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) 클래스의 멤버 함수 `CDaoRecordset`합니다.

`CDaoParameterInfo` 또한 정의 `Dump` 디버그 멤버 함수를 만듭니다. 사용할 수 있습니다 `Dump` 의 내용을 덤프 하는 데는 `CDaoParameterInfo` 개체입니다.

## <a name="requirements"></a>요구 사항

**헤더:** afxdao.h

## <a name="see-also"></a>참고자료

[구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef 클래스](../../mfc/reference/cdaoquerydef-class.md)
