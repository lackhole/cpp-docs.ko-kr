---
title: 애플리케이션 도메인 및 Visual C++
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
ms.openlocfilehash: 2296654e6935bc40f301226b184cf34f77cb126d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223035"
---
# <a name="application-domains-and-visual-c"></a>응용 프로그램 도메인 및 시각적 개체C++

있는 경우는 `__clrcall` 가상 함수를 vtable 응용 프로그램 도메인 (appdomain) 됩니다. 한 appdomain에서 개체를 만드는 경우에 해당 appdomain 내에서 가상 함수를 호출할 수 있습니다. 혼합 모드에서 ( **/clr**) 형식에 있으면 프로세스별 vtable 해야 `__clrcall` 가상 함수입니다. **/clr: pure** 및 **/clr: safe** Visual Studio 2015에서 사용 되지 않고 Visual Studio 2017에서 지원 되지 않는 컴파일러 옵션입니다.

자세한 내용은 다음을 참조하세요.

- [appdomain](../cpp/appdomain.md)

- [__clrcall](../cpp/clrcall.md)

- [process](../cpp/process.md)

## <a name="see-also"></a>참고자료

- [혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)