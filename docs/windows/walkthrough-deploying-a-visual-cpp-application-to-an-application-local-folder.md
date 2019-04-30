---
title: 앱 로컬 폴더에 Visual C++ 애플리케이션 배포
ms.date: 04/23/2019
helpviewer_keywords:
- deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
ms.openlocfilehash: 33edf4bb736fad62928e11dd0550af6640d411ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387697"
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>연습: 애플리케이션 로컬 폴더에 Visual C++ 애플리케이션 배포

파일을 폴더에 복사하여 Visual C++ 애플리케이션을 배포하는 방법을 설명합니다.

## <a name="prerequisites"></a>전제 조건

- Visual Studio가 설치가 설치된 컴퓨터.

- Visual C++ 라이브러리가 없는 다른 컴퓨터.

### <a name="to-deploy-an-application-to-an-application-local-folder"></a>애플리케이션 로컬 폴더에 애플리케이션을 배포하려면

1. [연습: 설치 프로젝트를 사용하여 Visual C++ 애플리케이션 배포](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)의 단계를 수행하여 MFC 애플리케이션을 만들고 빌드합니다.

1. \\VC\\redist\\*version* 폴더의 Visual Studio 설치 디렉터리에서 MFC 및 CRT(C 런타임) 라이브러리 파일을 복사한 후 MFC 프로젝트의 \Release\ 폴더에 붙여넣습니다. 복사해야 하는 다른 파일에 대한 자세한 내용은 [재배포할 DLL 확인](determining-which-dlls-to-redistribute.md)을 참조하세요.

1. Visual C++ 라이브러리가 없는 두 번째 컴퓨터에서 MFC 애플리케이션을 실행합니다.

   1. \Release\ 폴더의 내용을 복사하여 두 번째 컴퓨터의 애플리케이션 폴더에 붙여 넣습니다.

   1. 두 번째 컴퓨터에서 애플리케이션을 실행합니다.

   Visual C++ 라이브러리를 애플리케이션 로컬 폴더에서 사용할 수 있으므로 애플리케이션이 성공적으로 실행됩니다.

## <a name="see-also"></a>참고자료

[배포 예제](deployment-examples.md)<br/>
