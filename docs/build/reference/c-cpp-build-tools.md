---
title: 추가 MSVC 빌드 도구
ms.date: 08/28/2019
f1_keywords:
- c.build
helpviewer_keywords:
- builds [C++], C/C++ tools
- tools [C++], build
ms.assetid: 48d9daf4-6bbf-473a-8ce2-bf2923b69f80
ms.openlocfilehash: 53c7c2f8c162cd851b4612e75ba14b019d9cbd63
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177289"
---
# <a name="additional-msvc-build-tools"></a>추가 MSVC 빌드 도구

Visual Studio는 빌드 출력을 보거나 조작 하기 위한 다음 명령줄 유틸리티를 제공 합니다.

- [LIB. EXE](lib-reference.md) 는 COFF (Common Object File Format) 개체 파일의 라이브러리를 만들고 관리 하는 데 사용 됩니다. 내보내기 파일을 만들고 내보낸 정의를 참조 하는 라이브러리를 가져오는 데에도 사용할 수 있습니다.

- [EDITBIN. EXE](editbin-reference.md) 를 사용 하 여 COFF 이진 파일을 수정할 수 있습니다.

- [DUMPBIN. EXE](dumpbin-reference.md) COFF 이진 파일에 대 한 정보 (예: 기호 테이블)를 표시 합니다.

- [NMAKE](nmake-reference.md) 는 메이크파일을 읽고 실행 합니다.

- 오류 조회 유틸리티인 [ERRLOOK](value-edit-control.md)는 입력 된 값에 따라 시스템 오류 메시지 또는 모듈 오류 메시지를 검색 합니다.

- [XDCMake](xdcmake-reference.md). XML 태그로 표시 된 문서 주석을 포함 하는 소스 코드 파일을 처리 하기 위한 도구입니다.

- [BSCMAKE. ](bscmake-reference.md)이전 버전과의 호환성을 위해서만 제공 되는 EXE는 프로그램의 기호 (클래스, 함수, 데이터, 매크로 및 형식)에 대 한 정보를 포함 하는 찾아보기 정보 파일 (.bsc)을 빌드합니다. 개발 환경 내에서 찾아보기 창에서이 정보를 볼 수 있습니다. (.Bsc 파일은 개발 환경에서 빌드할 수도 있습니다.)

또한 Windows SDK에는 RC를 비롯 한 몇 가지 빌드 도구도 있습니다 [. EXE](/windows/win32/menurc/resource-compiler): 대화 상자 C++ , 속성 페이지, 비트맵, 문자열 테이블 등의 네이티브 Windows 리소스를 컴파일하기 위해 컴파일러가 호출 합니다.

## <a name="see-also"></a>참고자료

[C/C++ 빌드 참조](c-cpp-building-reference.md)<br/>
[데코레이팅된 이름](decorated-names.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 링커 옵션](linker-options.md)
