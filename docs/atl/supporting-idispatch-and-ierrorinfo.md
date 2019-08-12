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
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342032"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>IDispatch 및 IErrorInfo 지원

템플릿 클래스 [IDispatchImpl](../atl/reference/idispatchimpl-class.md)을 사용하여 구현하는 개체의 모든 이중 인터페이스에서 `IDispatch Interface` 부분의 기본 구현을 제공할 수 있습니다.

개체가 클라이언트에게 오류를 보고하기 위해 `IErrorInfo` 인터페이스를 사용하는 경우 개체는 반드시 `ISupportErrorInfo Interface` 인터페이스를 지원해야 합니다. 템플릿 클래스 [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md)은 개체에서 오류를 생성하는 단일 인터페이스 하나만 있는 경우 이를 구현할 수 있는 쉬운 방법을 제공합니다.

## <a name="see-also"></a>참고자료

[ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)
