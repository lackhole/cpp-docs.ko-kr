---
title: MFC MBCS DLL 추가 기능
ms.date: 05/08/2019
helpviewer_keywords:
- MBCS
- MFC
ms.openlocfilehash: 20145b200a0f8bac8ccb461331d4d233a3b0251e
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524812"
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL 추가 기능

MFC와 멀티 바이트 문자 집합(MBCS) 라이브러리의 지원을 위해 Visual Studio 2013 이상에서 Visual Studio를 설치하는 동안 추가 단계가 필요합니다.

**Visual Studio 2013**: 기본적으로 Visual Studio 2013에 설치된 MFC 라이브러리는 유니코드 개발만 지원합니다. **문자 집합** 속성이 **멀티 바이트 문자 집합 사용** 또는 **설정되지 않음**으로 설정된 Visual Studio 2013에서 MFC 프로젝트를 빌드하려면 MBCS DLL이 필요합니다. [Visual Studio 2013용 멀티 바이트 MFC 라이브러리](https://www.microsoft.com/download/details.aspx?id=40770)에서 DLL을 다운로드합니다.

**Visual Studio 2015**: Visual C++ 설치 구성 요소에 유니코드 및 MBCS MFC DLL이 모두 포함되어 있지만 기본적으로 MFC 지원은 설치되지 않습니다. Visual C++ 및 MFC는 Visual Studio 설치 프로그램에서 선택하여 설치합니다. MFC가 설치되었는지 확인하려면 설치 프로그램에서 **사용자 지정**을 선택하고 **프로그래밍 언어**에서 **Visual C++** 및 **C++용 Microsoft Foundation Classes**가 선택되어 있는지 확인합니다. Visual Studio를 이미 설치한 경우 MFC 프로젝트를 만들려고 하면 Visual C++ 및/또는 MFC를 설치하라는 메시지가 표시됩니다.

**Visual Studio 2017 이상**: **선택적 구성 요소** 창에서  **MFC 및 ATL 지원**을 선택하면 유니코드 및 MBCS MFC DLL이 **C++을 이용한 데스크톱 개발** 워크로드와 함께 설치됩니다. 설치에 이러한 구성요소가 포함되어 있지 않으면 **파일 | 새 프로젝트** 대화 상자를 열고 **Visual Studio 설치 관리자 열기** 링크를 클릭합니다.

## <a name="see-also"></a>참고자료

[MFC 라이브러리 버전](../mfc/mfc-library-versions.md)
