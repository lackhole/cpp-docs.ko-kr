---
title: 다중 스레드 프로그램
ms.date: 11/04/2016
helpviewer_keywords:
- threading [C++], about threading
- multithreading [C++], about threads
ms.assetid: 02443596-f7e1-48d0-b3a4-39ee0e54e444
ms.openlocfilehash: fd10893ecd33d39b531b9451dec708ea31c121d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407824"
---
# <a name="multithread-programs"></a>다중 스레드 프로그램

스레드는 기본적으로 프로그램 전체의 실행 경로이며. Win32에서 일정을 예약하는 최소 실행 단위이기도 합니다. 스레드는 스택, CPU 레지스터 상태 및 시스템 스케줄러 실행 목록의 엔트리로 구성됩니다. 각 스레드는 프로세스의 모든 리소스를 공유합니다.

프로세스는 한 개 이상의 스레드, 코드, 데이터 및 메모리에 있는 기타 프로그램 리소스로 구성됩니다. 일반적인 프로그램 리소스는 열린 파일, 세마포 및 동적 할당 메모리입니다. 시스템 스케줄러가 스레드 실행 컨트롤 중 하나를 제공하면 프로그램이 실행됩니다. 스케줄러는 실행해야 할 스레드 및 스레드 실행 시기를 결정합니다. 우선 순위가 낮은 스레드는 우선 순위가 높은 스레드가 작업을 완료할 때까지 기다려야 할 수도 있습니다. 다중 프로세서 컴퓨터에서 스케줄러는 CPU 작업량을 균형있게 분배하기 위해 개별 스레드를 다른 프로세서로 이동할 수 있습니다.

한 프로세스에서 각 스레드는 독립적으로 작동합니다. 다른 스레드를 볼 수 있도록 설정하지 않으면 스레드는 개별적으로 실행되며 한 프로세스에서 다른 스레드를 인식하지 못합니다. 그러나 공용 리소스를 공유하는 스레드는 세마포 또는 기타 프로세스간 통신 방법을 사용하여 작업을 조정해야 합니다. 스레드 동기화에 대한 자세한 내용은 [다중 스레드 Win32 프로그램 작성](writing-a-multithreaded-win32-program.md)을 참조하십시오.

## <a name="see-also"></a>참고자료

[C 및 Win32를 사용한 다중 스레딩](multithreading-with-c-and-win32.md)
