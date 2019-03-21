---
title: -Clr을 사용 하 여 빌드한 COM 개체에서 throw 된 예외를 방지 합니다.
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
ms.openlocfilehash: bafcfb4e8a8abfecc8491220202b63971bef1ac8
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749245"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>/clr로 빌드한 COM 개체를 사용할 때 CLR 종료 시 예외 방지

CLR (공용 언어 런타임)가 종료 모드를 입력 한 후 네이티브 함수 CLR 서비스에 대 한 액세스 제한 됩니다. COM 개체를 사용 하 여 컴파일한 Release를 호출 하는 동안 **/clr**, CLR이 네이티브 코드로 전환 및 전환의 iunknown:: Release 호출 (관리 코드에 정의 된) 서비스를 관리 코드로 다시 합니다. CLR 종료 모드 이므로 관리 코드로 다시 호출을 방지 합니다.

이 해결 하려면 릴리스 메서드에서 호출 된 소멸자만 포함 네이티브 코드를 확인 합니다.

## <a name="see-also"></a>참고자료

[혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)
