---
title: '방법: 부분적으로 신뢰할 수 있는 응용 프로그램 만들기 (C + + /cli CLI)'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- partially trusted applications [C++]
- mixed assemblies [C++], partially trusted applications
- msvcm90[d].dll
- interoperability [C++], partially trusted applications
- interop [C++], partially trusted applications
- /clr compiler option [C++], partially trusted applications
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
ms.openlocfilehash: afdfb8ca11753d7def9d7da6f431082b1a90c345
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743751"
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>방법: CRT 라이브러리 DLL에 대 한 종속성을 제거 하 여 부분적으로 신뢰할 수 있는 응용 프로그램 만들기

이 항목에서는 Visual c + +를 사용 하 여 msvcm90.dll에 대 한 종속성을 제거 하 여 부분적으로 신뢰할 수 있는 공용 언어 런타임 응용 프로그램을 만드는 방법을 설명 합니다.

사용 하 여 빌드한 Visual c + + 응용 프로그램을 **/clr** C 런타임 라이브러리의 일부인 msvcm90.dll에서 종속성을 갖습니다. 부분 신뢰 환경에서 사용할 응용 프로그램를 하려는 경우 CLR은 DLL에서 특정 코드 액세스 보안 규칙을 적용 합니다. 따라서 msvcm90.dll 네이티브 코드를 포함 하 고 여기에 코드 액세스 보안 정책을 적용할 수 없습니다 때문에이 종속성을 제거 해야 합니다.

응용 프로그램이 C 런타임 라이브러리의 모든 기능을 사용 하지 않습니다 하 고 코드에서이 라이브러리에 대 한 종속성을 제거 하려는 경우 사용 해야 합니다는 **/NODEFAULTLIB:msvcmrt.lib** 링커 옵션을 사용 하 여 링크 또는 ptrustmd.lib를 연결 해야 합니다. 초기화 및 초기화 해제는 응용 프로그램의 개체 파일을 포함 하는 이러한 라이브러리, 예외 클래스는 초기화 코드에서 사용 및 예외 처리 코드를 관리 합니다. 이러한 라이브러리 중 하나에 연결 msvcm90.dll에 대 한 종속성을 제거 됩니다.

> [!NOTE]
>  어셈블리 초기화 취소 작업의 순서는 ptrust 라이브러리를 사용 하는 응용 프로그램에 대 한 다를 수 있습니다. 일반 응용 프로그램의 경우 어셈블리는 일반적으로 로드 되는 보장 되지 않습니다 역순으로 해제 됩니다. 부분 신뢰 응용 프로그램에 대 한 어셈블리는 일반적으로 로드 되는 동일한 순서로 해제 됩니다. 이 또한 보장 되지 않습니다.

### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>부분적으로 신뢰할 수 있는 만들려면 혼합 (/ clr) 응용 프로그램

1. Msvcm90.dll에 대 한 종속성을 제거 하려면를 사용 하 여이 라이브러리를 포함 하지 않도록 링커에 지정 해야 합니다 **/NODEFAULTLIB:msvcmrt.lib** 링커 옵션입니다. Visual Studio 개발 환경을 사용 하 여 수행 하거나 프로그래밍 방식으로 참조 하는 방법에 대 한 내용은 [/NODEFAULTLIB (Ignore Libraries)](../build/reference/nodefaultlib-ignore-libraries.md)합니다.

1. 링커 입력된 종속성 ptrustm 라이브러리 중 하나를 추가 합니다. 릴리스 모드에서 응용 프로그램을 작성 하는 경우 ptrustm.lib를 사용 합니다. 디버그 모드에 대 한 사용 ptrustmd.lib를 연결 해야 합니다. Visual Studio 개발 환경을 사용 하 여 수행 하거나 프로그래밍 방식으로 참조 하는 방법에 대 한 내용은 [합니다. 링커 입력 파일로 파일을 lib](../build/reference/dot-lib-files-as-linker-input.md)합니다.

## <a name="see-also"></a>참고자료

[혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[혼합형 어셈블리 초기화](../dotnet/initialization-of-mixed-assemblies.md)<br/>
[혼합형 어셈블리에 대한 라이브러리 지원](../dotnet/library-support-for-mixed-assemblies.md)<br/>
[/link(옵션을 링커로 전달)](../build/reference/link-pass-options-to-linker.md)
