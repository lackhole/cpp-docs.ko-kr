---
title: C 런타임 오류 R6017
ms.date: 11/04/2016
f1_keywords:
- R6017
helpviewer_keywords:
- R6017
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
ms.openlocfilehash: 45f3b07f540cb72a955b19420130a5a806b750d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299662"
---
# <a name="c-runtime-error-r6017"></a>C 런타임 오류 R6017

예기치 않은 다중 스레드 잠금 오류입니다.

> [!NOTE]
> 앱을 실행 하는 동안이 오류 메시지를 발생 하는 경우 앱 종료가 내부 문제가 있기 때문입니다. 이 오류에 대 한 몇 가지 가능한 이유는 앱의 코드에서 결함으로 인 경우가 많습니다.
>
> 이 오류를 해결하려면 다음 단계를 시도할 수 있습니다.
>
> - 사용 하 여 합니다 **앱 및 기능** 또는 **프로그램 및 기능** 페이지를 **제어판** 를 복구 하거나 프로그램을 다시 설치 합니다.
> - 확인할 **Windows 업데이트** 에 **제어판** 소프트웨어 업데이트에 대 한 합니다.
> - 앱의 업데이트 된 버전을 확인 합니다. 문제가 지속 되는 경우 앱 공급 업체에 문의 합니다.

**프로그래머를 위한 정보**

C 런타임 다중 스레드 잠금을 시스템 리소스에 액세스 하는 동안 예기치 않은 오류가 수신 하는 프로세스입니다. 이 오류는 일반적으로 프로세스 런타임 힙에 데이터를 실수로 변경 하는 경우에 발생 합니다. 그러나 것 수 때문일 수도 런타임 라이브러리 또는 운영 체제 코드에 내부 오류가 발생 합니다.

이 문제를 해결 하려면 코드에서 힙 손상 버그를 확인 합니다. 자세한 내용 및 예제를 참조 하세요 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)합니다. 그런 다음, 앱 배포에 대 한 최신 재배포 가능 패키지를 사용 하 고 있는지 확인 합니다. 정보를 참조 하세요 [시각적 개체에 배포 C++ ](../../windows/deployment-in-visual-cpp.md)합니다.