---
title: DAO 데이터베이스 엔진 초기화 및 종료
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.macros.data
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
ms.openlocfilehash: 8ad0c1df2f5b6a7b1b48d2db119b04e4b3234f10
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323218"
---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO 데이터베이스 엔진 초기화 및 종료

먼저 DAO 데이터베이스 엔진 해야 MFC DAO 개체를 사용 하는 경우 초기화 및 종료 한 다음 응용 프로그램 또는 DLL 종료 되기 전에 합니다. 두 개의 함수가 `AfxDaoInit` 및 `AfxDaoTerm`, 이러한 작업을 수행 합니다.

### <a name="dao-database-engine-initialization-and-termination"></a>DAO 데이터베이스 엔진 초기화 및 종료

|||
|-|-|
|[AfxDaoInit](#afxdaoinit)|DAO 데이터베이스 엔진을 초기화합니다.|
|[AfxDaoTerm](#afxdaoterm)|DAO 데이터베이스 엔진을 종료합니다.|

##  <a name="afxdaoinit"></a>  AfxDaoInit

이 함수는 DAO 데이터베이스 엔진을 초기화합니다.

```

void AfxDaoInit();

throw(CDaoException*);
```

### <a name="remarks"></a>설명

대부분의 경우에서 호출할 필요가 `AfxDaoInit` 응용 프로그램이 자동으로 호출 하므로 필요할 때.

관련 정보 및 호출 하는 예제 `AfxDaoInit`를 참조 하세요 [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

##  <a name="afxdaoterm"></a>  AfxDaoTerm

이 함수는 DAO 데이터베이스 엔진을 종료합니다.

```

void AfxDaoTerm();
```

### <a name="remarks"></a>설명

일반 MFC DLL;에서이 함수를 호출 하려면만 하면 일반적으로 응용 프로그램에서는 자동으로 호출 `AfxDaoTerm` 필요할 때.

기본 MFC Dll에서 호출 `AfxDaoTerm` 하기 전에 `ExitInstance` 함수 되지만 MFC DAO 개체를 모두 제거 된 후입니다.

관련 정보를 참조 하세요 [기술 참고 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxdao.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
