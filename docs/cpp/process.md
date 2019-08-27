---
title: 프로세스
ms.date: 11/04/2016
f1_keywords:
- process_cpp
helpviewer_keywords:
- __declspec keyword [C++], process
- process __declspec keyword
ms.assetid: 60eecc2f-4eef-4567-b9db-aaed34733023
ms.openlocfilehash: 049360dddff2b9ca2ea460b96e027e86899f1ecb
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344991"
---
# <a name="process"></a>프로세스

프로세스의 모든 애플리케이션 도메인에서 공유되는 특정 전역 변수, 정적 멤버 변수 또는 정적 지역 변수의 단일 복사본이 관리되는 애플리케이션 프로세스에 있어야 함을 지정합니다. 이 사용 하 여 컴파일할 때 사용 되는 주로 되었습니다 **/clr: pure**는 Visual Studio 2017에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않는 합니다. 사용 하 여 컴파일하면 **/clr**, 전역 및 정적 변수는 기본적으로 프로세스별 및를 사용 하지 않아도 **__declspec (process)** 합니다.

전역 변수, 정적 멤버 변수 또는 네이티브 형식의 정적 지역 변수를 사용 하 여 표시할 수 있습니다 **__declspec (process)** 합니다.

**프로세스** 사용 하 여 컴파일할 때만 유효 [/clr](../build/reference/clr-common-language-runtime-compilation.md)합니다.

사용 하 여 각 응용 프로그램 도메인에 전역 변수의 자체 복사본을 원한다 면 [appdomain](../cpp/appdomain.md)합니다.

참조 [응용 프로그램 도메인 및 시각적 개체 C++ ](../dotnet/application-domains-and-visual-cpp.md) 에 대 한 자세한 내용은 합니다.

## <a name="see-also"></a>참고자료

[__declspec](../cpp/declspec.md)<br/>
[키워드](../cpp/keywords-cpp.md)
