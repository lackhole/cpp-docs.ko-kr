---
title: 'MIDL 속성 페이지: 고급'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ValidateParameters
helpviewer_keywords:
- MIDL, property pages
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
ms.openlocfilehash: 350563d140823910667812930f9283c7640cc1ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321477"
---
# <a name="midl-property-pages-advanced"></a>MIDL 속성 페이지: 고급

**MIDL** 폴더의 **고급** 속성 페이지에서 다음 MIDL 컴파일러 옵션을 지정합니다.

- 오류 검사 사용([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- 할당 검사([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- 경계 검사([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- 열거형 범위 검사([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- 참조 포인터 검사([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- 스텁 데이터 검사([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- 매개 변수 유효성 검사([/robust](https://msdn.microsoft.com/library/windows/desktop/aa367363)) \*

- 구조체 멤버 맞춤([/Zp](https://msdn.microsoft.com/library/windows/desktop/aa367388))

- 출력 리디렉션([/o](https://msdn.microsoft.com/library/windows/desktop/aa367351))

- C 전처리 옵션([/cpp_opt](https://msdn.microsoft.com/library/windows/desktop/aa367318))

- 전처리기 정의 해제([/U](https://msdn.microsoft.com/library/windows/desktop/aa367373))

\* /robust는 Windows 2000 이상의 컴퓨터용으로 빌드할 때만 사용합니다. ATL 프로젝트를 빌드하고 /robust를 사용하려면 dlldatax.c 파일에서 이 줄을 변경합니다.

```
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM
to
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM
```

액세스 하는 방법에 대 한 정보에 대 한 합니다 **고급** 속성 페이지에서를 **MIDL** 폴더를 참조 하세요 [설정 C++ Visual Studio에서 컴파일러 및 빌드 속성](../working-with-project-properties.md).

C++ 프로젝트의 MIDL 옵션에 프로그래밍 방식으로 액세스하는 방법에 대한 자세한 내용은 <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>을 참조하세요.

## <a name="see-also"></a>참고자료

[MIDL 속성 페이지](midl-property-pages.md)
