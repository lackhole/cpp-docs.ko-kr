---
title: IDispatch 및 IErrorInfo 지원
ms.date: 11/04/2016
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
ms.openlocfilehash: 2dcebd215ff5e1bdf72323323dfbaebd16fa3403
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807418"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch 및 IErrorInfo 지원

템플릿 클래스를 사용할 수 있습니다 [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 의 기본 구현을 제공 하는 `IDispatch Interface` 개체에 이중 인터페이스의 일부입니다.

개체를 사용 하는 경우는 `IErrorInfo` 오류를 클라이언트에 다시 개체를 지원 해야 보고서에 대 한 인터페이스를 `ISupportErrorInfo Interface` 인터페이스입니다. 템플릿 클래스 [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) 개체에서 오류를 생성 하는 단일 인터페이스 하나만 있는 경우이 구현 하는 쉬운 방법을 제공 합니다.

## <a name="see-also"></a>참고자료

[ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)
