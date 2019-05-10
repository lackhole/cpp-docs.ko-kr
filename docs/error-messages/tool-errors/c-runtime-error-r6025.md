---
title: C 런타임 오류 R6025
ms.date: 11/04/2016
f1_keywords:
- R6025
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
ms.openlocfilehash: 461bfb2aa46053ec56fff67de70038b1fcd97389
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62214170"
---
# <a name="c-runtime-error-r6025"></a>C 런타임 오류 R6025

순수 가상 함수 호출

> [!NOTE]
> 앱을 실행 하는 동안이 오류 메시지를 발생 하는 경우 앱 종료가 내부 문제가 있기 때문입니다. 이 오류에 대 한 가장 일반적인 이유는 앱 또는 손상 된 설치의 버그입니다.
>
> 이 오류를 해결하려면 다음 단계를 시도할 수 있습니다.
>
> - 사용 하 여 합니다 **앱 및 기능** 또는 **프로그램 및 기능** 페이지를 **제어판** 를 복구 하거나 프로그램을 다시 설치 합니다.
> - 확인할 **Windows 업데이트** 에 **제어판** 소프트웨어 업데이트에 대 한 합니다.
> - 앱의 업데이트 된 버전을 확인 합니다. 문제가 지속 되는 경우 앱 공급 업체에 문의 합니다.

**프로그래머를 위한 정보**

순수 가상 함수 호출을 처리할 수 없는 개체가 인스턴스화되지 합니다.

파생된 클래스의 형식으로 캐스트 하 여 생성 되지만 실제로 기본 클래스에 대 한 포인터는 포인터를 통해 추상 기본 클래스에는 가상 함수를 호출 하 여이 오류는 발생 합니다. 캐스트할 때 발생할 수 있습니다는 **void** <strong>\*</strong> 클래스에 대 한 포인터로 때 합니다 **void** <strong>\*</strong> 되었습니다 기본 클래스를 생성 하는 동안 만들어집니다.

