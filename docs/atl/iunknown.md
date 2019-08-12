---
title: IUnknown
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
ms.openlocfilehash: 17561092c6cccbad264bb82d68dbef9c0e078f76
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250297"
---
# <a name="iunknown"></a>IUnknown

[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)은 다른 모든 COM 인터페이스의 기반 인터페이스입니다.  이 인터페이스는 [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)), [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)및 [Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) 세 가지 메서드를 정의합니다. [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))를 통하여 인터페이스 사용자는 다른 인터페이스에 대한 포인터의 개체를 요청할 수 있습니다. [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref)와 [Release](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) 는 인터페이스에서 참조 횟수를 구현합니다.

## <a name="see-also"></a>참고자료

[COM 소개](../atl/introduction-to-com.md)<br/>
[IUnknown 및 인터페이스 상속](/windows/desktop/com/iunknown-and-interface-inheritance)
