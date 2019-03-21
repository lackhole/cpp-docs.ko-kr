---
title: ATL 프로젝트에서 CRT에 연결
ms.date: 11/04/2016
helpviewer_keywords:
- CRT, linking with ATL
- WinMainCRTStartup method
- DllMainCRTStartup method
- wWinMainCRTStartup method
- ATL, C Run-Time library (CRT)
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
ms.openlocfilehash: e247897f42eea5b4ced5bc40b556137a1a5cd228
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820184"
---
# <a name="linking-to-the-crt-in-your-atl-project"></a>ATL 프로젝트에서 CRT에 연결

합니다 [C 런타임 라이브러리](../c-runtime-library/crt-library-features.md) (CRT) 만들 수 있는 프로그래밍 훨씬 더 쉽게 ATL 개발 하는 동안 많은 유용한 기능을 제공 합니다. 모든 ATL 프로젝트는 CRT 라이브러리에 연결합니다. 메서드를 연결의 장단점을 볼 수 있습니다 [CRT에 연결할 메서드 사용의 장단점](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md)합니다.

## <a name="effects-of-linking-to-the-crt-on-your-program-image"></a>프로그램 이미지에서 CRT에 연결 하는 효과

정적으로 CRT에 링크를 CRT에서 코드 실행 가능 이미지에 배치 되 고 이미지를 실행 하는 시스템에 있는 CRT DLL을 할 필요가 없습니다. 동적으로 CRT에 링크 하면 CRT DLL의 코드에 대 한 참조 이미지를 하지만 코드 자체에 배치 됩니다. 지정된 된 시스템에서 실행 하 여 이미지에 대 한 순서로 CRT DLL 해당 시스템에 있어야 합니다. 도 때 동적으로 CRT에 연결할 수 있습니다 일부 코드를 정적으로 연결할 수 있는지 (예를 들어 `DllMainCRTStartup`).

이미지를 연결 하면 명시적 또는 암시적으로 지정할 운영 체제 이미지를 로드 한 후에 호출 하는 진입점입니다. 기본 진입점은 dll의 경우 `DllMainCRTStartup`합니다. EXE, `WinMainCRTStartup`합니다. /ENTRY 링커 옵션을 사용 하 여 기본값을 재정의할 수 있습니다. CRT에 대 한 구현을 제공 `DllMainCRTStartup`하십시오 `WinMainCRTStartup`, 및 `wWinMainCRTStartup` (유니코드 진입점 exe). 이러한 CRT 제공한 진입점 전역 개체의 생성자를 호출 하 고 일부 CRT 함수에 의해 사용 되는 기타 데이터 구조를 초기화 합니다. 이 시작 코드는 정적으로 연결 된 경우 약 25 K 이미지에 추가 합니다. 동적으로 링크 된 DLL의 대부분의 코드 이므로 이미지 크기가 작게 유지 합니다.

자세한 내용은 링커 항목을 참조 하세요 [/ENTRY (진입점 기호)](../build/reference/entry-entry-point-symbol.md)합니다.

## <a name="optimization-options"></a>최적화 옵션

/ Opt:nowin98 링커 옵션을 사용 하 여 더 줄일 수 있습니다을 10k 기본 ATL 컨트롤 복제할지 Windows 98 시스템으로 로드 증가 합니다. 연결 옵션에 대 한 자세한 내용은 참조 하세요. [/OPT (최적화)](../build/reference/opt-optimizations.md)합니다.

## <a name="see-also"></a>참고자료

[ATL 및 C 런타임 코드를 사용한 프로그래밍](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[DLL 및 Visual C++ 런타임 라이브러리 동작](../build/run-time-library-behavior.md)
