---
title: 예약어
ms.date: 11/04/2016
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
ms.openlocfilehash: 7d51f599dfb81dfa860e1bdba86c4372e80379fb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822446"
---
# <a name="reserved-words"></a>예약어

링커에 의해에서는 다음 단어가 예약 되어 있습니다. 이러한 이름은의 인수로 사용할 수 있습니다 [모듈 정의 문의](module-definition-dot-def-files.md) 이름을 큰따옴표로 묶은 경우에 ("").

||||
|-|-|-|
|**APPLOADER**<sup>1</sup>|**INITINSTANCE**<sup>2</sup>|**PRELOAD**|
|**BASE**|**IOPL**|**PRIVATE**|
|**CODE**|**LIBRARY**<sup>1</sup>|**PROTMODE**<sup>2</sup>|
|**준수**|**LOADONCALL**<sup>1</sup>|**PURE**<sup>1</sup>|
|**DATA**|**LONGNAMES**<sup>2</sup>|**READONLY**|
|**DESCRIPTION**|**MOVABLE**<sup>1</sup>|**READWRITE**|
|**DEV386**|**MOVEABLE**<sup>1</sup>|**REALMODE**<sup>1</sup>|
|**DISCARDABLE**|**MULTIPLE**|**RESIDENT**|
|**DYNAMIC**|**Name**|**RESIDENTNAME**<sup>1</sup>|
|**EXECUTE-ONLY**|**NEWFILES**<sup>2</sup>|**SECTIONS**|
|**EXECUTEONLY**|**NODATA**<sup>1</sup>|**SEGMENTS**|
|**EXECUTEREAD**|**NOIOPL**<sup>1</sup>|**SHARED**|
|**EXETYPE**|**NONAME**|**SINGLE**|
|**EXPORTS**|**표준에 맞지 않는**<sup>1</sup>|**STACKSIZE**|
|**고정**<sup>1</sup>|**NONDISCARDABLE**|**STUB**|
|**함수**<sup>2</sup>|**없음**|**VERSION**|
|**HEAPSIZE**|**비공유**|**WINDOWAPI**|
|**IMPORTS**|**NOTWINDOWCOMPAT**<sup>1</sup>|**WINDOWCOMPAT**|
|**IMPURE**<sup>1</sup>|**OBJECTS**|**WINDOWS**|
|**INCLUDE**<sup>2</sup>|**OLD**<sup>1</sup>||

<sup>1</sup> 링커가이 용어를 발견할 때 경고 ("무시")을 내보냅니다. 그러나 단어 여전히 예약 되어 있습니다.

<sup>2</sup> 링커가이 단어를 무시 하지만 없는 경고를 생성 합니다.

## <a name="see-also"></a>참고자료

- [MSVC 링커 참조](linking.md)
- [MSVC 링커 옵션](linker-options.md)