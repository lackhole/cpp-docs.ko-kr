---
title: 마샬링
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: 9963e261f26daa57cb58e30ffc404b431d781bfa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492039"
---
# <a name="marshaling"></a>마샬링

COM 기술인 마샬링은 개체가 어떤 프로세스에서 다른 프로세스에서 사용되는 인터페이스를 노출하는 것을 허용합니다. 마샬링에서 COM은 다른 프로세스(다른 프로세스는 다른 컴퓨터에서 실행 중인 프로세스를 포함)로 옮겨질 수 있는 형식으로 메서드의 매개 변수를 패키징하고 매개 변수를 언패키징하는 코드를 제공(또는 인터페이스 구현자가 제공하는 코드를 사용)합니다. 마찬가지로, COM은 호출에서 반환된 값에도 이와 동일한 단계를 수행해야 합니다.

> [!NOTE]
>  마샬링은 일반적으로 인터페이스가 제공되는 개체와 동일한 프로세스에서 사용된다면 필요하지 않습니다. 그러나 마샬링은 스레드 간에는 필요할 수 있습니다.

## <a name="see-also"></a>참고자료

[COM 소개](../atl/introduction-to-com.md)<br/>
[마샬링 정보](/windows/win32/com/marshaling-details)
