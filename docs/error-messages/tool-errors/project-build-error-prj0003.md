---
title: 프로젝트 빌드 오류 PRJ0003
ms.date: 11/04/2016
f1_keywords:
- PRJ0003
helpviewer_keywords:
- PRJ0003
ms.assetid: fc5a84bb-c6d3-41d6-8dd6-475455820778
ms.openlocfilehash: 00d101e62d49078ebfcfff9455497f30224b84fe
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039522"
---
# <a name="project-build-error-prj0003"></a>프로젝트 빌드 오류 PRJ0003

> 오류 생성 '*명령줄*'.

*명령줄* 명령에서 입력에서 형성 합니다 **속성 페이지** 대화 상자는 오류 코드를 반환 했지만에 아무 정보도 표시는 **출력** 창입니다.

이 오류의 가능한 원인은 다음과 같습니다.

- 프로젝트에 ATL 서버에 따라 달라 집니다. Visual Studio 2008부터 ATL 서버 더 이상 Visual Studio의 일부로 포함 되었지만 CodePlex에서 공유 소스 프로젝트로 놓았습니다. ATL 서버 소스 코드 및 도구를 다운로드 하려면로 이동 [ATL 서버 라이브러리 및 도구](http://go.microsoft.com/fwlink/p/?linkid=81979)합니다.

- 시스템 리소스가 부족 합니다. 이 해결 하려면 일부 응용 프로그램을 닫습니다.

- 보안 권한이 부족 합니다. 보안 권한이 있는지 확인 합니다.

- 에 지정 된 실행 파일 경로 **VC + + 디렉터리** 실행 하려고 하는 도구의 경로 포함 하지 않습니다. 내용은 [컴파일러 설정 및 빌드 속성](../../build/working-with-project-properties.md)

- 메이크파일 프로젝트에 대 한 중 하나에서 실행 하는 명령을 누락 **명령줄 빌드** 하거나 **다시 빌드 명령줄**합니다.

## <a name="see-also"></a>참고자료

[프로젝트 빌드 오류 및 경고(PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)