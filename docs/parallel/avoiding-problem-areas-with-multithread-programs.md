---
title: 다중 스레드 프로그램으로 문제 영역 방지
ms.date: 11/04/2016
helpviewer_keywords:
- multithreading [C++], troubleshooting
- errors [C++], multithreaded programs
- threading [C++], troubleshooting
- troubleshooting [C++], multithreading
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
ms.openlocfilehash: 3ceae832599243ffa0aad2b6fa67148e7ea30510
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62237066"
---
# <a name="avoiding-problem-areas-with-multithread-programs"></a>다중 스레드 프로그램으로 문제 영역 방지

다중 스레드 C 프로그램을 만들거나 링크하거나 실행할 때 발생할 수 있는 몇 가지 문제점이 있습니다. 다음 표에서는 자주 발생하는 몇 가지 문제에 대해 설명합니다. (MFC의 관점에서 유사한 내용은 참조 하세요. [다중 스레딩: 프로그래밍 팁](multithreading-programming-tips.md).)

|문제점|예상 원인|
|-------------|--------------------|
|프로그램에서 보호 위반이 발생했다는 메시지 상자가 표시됩니다.|많은 Win32 프로그래밍 오류로 인해 보호 위반이 발생합니다. 보호 위반의 일반적인 원인은 null 포인터에 데이터를 간접 할당하기 때문입니다. 결과적으로 프로그램이 자신에게 속하지 않는 메모리에 액세스를 시도하므로 보호 위반이 발생합니다.<br /><br /> 보호 위반의 원인을 쉽게 알아내는 방법은 디버깅 정보를 사용하여 프로그램을 컴파일한 다음 Visual C++ 환경의 디버거에서 프로그램을 실행하는 것입니다. 보호 오류가 발생하는 경우 Windows는 디버거에 컨트롤을 전송하고 문제가 발생한 줄에 커서를 놓습니다.|
|프로그램에서 컴파일 및 링크 오류가 많습니다.|컴파일러의 경고 수준을 가장 높은 값 중의 하나로 설정하고 경고 메시지에 주의하여 많은 잠재적 문제를 제거할 수 있습니다. 경고 수준 3 또는 경고 수준 4 옵션을 사용하여 실수에 의한 데이터 변환, 함수 프로토타입 누락 및 ANSI에서 지원하지 않는 기능 사용 등을 검색할 수 있습니다.|

## <a name="see-also"></a>참고자료

[C 및 Win32를 사용한 다중 스레딩](multithreading-with-c-and-win32.md)
