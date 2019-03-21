---
title: '찾아보기 정보 파일 빌드: 개요'
ms.date: 11/04/2016
helpviewer_keywords:
- .bsc files, about .bsc files
- bsc files, about bsc files
- browse information files (.bsc)
- browse information files (.bsc), creating
ms.assetid: b5c12832-51f6-4953-8044-4264dd0fb242
ms.openlocfilehash: 4f12bd25ca3ab718a845dbb04aba3169cc6d4b19
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820624"
---
# <a name="building-browse-information-files-overview"></a>찾아보기 정보 파일 빌드: 개요

기호 검색에 대 한 찾아보기 정보를 만들려면 컴파일러 BSCMAKE 다음 프로젝트에서 각 소스 파일에 대 한.sbr 파일을 만듭니다. EXE는.bsc 파일 하나로.sbr 파일을 연결합니다.

.Sbr 및.bsc 파일을 생성 시간이, Visual c + + 기본적으로 이러한 함수를 설정 하도록 합니다. 현재 정보를 검색 하려는 경우 찾아보기 옵션을 설정 하 고 프로젝트를 다시 작성 해야 합니다.

사용 하 여 [/FR](fr-fr-create-dot-sbr-file.md) 하거나 [/Fr](fr-fr-create-dot-sbr-file.md) .sbr 파일을 만드는 컴파일러에 지시 합니다. .Bsc 파일을 만들려면 호출할 수 있습니다 [BSCMAKE](bscmake-command-line.md) 명령줄에서. BSCMAKE를 사용 하 여 명령줄에서 보다 자세히 제어할 찾아보기 정보 파일 조작 제공 합니다. 참조 [BSCMAKE 참조](bscmake-reference.md) 자세한 내용은 합니다.

> [!TIP]
>  .Sbr 파일 생성에 선택할 수 있지만 해제.bsc 파일 생성을 그대로 둡니다. 이 제공 빠른 빌드 하지만.bsc 파일 생성 설정 하 고 프로젝트를 작성 하 여 새.bsc 파일을 신속 하 게 만들 수 있습니다.

시간, 메모리 및.bsc 파일의 크기를 줄여.bsc 파일을 빌드하는 데 필요한 디스크 공간을 줄일 수 있습니다.

참조 [일반 속성 페이지 (프로젝트)](general-property-page-project.md) 개발 환경에서 브라우저 파일을 작성 하는 방법에 대 한 정보에 대 한 합니다.

### <a name="to-create-a-smaller-bsc-file"></a>더 작은.bsc 파일을 만들려면

1. 사용 하 여 [BSCMAKE 명령줄 옵션](bscmake-options.md) 에 찾아보기 정보 파일에서 정보를 제외 합니다.

1. 하나 이상의.sbr 파일 컴파일 또는 어셈블할 때 로컬 기호를 생략 합니다.

1. 개체 파일에 디버깅에 현재 단계에 필요한 정보가 없으면 찾아보기 정보 파일을 다시 빌드할 때 BSCMAKE 명령에서 해당.sbr 파일을 생략 합니다.

### <a name="to-combine-the-browse-information-from-several-projects-into-one-browser-file-bsc"></a>하나의 브라우저 파일 (.bsc)에 여러 프로젝트에서 찾아보기 정보를 결합

1. 중 하나는 프로젝트 수준에서.bsc 파일 빌드 또는.sbr 파일이 잘리지 않도록 하려면 /n 스위치를 사용 하지 마세요.

1. 모든 프로젝트를 빌드한 후는 입력으로 모든.sbr 파일이 BSCMAKE를 실행 합니다. 와일드 카드가 허용 됩니다. 예를 들어 서.bsc 파일 하나에 모두 결합 하려면에서.sbr 파일을 사용 하 여 프로젝트 디렉터리 C:\X, C:\Y, 및 C:\Z을 설치한 경우 다음 사용 하 여 BSCMAKE C:\X\\\*.sbr C:\Y\\\*.sbr C:\Z\\ \*.sbr /o c:\whatever_directory\combined.bsc 결합된.bsc 파일을 빌드합니다.

## <a name="see-also"></a>참고자료

[추가 MSVC 빌드 도구](c-cpp-build-tools.md)<br/>
[BSCMAKE 참조](bscmake-reference.md)
