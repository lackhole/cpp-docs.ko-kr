---
title: 예외 처리기에 대한 제한
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 7d5bf20da61f4b9f5012b7f2aab932dfc904c302
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403362"
---
# <a name="restrictions-on-exception-handlers"></a>예외 처리기에 대한 제한

코드에서 예외 처리기를 사용할 때의 주요 제한 사항은 **goto** 문을 사용하여 **__try** 문 블록으로 이동할 수 없다는 점입니다. 대신, 정상적인 제어 흐름을 통해 문 블록에 들어가야 합니다. **__try** 문 블록의 외부로 이동할 수 있으며 선택한 예외 처리기를 중첩할 수 있습니다.

## <a name="see-also"></a>참고

[예외 처리기 작성](../cpp/writing-an-exception-handler.md)<br/>
[구조적 예외 처리(C/C++)](../cpp/structured-exception-handling-c-cpp.md)