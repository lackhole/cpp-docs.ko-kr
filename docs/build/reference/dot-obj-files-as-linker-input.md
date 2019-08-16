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
ms.openlocfilehash: 3e02ccc09ae8c9c2f3df88bc1767ff0188baa1f4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492933"
---
# <a name="obj-files-as-linker-input"></a>링커 입력 파일로 사용하는 .Obj 파일

링커 도구 (링크)입니다. EXE)는 COFF (Common Object File Format)에 있는 .obj 파일을 허용 합니다.

## <a name="remarks"></a>설명

Microsoft에서는 일반적인 개체 파일 형식에 대 한 전체 설명을 제공 합니다. 자세한 내용은 [PE 형식](/windows/win32/Debug/pe-format)을 참조 하세요.

## <a name="unicode-support"></a>유니코드 지원

Visual Studio 2005부터 Microsoft MSVC 컴파일러는 ISO/IEC C 및 C++ 표준에 정의 된 대로 식별자의 유니코드 문자를 지원 합니다. 이전 버전의 컴파일러는 식별자에서 ASCII 문자만 지원 했습니다. 함수, 클래스 및 정적 이름에서 유니코드를 지원 하기 위해 컴파일러와 링커는 .obj 파일의 COFF 기호에 유니코드 UTF-8 인코딩을 사용 합니다. UTF-8 인코딩은 이전 버전의 Visual Studio에서 사용 하는 ASCII 인코딩과 upwardly 호환 됩니다.

컴파일러 및 링커에 대 한 자세한 내용은 [컴파일러 및 링커의 유니코드 지원](unicode-support-in-the-compiler-and-linker.md)을 참조 하세요. 유니코드 표준에 대 한 자세한 내용은 [유니코드](https://www.unicode.org/) 조직을 참조 하세요.

## <a name="see-also"></a>참고자료

[LINK 입력 파일](link-input-files.md)<br/>
[MSVC 링커 옵션](linker-options.md)<br/>
[유니코드 지원](../../text/support-for-unicode.md)<br/>
[컴파일러 및 링커에서의 유니코드 지원](unicode-support-in-the-compiler-and-linker.md)<br/>
[유니코드 표준](https://www.unicode.org/)<br/>
[PE 형식](/windows/win32/Debug/pe-format)
