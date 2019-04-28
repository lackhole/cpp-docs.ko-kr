---
title: ATL 프로그램 또는 컨트롤 소스 및 헤더 파일
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], ATL source and headers
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
ms.openlocfilehash: e315586de57ca65c60c435c436734bcdededed54
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273029"
---
# <a name="atl-program-or-control-source-and-header-files"></a>ATL 프로그램 또는 컨트롤 소스 및 헤더 파일

Visual Studio에서 ATL 프로젝트를 만들 때, 생성하는 프로젝트에 대해 선택한 옵션에 따라 다음 파일이 생성됩니다.

이러한 파일은 모두 *Projname* 디렉터리와 솔루션 탐색기의 헤더 파일(.h 파일) 폴더 또는 원본 파일(.cpp 파일) 폴더에 있습니다.

|파일 이름|설명|
|---------------|-----------------|
|*Projname*.h|ATLSample.idl에 정의된 항목의 C++ 인터페이스 정의 및 GUID 선언이 포함된 주요 포함 파일입니다. 컴파일하는 동안 MIDL에 의해 다시 생성됩니다.|
|*Projname*.cpp|주 프로그램 원본 파일. in-process 서버용 DLL 내보내기 구현과 로컬 서버용 `WinMain` 구현이 포함되어 있습니다. 서비스의 경우 이는 모든 서비스 관리 기능을 추가로 구현합니다.|
|Resource.h|리소스 파일용 헤더 파일.|
|StdAfx.cpp|StdAfx.h 및 Atlimpl.cpp 파일을 포함합니다.|
|StdAfx.h|ATL 헤더 파일을 포함합니다.|

## <a name="see-also"></a>참고자료

[Visual C++ 프로젝트용 파일 형식](file-types-created-for-visual-cpp-projects.md)<br>
[MFC 프로그램 또는 컨트롤 소스 및 헤더 파일](mfc-program-or-control-source-and-header-files.md)<br>
[CLR 프로젝트](files-created-for-clr-projects.md)
