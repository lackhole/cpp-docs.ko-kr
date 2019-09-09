---
title: CLR 통합(C++/CX)
ms.date: 01/22/2017
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
ms.openlocfilehash: 44ef35d1a62706cae37285c06547a8b9b7deb35c
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740290"
---
# <a name="clr-integration-ccx"></a>CLR 통합(C++/CX)

일부 Windows 런타임 형식은/Cx에서 C++특수 처리를 받고 CLR (공용 언어 런타임)을 기반으로 하는 언어를 제공 합니다. 이 문서에서는 한 언어의 여러 형식을 다른 언어에 매핑하는 방법을 설명합니다. 예를 들어 CLR은 Windows.Foundation.IVector를 System.Collections.IList에 매핑하고, Windows.Foundation.IMap를 System.Collections.IDictionary에 매핑합니다. 마찬가지로, C++/Cx는 platform::D 대리자 및 platform:: String과 같은 형식을 특별히 매핑합니다.

## <a name="mapping-the-windows-runtime-to-ccx"></a>/Cx에 C++Windows 런타임 매핑

/Cx C++가 Windows 메타 데이터 (winmd) 파일을 읽을 때 컴파일러는 일반적인 Windows 런타임 네임 스페이스와 형식을/cx 네임 C++스페이스 및 형식에 자동으로 매핑합니다. 예를 들어 숫자 Windows 런타임 형식은 `UInt32` 자동으로에 `default::uint32`매핑됩니다.

C++/CX는 여러 다른 Windows 런타임 형식을 **Platform** 네임 스페이스에 매핑합니다. 예를 들어 읽기 전용 유니코드 텍스트 문자열을 나타내는 **Windows:: Foundation** hstring 핸들은 C++/cx `Platform::String` 클래스에 매핑됩니다. Windows 런타임 작업이 오류 HRESULT를 반환 하는 경우 C++/cx `Platform::Exception`에 매핑됩니다.

또한 C++/cx는 Windows 런타임 네임 스페이스의 특정 형식을 매핑하여 형식의 기능을 향상 시킵니다. 이러한 형식에 대해 C++/cx는 C++ 와 관련 된 도우미 생성자 및 메서드를 제공 하며, 형식의 표준 winmd 파일에서 사용할 수 없습니다.

다음 목록에서는 새 생성자 및 도우미 메서드를 지원하는 값 구조체를 보여 줍니다. 구조체 초기화 목록을 사용하는 이전에 작성된 코드가 있으면 새로 추가된 생성자를 사용하도록 이를 변경합니다.

**Windows::Foundation**

- 점

- Rect

- Size

**Windows::UI**

- 색

**Windows::UI::Xaml**

- CornerRadius

- Duration

- GridLength

- Thickness

**Windows::UI::Xaml::Interop**

- TypeName

**Windows::UI::Xaml::Media**

- 행렬

**Windows::UI::Xaml::Media::Animation**

- KeyTime

- RepeatBehavior

**Windows::UI::Xaml::Media::Media3D**

- Matrix3D

## <a name="mapping-the-clr-to-ccx"></a>CLR을/Cx에 C++매핑

Microsoft C++ 또는 C# 컴파일러가 winmd 파일을 읽을 때 메타 데이터 파일의 특정 형식을 적절 한 C++/cx 또는 CLR 형식에 자동으로 매핑합니다. 예를 들어 CLR에서 IVector\<t > 인터페이스는 IList\<t >에 매핑됩니다. 그러나/cx C++에서 IVector\<T > 인터페이스는 다른 형식에 매핑되지 않습니다.

Windows 런타임\<의 IReference t >는 .net의 Nullable\<t >에 매핑됩니다.

## <a name="see-also"></a>참고자료

[다른 언어와의 상호 운용](../cppcx/interoperating-with-other-languages-c-cx.md)
