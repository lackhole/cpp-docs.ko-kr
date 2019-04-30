---
title: CLongBinary 클래스
ms.date: 11/04/2016
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
helpviewer_keywords:
- CLongBinary class [MFC]
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
ms.openlocfilehash: ed3a153ec89785a9c9da43037d20f7d88b5661ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62225204"
---
# <a name="clongbinary-class"></a>CLongBinary 클래스

데이터베이스에서 매우 큰 이진 데이터 개체(BLOB 또는 "이진 대형 개체"라고도 함) 사용 작업을 간소화합니다.

## <a name="syntax"></a>구문

```
class CLongBinary : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CLongBinary::CLongBinary](#clongbinary)|`CLongBinary` 개체를 생성합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|이름|설명|
|----------|-----------------|
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|실제 크기 핸들이에 저장 된 데이터 개체의 바이트를 포함 `m_hData`합니다.|
|[CLongBinary::m_hData](#m_hdata)|실제 이미지 개체에 대 한 Windows HGLOBAL 핸들을 포함합니다.|

## <a name="remarks"></a>설명

예를 들어 SQL 테이블에서 레코드 필드에 그림을 나타내는 비트맵을 포함할 수 있습니다. `CLongBinary` 개체는 이러한 개체를 저장 하 고 해당 크기는 추적 합니다.

> [!NOTE]
>  좋습니다 지금 사용 하는 것이 일반적으로 [CByteArray](../../mfc/reference/cbytearray-class.md) 함께에서 합니다 [DFX_Binary](record-field-exchange-functions.md#dfx_binary) 함수입니다. 계속 사용할 수 없습니다 `CLongBinary`, 하지만 일반적 `CByteArray` 많은 기능을 제공 win32에서 되므로 더 이상 16 비트를 사용 하 여 발생 하는 크기 제한 `CByteArray`합니다. 이 권장 사항은 개방형 데이터베이스 연결 (ODBC) 뿐만 아니라 데이터 액세스 개체 (DAO)를 사용한 프로그래밍에 적용 됩니다.

사용 하는 `CLongBinary` 개체 형식의 필드 데이터 멤버를 선언 `CLongBinary` 레코드 집합 클래스에서. 이 멤버는 레코드 집합 클래스의 멤버를 포함된 되며 레코드 집합이 생성 될 때 생성 됩니다. 이후에 `CLongBinary` 개체가 생성 되 면 레코드 필드 교환 (RFX) 메커니즘 데이터 소스의 현재 레코드의 필드에서 데이터 개체를 로드 하 고는 레코드가 업데이트 될 때 레코드에 다시 저장 합니다. RFX에 대 한 저장소를 할당 하는 큰 이진 개체의 크기에 대 한 데이터 소스를 쿼리 (통해 합니다 `CLongBinary` 개체의 `m_hData` 데이터 멤버)를 가져와 `HGLOBAL` 의 데이터에 대 한 핸들 `m_hData`합니다. RFX 저장 데이터 개체의 실제 크기는 `m_dwDataLength` 데이터 멤버입니다. 통해 개체의 데이터로 작동 `m_hData`, 일반적으로 Windows에 저장 된 데이터를 조작 하는 데 사용 하는 동일한 기술을 사용 하 여 `HGLOBAL` 처리 합니다.

레코드 집합에 포함된 된 경우 삭제할 `CLongBinary` 개체도 제거 하 고 해당 소멸자 할당을 취소 합니다 `HGLOBAL` 데이터 핸들입니다.

큰 개체 및 사용에 대 한 자세한 내용은 `CLongBinary`, 문서를 참조 하세요 [레코드 집합 (ODBC)](../../data/odbc/recordset-odbc.md) 고 [레코드 집합: 대형 데이터 항목 (ODBC)를 사용 하 여 작업](../../data/odbc/recordset-working-with-large-data-items-odbc.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CLongBinary`

## <a name="requirements"></a>요구 사항

**헤더:** afxdb_.h

##  <a name="clongbinary"></a>  CLongBinary::CLongBinary

`CLongBinary` 개체를 생성합니다.

```
CLongBinary();
```

##  <a name="m_dwdatalength"></a>  CLongBinary::m_dwDataLength

실제 크기는 HGLOBAL 핸들에 저장 된 데이터의 바이트에 저장 `m_hData`합니다.

```
SQLULEN m_dwDataLength;
```

### <a name="remarks"></a>설명

이 크기는 데이터에 할당 된 메모리 블록의 크기 보다 작을 수 있습니다. Win32 호출 [GLobalSize](/windows/desktop/api/winbase/nf-winbase-globalsize) 함수 할당 된 크기를 가져옵니다.

##  <a name="m_hdata"></a>  CLongBinary::m_hData

실제 binary large object 데이터에 대 한 Windows HGLOBAL 핸들을 저장합니다.

```
HGLOBAL m_hData;
```

## <a name="see-also"></a>참고자료

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CRecordset 클래스](../../mfc/reference/crecordset-class.md)
