---
title: Naked 함수 호출
ms.date: 11/04/2016
helpviewer_keywords:
- virtual device drivers
- VXD virtual device drivers
- virtual device drivers, naked function calls
- naked functions
- prolog code
- epilog code
- naked keyword [C++]
- naked keyword [C++], storage-class attribute
ms.assetid: 2a66847a-a43f-4541-a7be-c9f5f29b5fdb
ms.openlocfilehash: f9d8a8747d4a808d040b814005782ed8187bf274
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301580"
---
# <a name="naked-function-calls"></a>Naked 함수 호출

## <a name="microsoft-specific"></a>Microsoft 전용

으로 선언 된 함수는 **naked** 프롤로그 또는 에필로그 코드를 사용 하 여 사용자 고유의 사용자 지정 프롤로그/에필로그 시퀀스를 작성 하는 데 사용할 수 없는 특성 내보내집니다 합니다 [인라인 어셈블러](../assembler/inline/inline-assembler.md)합니다. Naked 함수는 고급 기능으로 제공됩니다. 이 함수를 통해 C/C++ 이외의 컨텍스트에서 호출되는 함수를 선언할 수 있으므로 매개 변수의 위치와 유지되고 있는 레지스터에 대한 다양한 가정을 만들 수 있습니다. 예시에는 인터럽트 처리기와 같은 루틴이 포함됩니다. 이러한 기능은 VxD(가상 장치 드라이버) 작성에 특히 유용합니다.

## <a name="what-do-you-want-to-know-more-about"></a>추가 정보

- [naked](../cpp/naked-cpp.md)

- [Naked 함수의 규칙 및 제한](../cpp/rules-and-limitations-for-naked-functions.md)

- [프롤로그-에필로그 코드 작성 시 고려 사항](../cpp/considerations-for-writing-prolog-epilog-code.md)

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[호출 규칙](../cpp/calling-conventions.md)