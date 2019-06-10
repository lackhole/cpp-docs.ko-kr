---
title: Visual Studio 2015와 Visual Studio 2019 간의 C++ 이진 호환성
ms.date: 05/03/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: 052874eb9273ee9a9ce1695ffdadedd9911673e1
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65449042"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2019"></a>Visual Studio 2015와 Visual Studio 2019 간의 C++ 이진 호환성

Visual Studio 2013 및 이전 버전에서는 여러 버전의 컴파일러 도구 집합 및 런타임 라이브러리를 사용하여 빌드된 개체 파일(OBJ), 정적 라이브러리(LIB), 동적 라이브러리(DLL) 및 실행 파일(EXE) 간의 이진 호환성이 보장되지 않았습니다. 

Visual Studio 2015 이상에서 C++ 도구 집합 주 번호는 14입니다(Visual Studio 2015의 경우 v140, Visual Studio 2017의 경우 v141 및 Visual Studio 2019의 경우 v142). 이는 둘 중 한 버전의 컴파일러를 사용하여 컴파일된 런타임 라이브러리와 애플리케이션은 이진 호환성이 보장됨을 나타냅니다. 즉, Visual Studio 2015로 빌드된 타사 라이브러리가 있는 경우 Visual Studio 2017 또는 Visual Studio 2019로 빌드된 애플리케이션에서 사용하기 위해 다시 컴파일하지 않아도 됩니다.

이 규칙의 유일한 예외는 정적 라이브러리 또는 `/GL` 컴파일러 스위치로 컴파일된 개체 파일이 이진 호환되지 않는다는 것입니다. 

지원되는 다른 버전의 MSVC 도구 집합으로 빌드된 이진 파일을 혼합하면 애플리케이션이 실행되는 Visual C++ 재배포 가능 파일이 앱 빌드에 사용되는 도구 집합 버전 또는 사용하는 라이브러리보다 이전 버전일 수 없습니다. 

## <a name="see-also"></a>참고 항목

[Visual C++ 변경 기록](../porting/visual-cpp-change-history-2003-2015.md)
