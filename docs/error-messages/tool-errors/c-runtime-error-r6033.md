---
title: C 런타임 오류 R6033
ms.date: 11/04/2016
f1_keywords:
- R6033
helpviewer_keywords:
- R6033
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
ms.openlocfilehash: 39d8a20dacb0cdeb2a767529e9716bd476f406dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400008"
---
# <a name="c-runtime-error-r6033"></a>C 런타임 오류 R6033

네이티브 코드를 초기화 하는 동안이 어셈블리의 MSIL 코드를 사용 하려고 합니다. 이 응용 프로그램에서 버그를 나타냅니다. MSIL로 컴파일된 호출의 결과 가능성이 높습니다 (/ clr) 기본 생성자에서 또는 DllMain 함수입니다.

> [!NOTE]
> 앱을 실행 하는 동안이 오류 메시지를 발생 하는 경우 앱 종료가 내부 문제가 있기 때문입니다. 이 오류는 앱에서 버그 또는 추가 기능이 나 사용 하는 확장의 버그로 인해 발생할 수 있습니다.
>
> 이 오류를 해결하려면 다음 단계를 시도할 수 있습니다.
>
> - 사용 하 여 합니다 **앱 및 기능** 또는 **프로그램 및 기능** 페이지를 **제어판** 를 복구 하거나 프로그램을 다시 설치 합니다.
> - 사용 합니다 **앱 및 기능** 또는 **프로그램 및 기능** 페이지를 **제어판** 제거, 복구 또는 확장 하거나 추가 기능을 다시 설치 합니다.
> - 확인할 **Windows 업데이트** 에 **제어판** 소프트웨어 업데이트에 대 한 합니다.
> - 앱의 업데이트 된 버전을 확인 합니다. 문제가 지속 되는 경우 앱 공급 업체에 문의 합니다.

**프로그래머를 위한 정보**

이 진단 로더 잠금 중 MSIL 명령을 실행 하는 것을 나타냅니다. 네이티브 컴파일한 경우 발생할 수 있습니다 C++ /clr 플래그를 사용 합니다. 만 /clr 플래그를 사용 하 여 관리 되는 코드를 포함 하는 모듈입니다. 자세한 내용은 [혼합 어셈블리 초기화](../../dotnet/initialization-of-mixed-assemblies.md)합니다.