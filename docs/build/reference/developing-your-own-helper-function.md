---
title: 사용자 도우미 함수 개발
ms.date: 11/04/2016
helpviewer_keywords:
- helper functions
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
ms.openlocfilehash: 73b4a8180345dd6f7dc26f4243f6e63eda80e4af
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820142"
---
# <a name="developing-your-own-helper-function"></a>사용자 도우미 함수 개발

사용자 고유의 버전 가져오기 DLL의 이름을 기반으로 하는 특정 처리를 수행 하는 루틴을 제공 하려는 경우. 이 작업을 수행 하는 방법은 두 가지가 있습니다: 코딩 직접 제공된 된 코드에 따라 또는 단순히 이전에 설명한 알림 후크를 사용 하 여 제공 된 버전을 연결 합니다.

## <a name="code-your-own"></a>코드 작성

새 리소스에 대 한 지침으로 제공된 된 코드를 기본적으로 사용할 수 있으므로 매우 간단 합니다. 물론, 호출 규칙을 따라야 합니다 및는 링커 생성 한 썽크를 반환 하는 경우 적절 한 함수 포인터를 반환 해야 합니다. 한 번 코드에서 호출을 충족 하거나 호출을 최대한 원하는 대로 거의 수행할 수 있습니다.

## <a name="use-the-start-processing-notification-hook"></a>알림 후크 처리 시작 사용

아마도 가장 dlistartprocessing 알림의 기본 도우미와 동일한 값을 수신 하는 사용자가 제공한 알림 후크 함수에 대 한 새 포인터를 제공 하기만 하면 됩니다. 이 시점에서 후크 함수 해질 수 있으며 기본적으로 새 도우미 함수를 기본 도우미의 모든 추가 처리가 기본 도우미 반환이 성공적 이면을 바이패스 합니다.

## <a name="see-also"></a>참고자료

[링커의 지연 로드된 DLL 지원](linker-support-for-delay-loaded-dlls.md)
