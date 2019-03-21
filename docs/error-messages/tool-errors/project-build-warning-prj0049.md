---
title: 프로젝트 빌드 경고 PRJ0049
ms.date: 11/04/2016
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
ms.openlocfilehash: fba3de0be764aa56b56ed22c6a9fde9366295456
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816232"
---
# <a name="project-build-warning-prj0049"></a>프로젝트 빌드 경고 PRJ0049

참조 된 대상 '\<참조 >'에.NET Framework \<MinFrameworkVersion >이 프로젝트의 대상 프레임 워크에서 실행 실패

Visual Studio 2008을 사용 하 여 만든 응용 프로그램 대상.NET Framework의 버전을 지정할 수 있습니다. 어셈블리 또는 프로젝트의 대상된 버전 보다 나중에.NET Framework 버전에 따라 달라 지는에 대 한 참조를 추가 하는 경우 컴파일 타임에이 경고가 표시 됩니다.

### <a name="to-correct-this-warning"></a>이 경고를 해결 하려면

1. 다음 중 하나를 선택합니다.

   - 프로젝트의 대상된 프레임 워크를 변경 **속성 페이지** 대화 상자는 최소 프레임 워크 버전의 모든 참조 된 어셈블리 및 프로젝트와 같거나 이후일 것입니다. 자세한 내용은 [참조 추가](../../build/adding-references-in-visual-cpp-projects.md)합니다.

   - 어셈블리 또는 프로젝트 대상된 프레임 워크 보다 나중에 최소 프레임 워크 버전에 대 한 참조를 제거 합니다. 이러한 항목을 프로젝트의 경고 아이콘을 사용 하 여 표시 됩니다 **속성 페이지**합니다.

## <a name="see-also"></a>참고 항목

[프로젝트 빌드 오류 및 경고(PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)