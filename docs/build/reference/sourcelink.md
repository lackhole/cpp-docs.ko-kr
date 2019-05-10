---
title: / SOURCELINK (Sourcelink 포함 파일 PDB)
ms.date: 08/20/2018
f1_keywords:
- /sourcelink
helpviewer_keywords:
- /SOURCELINK linker option
- /SOURCELINK
ms.openlocfilehash: 1643727d8f556a905eccbfa9626d1aaa8ea63cbf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317954"
---
# <a name="sourcelink-include-source-link-file-in-pdb"></a>/ SOURCELINK (PDB에 소스 링크 포함 파일)

링커에 의해 생성 되는 PDB 파일에 포함할 원본 연결 구성 파일을 지정 합니다.

## <a name="syntax"></a>구문

> **/ SOURCELINK:**_파일 이름_

## <a name="arguments"></a>인수

*filename*<br/>
JSON 형식의 구성 파일을 지정 로컬 파일 경로를 Url의 간단한 매핑을 포함 하는 소스 파일을 검색할 수 있는 디버거에 의해 표시 합니다. 이 파일의 형식에 자세한 내용은 참조 [소스 링크 JSON 스키마](https://github.com/dotnet/designs/blob/master/accepted/diagnostics/source-link.md#source-link-json-schema)합니다.

## <a name="remarks"></a>설명

소스 링크는 소스 이진 파일에 대 한 디버깅을 제공 하기 위한 언어 및 소스 제어 알 수 없는 시스템. 네이티브에 대 한 소스 링크가 지원 됩니다 C++ Visual Studio 2017 버전 15.8에서에서 시작 하는 이진 파일. 소스 링크의 개요를 보려면 [소스 링크](https://github.com/dotnet/designs/blob/master/accepted/diagnostics/source-link.md)합니다. 프로젝트에서 소스 링크를 사용 하는 방법 및 프로젝트의 일부로 SourceLink 파일을 생성 하는 방법에 대 한 내용은 참조 하세요 [소스 링크를 사용 하 여](https://github.com/dotnet/sourcelink#using-source-link-in-c-projects)입니다.

### <a name="to-set-the-sourcelink-linker-option-in-visual-studio"></a>Visual Studio에서 /SOURCELINK 링커 옵션을 설정 하려면

1. 엽니다는 **속성 페이지** 프로젝트에 대 한 대화 상자. 자세한 내용은 [Visual Studio에서 설정 C++ 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 에 **추가 옵션** 상자에서 추가 **/SOURCELINK:**_filename_ 를 선택한 후 **확인** 또는 **적용**변경 내용을 저장 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- 이 옵션에 프로그래밍 방식으로 해당 하는 없습니다.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
