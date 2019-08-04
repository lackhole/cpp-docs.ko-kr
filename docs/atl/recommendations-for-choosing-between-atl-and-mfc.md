---
title: ATL 및 MFC 간의 선택에 대한 권장사항
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
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>ATL 및 MFC 간의 선택에 대한 권장사항

구성 요소 및 응용 프로그램을 개발할 때 ATL 및 MFC (Microsoft Foundation Class 라이브러리) 두 가지 방법 중 하나를 선택할 수 있습니다.

## <a name="using-atl"></a>ATL을 사용

ATL는 C++을 이용하여 작은 사용 공간을 유지하는 COM 구성요소를 만드는 쉽고 빠른 방법입니다. MFC가 자동으로 제공하는 모든 기본 제공 기능이 필요하지 않은 경우 ATL을 사용하여 컨트롤을 만듭니다.

## <a name="using-mfc"></a>MFC를 사용

MFC를 사용하면 응용 프로그램 전체, ActiveX 컨트롤 및 액티브 문서를 만들 수 있습니다. 이미 MFC를 사용하여 컨트롤을 만든 경우에 MFC의 개발을 계속하는 것이 좋습니다. 새 컨트롤을 만들 때 MFC의 기본 제공 기능이 모두 필요 하지 않는다면 ATL을 사용 하는 것이 좋습니다.

## <a name="using-atl-in-an-mfc-project"></a>MFC 프로젝트에서 ATL을 사용

마법사를 실행하여 기존 MFC 프로젝트에서 ATL을 사용하도록 지원을 추가할 수 있습니다. 자세한 내용은 [MFC 프로젝트에 ATL 지원 추가](../mfc/reference/adding-atl-support-to-your-mfc-project.md)를 참조합니다.

## <a name="see-also"></a>참고자료

[ATL 소개](../atl/introduction-to-atl.md)
