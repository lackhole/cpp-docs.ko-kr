---
title: CDynamicStringAccessorW 클래스
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorW
helpviewer_keywords:
- CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
ms.openlocfilehash: 20ea4a2d795108e00c4b11c3abea6cf7b9953ca7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59025152"
---
# <a name="cdynamicstringaccessorw-class"></a>CDynamicStringAccessorW 클래스

이 기능을 사용 하면 데이터베이스 스키마 (내부 구조)에 대 한 지식이 없는 경우 데이터 소스에 액세스할 수 있습니다.

## <a name="syntax"></a>구문

```cpp
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;
```

## <a name="remarks"></a>설명

공급자 문자열 데이터로 데이터 저장소에서 액세스 하는 모든 데이터를 인출 하는 요청 모두 있지만 `CDynamicStringAccessor` 유니코드 문자열 데이터를 요청 합니다.

`CDynamicStringAccessorW` 상속 `GetString` 하 고 `SetString` 에서 `CDynamicStringAccessor`합니다. 이러한 메서드를 사용 하는 경우는 `CDynamicStringAccessorW` 개체를 `BaseType` 됩니다 **WCHAR**합니다.

## <a name="requirements"></a>요구 사항

**헤더**: atldbcli.h

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor 클래스](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessor 클래스](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
