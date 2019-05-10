---
title: 링커 입력 파일로 사용하는 .Obj 파일
ms.date: 12/29/2017
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
ms.openlocfilehash: c55c3181c2ddfabddce882a473e56d952a7e5d81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293279"
---
# <a name="obj-files-as-linker-input"></a>링커 입력 파일로 사용하는 .Obj 파일

링커 도구 (링크입니다. EXE).obj 파일에서 개체 파일 형식 COFF (공용)을 허용 합니다.

## <a name="remarks"></a>설명

Microsoft 공용 개체 파일 형식 한 전체 설명을 제공합니다. 자세한 내용은 [PE 형식](/windows/desktop/Debug/pe-format)합니다.

## <a name="unicode-support"></a>유니코드 지원

Visual Studio 2005 부터는 Microsoft MSVC 컴파일러에서는 유니코드 문자 식별자 ISO/IEC C에 정의 된 대로 및 C++ 표준입니다. 이전 버전의 컴파일러는 식별자에 ASCII 문자만 지원 합니다. 함수, 클래스 및 정적 변수 이름에 유니코드를 지원 하기 위해 컴파일러 및 링커에서의 유니코드 u t F-8 인코딩을 사용.obj 파일에 COFF 기호에 대 한 합니다. 인코딩을 u t F-8 이전 버전의 Visual Studio에서 사용 하는 ASCII 인코딩을 사용 하 여 만들어졌기 호환있지 않습니다.

컴파일러 및 링커에 대 한 자세한 내용은 참조 하세요. [컴파일러 및 링커에서의 유니코드 지원](unicode-support-in-the-compiler-and-linker.md)합니다. 유니코드 표준에 대 한 자세한 내용은 참조는 [유니코드](http://www.unicode.org/) 조직입니다.

## <a name="see-also"></a>참고자료

[LINK 입력 파일](link-input-files.md)<br/>
[MSVC 링커 옵션](linker-options.md)<br/>
[유니코드 지원](../../text/support-for-unicode.md)<br/>
[컴파일러 및 링커에서의 유니코드 지원](unicode-support-in-the-compiler-and-linker.md)<br/>
[유니코드 표준](http://www.unicode.org/)<br/>
[PE 형식](/windows/desktop/Debug/pe-format)
