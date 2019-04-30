---
title: ATL 및 MFC 간의 선택에 대 한 권장 사항
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
ms.openlocfilehash: e4e51f81bbdc54ff09980acfba22037df77abac9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261340"
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>ATL 및 MFC 간의 선택에 대 한 권장 사항

구성 요소 및 응용 프로그램을 개발할 때에 두 가지 방법을 선택할 수 있습니다-ATL 및 MFC (Microsoft Foundation 클래스 라이브러리)입니다.

## <a name="using-atl"></a>ATL을 사용 하 여

ATL는 빠르고 쉬운 방법 둘 다에서 COM 구성 요소를 만듭니다 C++ 및 작은 사용 공간을 유지 관리 합니다. ATL을 사용 하 여 컨트롤을 만들려면 MFC 자동으로 제공 하는 기본 제공 기능을 모두 필요가 없는 경우.

## <a name="using-mfc"></a>MFC를 사용 하 여

MFC를 사용 하면 전체 응용 프로그램, ActiveX 컨트롤 및 액티브 문서를 만들 수 있습니다. MFC를 사용 하 여 컨트롤을 이미 만든 경우에 MFC의 개발을 계속 하는 것이 좋습니다. 새 컨트롤을 만들 때에 MFC의 기본 제공 기능을 모두 필요 하지 않으면 ATL을 사용 하는 것이 좋습니다.

## <a name="using-atl-in-an-mfc-project"></a>MFC 프로젝트에서 ATL을 사용 하 여

기존 MFC 프로젝트에서 ATL을 사용 하 여 마법사를 실행 하 여에 대 한 지원을 추가할 수 있습니다. 자세한 내용은 참조 하세요 [MFC 프로젝트에 ATL 지원 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md)합니다.

## <a name="see-also"></a>참고자료

[ATL 소개](../atl/introduction-to-atl.md)
