---
title: 'MFC 응용 프로그램의 지역화 된 리소스: 위성 Dll'
ms.date: 11/04/2016
helpviewer_keywords:
- multiple language support [C++]
- localization [C++], MFC resources
- localized resources [C++]
- MFC DLLs [C++], localizing
- DLLs [C++], localizing MFC
- resources [MFC], localizing
- resource-only DLLs [C++]
- resource-only DLLs [C++], MFC applications
- satellite DLLs [C++]
ms.assetid: 3a1100ae-a9c8-47b5-adbd-cbedef5992ef
ms.openlocfilehash: c593d0bae6fc23cfd765116c44b07caa2a6d8ccf
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821328"
---
# <a name="localized-resources-in-mfc-applications-satellite-dlls"></a>MFC 응용 프로그램의 지역화 된 리소스: 위성 Dll

MFC 버전 7.0 이상 위성 Dll 여러 언어로 지역화 된 응용 프로그램을 만드는 데 도움이 되는 기능에 대 한 향상 된 지원을 제공 합니다. 위성 DLL은는 [리소스 전용 DLL](creating-a-resource-only-dll.md) 특정 언어에 대해 지역화 된 응용 프로그램의 리소스를 포함 하는 합니다. 응용 프로그램 실행을 시작할 때 MFC 환경에 가장 적합 한 지역화 된 리소스를 자동으로 로드 합니다. 예를 들어 두 위성 리소스는 독일어로 번역을 포함 하며 다른을 프랑스어 번역을 포함 하는 Dll 사용 하 여 영어 리소스를 사용 하 여 응용 프로그램에 있을 수 있습니다. 응용 프로그램 영어 시스템에서 실행 되 면 영어 리소스를 사용 합니다. 프랑스어 리소스를 사용 하 여 프랑스어 시스템을 실행 하는 경우 독일어 시스템에서 실행할 경우 독일어 리소스를 사용 합니다.

위성 DLL을 로드 하려고 하는 MFC MFC 응용 프로그램에서 지역화 된 리소스를 지원 하기 위해이 특정 언어에 지역화 된 리소스를 포함 하 합니다. 위성 Dll 라고 *ApplicationNameXXX*.dll, 여기서 *ApplicationName* .exe 또는.dll MFC를 사용 하 여 이름 및 *XXX* 언어에 대 한 세 문자로 된 코드는 리소스 (예: '한국어' 또는 'DEU').

MFC를 발견할 때 중지 순서로 다음 언어에 대 한 리소스 DLL를 로드 하려고 합니다.

1. 현재 사용자의 기본 UI 언어를 GetUserDefaultUILanguage() Win32 API에서 반환 되는 것입니다.

1. 특정 보조 언어 없이 현재 사용자의 기본 UI 언어 (즉, ENC [캐나다 영어]가 [미국 한국어 영어])입니다.

1. 시스템의 기본 UI 언어를 GetSystemDefaultUILanguage() API에서 반환 되는 것입니다. 다른 플랫폼에서 자체 운영 체제의 언어입니다.

1. 시스템의 기본 UI 언어에서 특정 보조 언어 없이 합니다.

1. LOC. 3 문자 코드를 사용 하 여 가짜 언어

MFC 위성 Dll을 찾을 수 없는 경우 응용 프로그램 자체에 포함 된 리소스를 사용 합니다.

예를 들어 LangExample.exe 응용 프로그램 MFC를 사용 하는 여러 사용자 인터페이스 시스템에서 실행 되 고 가정 시스템 UI 언어는 한국어 [미국 영어] 현재 사용자의 UI 언어 FRC [캐나다 프랑스어]로 설정 됩니다. 다음 순서 대로 다음 Dll에 대 한 MFC 표시 됩니다.

1. LangExampleFRC.dll (사용자의 UI 언어)입니다.

1. LangExampleFRA.dll (이 예에서는 프랑스어 (프랑스)에 보조 언어 없이 사용자의 UI 언어입니다.

1. LangExampleENU.dll (시스템의 UI 언어)입니다.

1. LangExampleLOC.dll.

이러한 Dll의 일치 항목이 없는 경우, MFC LangExample.exe의 리소스를 사용 합니다.

## <a name="see-also"></a>참고자료

[Visual C++의 DLL](dlls-in-visual-cpp.md)<br/>
[TN057: 지역화 된 MFC 구성 요소](../mfc/tn057-localization-of-mfc-components.md)
