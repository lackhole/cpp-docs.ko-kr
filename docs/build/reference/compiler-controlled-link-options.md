---
title: Compiler-Controlled LINK Options
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
ms.openlocfilehash: bc7a6cc596f138daa373042abca51642c24cf737
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822329"
---
# <a name="compiler-controlled-link-options"></a>Compiler-Controlled LINK Options

/C 옵션을 지정 하지 않으면 CL 컴파일러 링크를 자동으로 호출 합니다. CL 일부 제어 하 여 링커 명령줄 옵션 및 인수를 제공합니다. 다음 표에서 연결에 영향을 주는 CL 기능을 보여 줍니다.

|CL 사양|링크에 영향을 주는 CL 작업|
|----------------------|---------------------------------|
|.C,.cxx,.cpp 또는.def 이외의 모든 파일 이름 확장명|링크에 대 한 입력으로 파일 이름을 전달합니다.|
|*filename*.def|/DEF 전달:*filename*.def|
|/F*number*|/STACK 패스:*수*|
|/Fd*filename*|/PDB 전달:*파일 이름*|
|/Fe*filename*|전달/출력:*파일 이름*|
|/Fm*filename*|패스 /MAP:*파일 이름*|
|/Gy|패키지 함수 (Comdat);를 만듭니다. 함수 수준 링크 사용|
|/LD|/DLL 전달|
|/LDd|/DLL 전달|
|/link|링크 명령줄의 나머지 부분을 전달합니다.|
|/MD 또는 /MT|기본 라이브러리 이름을.obj 파일에 배치|
|/MTd 또는 /mdd|기본 라이브러리 이름을.obj 파일에 배치합니다. 기호를 정의 합니다 **_DEBUG**|
|/nologo|/NOLOGO 전달|
|/Zd|/DEBUG 전달|
|/Zi 또는/z7|/DEBUG 전달|
|/Zl|.Obj 파일에서 기본 라이브러리 이름 생략|

자세한 내용은 [MSVC 컴파일러 옵션](compiler-options.md)합니다.

## <a name="see-also"></a>참고자료

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
