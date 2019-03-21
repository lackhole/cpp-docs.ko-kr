---
title: 지연 로드된 가져오기 덤프
ms.date: 11/04/2016
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
ms.openlocfilehash: 368c6b851340dd2a39df9a758f15d52ff5104479
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809914"
---
# <a name="dumping-delay-loaded-imports"></a>지연 로드된 가져오기 덤프

지연 로드된 가져오기는 [/imports dumpbin](imports-dumpbin.md)를 사용하여 덤프될 수 있으며 표준 가져오기와 약간 다른 내용을 표시합니다. 지연 로드된 가져오기는 자체의 /imports 덤프 섹션으로 분리되고 지연 로드된 가져오기라는 레이블이 명시적으로 붙습니다. 이미지에 언로드 정보가 있으면 해당 내용이 기록되며 바인드 정보가 있으면 대상 DLL의 날짜/시간 스탬프가 바인딩된 가져오기 주소와 함께 기록됩니다.

## <a name="see-also"></a>참고자료

[링커의 지연 로드된 DLL 지원](linker-support-for-delay-loaded-dlls.md)
