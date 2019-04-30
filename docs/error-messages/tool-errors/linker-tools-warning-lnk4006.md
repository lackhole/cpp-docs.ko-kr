---
title: 링커 도구 경고 LNK4006
ms.date: 11/04/2016
f1_keywords:
- LNK4006
helpviewer_keywords:
- LNK4006
ms.assetid: 3a637d17-1676-4ea6-bd8b-290137d28d3b
ms.openlocfilehash: c81c93a6df8c7eef809f243e3dc56164ea548371
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187143"
---
# <a name="linker-tools-warning-lnk4006"></a>링커 도구 경고 LNK4006

개체에 이미 정의 된 기호 두 번째 정의가 무시 됩니다.

데코레이팅된 폼으로 표시되는 해당 `symbol` 기호는 여러 번 정의되었습니다. 이 경고가 발생 하면 `symbol` 을 두 번 추가 되지만 해당 첫 번째 폼에만 사용 됩니다.

두 개의 가져오기 라이브러리를 하나로 병합 하려는 경우이 경고를 가져올 수 있습니다.

C 런타임 라이브러리를 다시 작성 하는 경우에이 메시지를 무시할 수 있습니다.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.

1. 지정 된 `symbol` 사용해 컴파일하여 만든 패키지 함수로, 않을 [/Gy](../../build/reference/gy-enable-function-level-linking.md)합니다. 이 기호가 둘 이상의 파일에 포함 되어 있지만 컴파일 간에 변경 되었습니다. 포함 된 모든 파일을 다시 컴파일해야 합니다 `symbol`합니다.

1. 지정 된 `symbol` 있습니다 다르게 정의 되어 다른 라이브러리에서 두 멤버 개체에 있습니다.

1. 절대 정의 되어 있습니다을 두 번 각 정의에서 다른 값을 사용 하 여 합니다.

1. 라이브러리를 결합 하는 경우 오류 메시지를 받을 경우 `symbol` 추가할 라이브러리에 이미 있습니다.