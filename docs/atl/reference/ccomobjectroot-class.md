---
title: CComObjectRoot 클래스
ms.date: 11/04/2016
f1_keywords:
- CComObjectRoot
- atlcom/ATL::CComObjectRoot
helpviewer_keywords:
- CComObjectRoot class
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
ms.openlocfilehash: 9a9ffa1813fb15297d209894050b6bcce6802df2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259367"
---
# <a name="ccomobjectroot-class"></a>CComObjectRoot 클래스

이 typedef [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) 스레딩 모델이 서버의 기본 템플릿 화 됩니다.

## <a name="syntax"></a>구문

```
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;
```

## <a name="remarks"></a>설명

`CComObjectRoot` `typedef` 의 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) 스레딩 모델이 서버의 기본 템플릿 화 합니다. 따라서 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel) 참조할 됩니다 [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) 하거나 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).

`CComObjectRootEx` 집계 및 집계 개체에 대 한 개체 참조 개수 관리를 처리합니다. 개체가 집계 되는 개체를 집계 하는 경우 알 수 없는 외부에 대 한 포인터를 보유 하는 경우 개체 참조 횟수를 포함 합니다. 집계 개체에 대 한 `CComObjectRootEx` 을 생성 하려면 내부 개체의 오류를 처리 하기 메서드를 사용할 수 있으며 내부 인터페이스 릴리스될 때 삭제에서 외부 개체 또는 내부 개체를 보호 하기 위해 삭제 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atlcom.h

## <a name="see-also"></a>참고자료

[CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComAggObject 클래스](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject 클래스](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject 클래스](../../atl/reference/ccompolyobject-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)
