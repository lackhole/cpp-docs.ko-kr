---
title: /errorReport(내부 컴파일러 오류 보고)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.ErrorReporting
- /errorreport
helpviewer_keywords:
- /errorReport compiler option [C++]
- -errorReport compiler option [C++]
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
ms.openlocfilehash: 52909cb42180bf8b778d73fd709be05faf3f5714
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271790"
---
# <a name="errorreport-report-internal-compiler-errors"></a>/errorReport(내부 컴파일러 오류 보고)

내부 컴파일러 오류(ICE, Internal Compiler Error) 정보를 Microsoft에 직접 제공할 수 있도록 합니다.

## <a name="syntax"></a>구문

```
/errorReport:[ none | prompt | queue | send ]
```

## <a name="arguments"></a>인수

**none**<br/>
내부 컴파일러 오류에 대한 보고서를 수집하거나 Microsoft로 보내지 않습니다.

**prompt**<br/>
내부 컴파일러 오류가 발생하면 보고서를 보낼지 묻는 메시지를 표시합니다. **prompt**는 개발 환경에서 응용 프로그램을 컴파일할 때 기본값입니다.

**queue**<br/>
오류 보고서를 큐에 넣습니다. 관리자 권한으로 로그인 하면 마지막 로그인한 이후 발생한 모든 오류를 보고할 수 있도록 창이 표시 됩니다 (3일에 한번 이상 오류에 대한 보고서를 보내라는 메시지를 표시하지 않습니다). **queue**는 명령 프롬프트에서 응용 프로그램을 컴파일할 때 기본값입니다.

**send**<br/>
Windows 오류 보고 시스템 설정으로 보고를 사용 하는 경우 Microsoft에 내부 컴파일러 오류 보고서를 자동으로 보냅니다.

## <a name="remarks"></a>설명

내부 컴파일러 오류(ICE)는 컴파일러에서 소스 코드 파일을 처리할 수 없을 때 발생합니다. ICE가 발생하면 컴파일러에서 출력 파일 또는 코드를 수정하는 데 사용할 수 있는 유용한 진단을 생성하지 않습니다.

이전 릴리스에서 ICE가 있을 때 Microsoft 기술 지원 서비스를 호출 하는 것이 좋습니다. **/errorReport**를 사용하면 Microsoft로 직접 ICE 정보를 보낼 수 있습니다. 오류 보고서는 향후 컴파일러 제품을 개선하는 데 도움이 됩니다.

사용자가 보고서를 보내는 기능은 컴퓨터 및 사용자 정책 권한에 따라 달라집니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **고급** 속성 페이지를 클릭합니다.

1. **오류 보고** 속성을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
