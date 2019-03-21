---
title: Visual Studio 2015와 Visual Studio 2017 간의 C++ 이진 호환성
ms.date: 09/24/2018
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: d0291ef75bda2e4da994e40ad55d94ae1042e57e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740513"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2017"></a>Visual Studio 2015와 Visual Studio 2017 간의 C++ 이진 호환성

이전 버전의 Visual Studio에서는 여러 버전의 컴파일러 도구 집합 및 런타임 라이브러리를 사용하여 빌드된 개체 파일(OBJ), 정적 라이브러리(LIB), 동적 라이브러리(DLL) 및 실행 파일(EXE) 간의 이진 호환성이 보장되지 않았습니다. Visual Studio 2017에서는 이러한 부분이 변경되었습니다. Visual Studio 2015 및 Visual Studio 2017에서는 C++ 도구 집합 주 번호는 14입니다(Visual Studio 2015의 경우 v140, Visual Studio 2017의 경우 v141). 이는 둘 중 한 버전의 컴파일러를 사용하여 컴파일된 런타임 라이브러리와 애플리케이션은 대부분 이진 호환성이 보장됨을 나타냅니다. 예를 들어 Visual Studio 2015에 DLL이 있는 경우 Visual Studio 2017을 사용하여 빌드된 애플리케이션에서 사용하기 위해 이 DLL을 다시 컴파일하지 않아도 됩니다.

이 규칙에는 두 가지 예외 사항이 있습니다. 이러한 경우 이진 호환성이 보장되지 않습니다.

1. 정적 라이브러리 또는 개체 파일이 `/GL` 컴파일러 스위치를 사용하여 컴파일된 경우.

2. 애플리케이션을 컴파일하고 연결하는 데 사용하는 도구 집합 보다 버전이 높은 도구 집합을 사용하여 빌드된 라이브러리를 사용한 경우 예를 들어 컴파일러 버전 19.12를 사용하여 컴파일되고 연결된 프로그램은 19.0~19.12로 컴파일된 라이브러리를 사용할 수 있습니다. 또한 이진 호환성은 Visual Studio 2015와 Visual Studio 2017 간에만 존재합니다. Visual Studio 2013 또는 이전 버전에서 생성된 라이브러리와 19.x 프로그램을 연결할 수는 없습니다.

## <a name="see-also"></a>참고 항목

[Visual C++ 변경 기록](../porting/visual-cpp-change-history-2003-2015.md)
